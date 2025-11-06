# Developer Notes

Flux Shared DB is open-source. The code is written in Node.js (server-side) and an HTML/JS-based UI. To contribute or customize:

* **Source & Build:** Check out the GitHub repo. It uses standard Node.js tooling; after cloning, run `npm install` and modify the code in the `ClusterOperator` (backend) or `ui` directories. You can test locally or build a Docker image.
* **Adding Features:** The cluster operator is modular. Future work includes supporting new database engines; for example, MongoDB and PostgreSQL support are listed as TODOs. You can contribute by implementing the necessary replication logic and APIs for those engines.
* **Pull Requests:** If you fix bugs or add features, submit pull requests on GitHub. (Issues list any known problems or requests.)
* **Customization:** You may customize operator behavior via environment variables (see above). The code also reads a `containerData` directory (`s:/app/dumps`) for backups; adjust this path if needed.
* **Documentation:** There is no published OpenAPI spec for the HTTP APIs yet. You can explore endpoints by browsing the UI or reading the source. Keep an eye on the project GitHub for updates to docs.

### Deployment

You can deploy Flux Shared DB via Docker or on Flux’s cloud platform. In all cases you need a database engine (e.g. MySQL) and one or more Shared DB operator instances configured to connect to that engine.

* **Docker (local or cloud):** Pull the official image `runonflux/shared-db:latest`. In a `docker-compose.yml`, include your DB engine service (e.g. `mysql:latest`) and the `runonflux/shared-db` operator. Set the required environment variables (below) on the operator and link it to the DB engine. By default, the operator exposes port **3307** for MySQL clients[github.com](https://github.com/RunOnFlux/Flux-Shared-DB). For example, use `docker run` or Compose to start the DB and operator together, so the operator can proxy to the database.
* **Local (manual):** For testing, you can run it locally. Clone the GitHub repo and use Node.js or Docker directly. For example, after setting the same environment variables (below) you could execute `npm install` and `node ClusterOperator/server.js` in the repo (port 3307 will be open). Alternatively, use `docker run` with the image and env vars to connect to your MySQL instance.

### Security and Access Control

By default, Flux Shared DB has **no built-in authentication** beyond the MySQL credentials you supply. Security considerations include:

* **Database Credentials:** You must set `DB_INIT_PASS` (root password) and preferably change `DB_USER` from the default. Treat these credentials securely. The operator will only allow login with the configured user/password.
* **IP Whitelisting:** Use the `WHITELIST` variable to restrict which IP addresses can connect to port 3307. Only clients from those IPs will be allowed to use the DB interface.
* **Master-Only Access:** If `authMasterOnly=true`, then only the master node will accept client connections. Slave nodes will refuse connections from the app, preventing split-brain or accidental use of stale data.
* **Network Security:** In Flux deployments, the internal API (port 7071) and UI port (8008) should be firewalled or accessible only over the Flux private network, as they have no public auth. Encrypt the `DB_PORT` connection (e.g. via TLS tunnel) if connecting over untrusted networks.
* **Flux Environment:** The operator assumes a trusted FluxOS environment. Operators should monitor and update the software regularly. Note: the project currently has no formal security policy or audit published, so use caution in production and follow best practices (e.g. use strong passwords, limit network exposure, and regularly back up data).

In summary, control access through strong DB credentials, IP whitelisting, and the `authMasterOnly` setting. Always ensure that only intended apps on the Flux network can reach your Shared DB operator.

**Sources:** The above information is drawn from the official Flux Shared DB documentation and code on GitHub [https://github.com/RunOnFlux/Flux-Shared-DB](https://github.com/RunOnFlux/Flux-Shared-DB), including the repository README and comments. Any uncited details are either common database knowledge or explicit in the cited sections.

### API Structure and Endpoints

Flux Shared DB exposes three interfaces:

* **DB Interface (MySQL Protocol):** Listens by default on port **3307**. It speaks the MySQL wire protocol, so any MySQL client or library can connect as if it were a MySQL server. Reads are executed on the connected node’s database, while writes are forwarded to the master. You can run any SQL command (CREATE/DROP/SELECT/INSERT/UPDATE/DELETE) against this interface.
* **Internal Cluster API:** Exposes an HTTP API (by default on port **7071**) used internally for inter-node communication (replication, heartbeats, etc.). This is not typically used by client applications.
* **UI/Management API:** Runs an HTTP server (default port **8008**) that provides a web UI and JSON endpoints for managing or monitoring the cluster. (For example, there may be endpoints to check cluster status or configuration.) Detailed API documentation is not yet published, but you can access the UI by navigating to `http://<operator_host>:8008`.

In summary, the operator has 3 interfaces – a **DB proxy**, an **internal API**, and a **UI/API** – as outlined in the official docs [https://github.com/RunOnFlux/Flux-Shared-DB/blob/master/Dockerfile](https://github.com/RunOnFlux/Flux-Shared-DB/blob/master/Dockerfile)



### Example Usage

Since Flux Shared DB behaves like MySQL, you use it with normal SQL commands. For example, after starting the operator (with a database named `example_db`), connect to it using a MySQL client on port 3307:

```sql
sqlCopyEdit-- Connect to the operator (host=<operator_ip>, port=3307)
mysql -h <operator_ip> -P 3307 -u root -p

-- (Enter the password you set in DB_INIT_PASS)

-- Create and use a test database
CREATE DATABASE example;
USE example;

-- Create a table and insert data
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
```



Flux Shared DB is an open-source service written in **Node.js** (server-side) with an **HTML/JavaScript-based UI**. This section provides guidance for contributing, customizing, deploying, and securing the operator.

***

### 🧩 Source & Contribution

#### 🔗 GitHub Repository

You can find the source code on GitHub:\
[**https://github.com/RunOnFlux/Flux-Shared-DB**](https://github.com/RunOnFlux/Flux-Shared-DB)

#### 🛠️ Build & Run Locally

Clone the repository and install dependencies:

```bash
bashCopyEditgit clone https://github.com/RunOnFlux/Flux-Shared-DB.git
cd Flux-Shared-DB
npm install
```

To test:

* Modify code in the `/ClusterOperator` (backend) or `/ui` (frontend) directories.
* Run the backend using `node ClusterOperator/server.js` or package the app with Docker.

#### 🔧 Adding Features

The operator is modular. Planned extensions include:

* **Support for additional DB engines** (e.g., MongoDB, PostgreSQL).
* You can contribute by implementing replication logic and extending APIs for new engines.

#### 📬 Pull Requests

* Fix bugs or add features via GitHub pull requests.
* Check the [Issues](https://github.com/RunOnFlux/Flux-Shared-DB/issues) section for known bugs or feature requests.

***

### ⚙️ Customization

#### Environment Variables

Customize operator behavior using environment variables (see previous sections for examples).

#### Data Directory

The operator reads from `s:/app/dumps` for backup and restore. You may adjust this path as needed.

***

### 📦 Deployment Options

#### 1. Docker (Local or Cloud)

Use the official image:

```bash
bashCopyEditrunonflux/shared-db:latest
```

In a `docker-compose.yml`, define:

* Your DB engine service (e.g., `mysql:latest`)
* The Shared DB operator container

Set required environment variables, and expose:

* **3307** for MySQL client traffic

```yaml
yamlCopyEditservices:
  db:
    image: mysql:latest
    ...
  operator:
    image: runonflux/shared-db:latest
    ports:
      - "3307:3307"
    environment:
      - DB_INIT_PASS=yourpassword
      - ...
```

#### 2. Local Manual Setup

For development:

```bash
bashCopyEditnpm install
node ClusterOperator/server.js
```

Alternatively:

```bash
bashCopyEditdocker run -p 3307:3307 -e DB_INIT_PASS=yourpassword runonflux/shared-db:latest
```

***

### 🔒 Security & Access Control

Flux Shared DB does not implement user authentication beyond DB credentials. Secure your deployment with:

#### 🔐 Credentials

* Set a strong value for `DB_INIT_PASS`
* Use `DB_USER` with non-default usernames

#### 📍 IP Whitelisting

Restrict access to port **3307** using the `WHITELIST` variable:

```env
envCopyEditWHITELIST=1.2.3.4,5.6.7.8
```

#### 👑 Master-Only Mode

Set `authMasterOnly=true` to allow only the master node to accept client traffic.

#### 🌐 Network Recommendations

* **Port 7071** (internal API) and **8008** (UI) should only be accessible from trusted networks.
* Use encryption (e.g., TLS tunnel) for remote DB\_PORT access.

> ⚠️ There is no formal security policy or audit. Always follow best practices and update the operator regularly.

***

### 🔌 Interfaces & Endpoints

| Interface           | Port | Purpose                                          |
| ------------------- | ---- | ------------------------------------------------ |
| **DB Proxy**        | 3307 | Accepts MySQL protocol connections               |
| **Cluster API**     | 7071 | Internal HTTP API for replication, health checks |
| **UI / Management** | 8008 | Web interface and JSON endpoints                 |

* The UI can be accessed at:\
  `http://<operator_host>:8008`
* API documentation is not published yet; inspect the UI or source for details.

***

### 💡 Example Usage

Assume you've deployed Flux Shared DB with a MySQL container and created a DB named `example_db`. Connect using a MySQL client:

```bash
bashCopyEditmysql -h <operator_ip> -P 3307 -u root -p
```

```sql
sqlCopyEditCREATE DATABASE example_db;
USE example_db;
CREATE TABLE users (id INT PRIMARY KEY, name VARCHAR(100));
INSERT INTO users VALUES (1, 'Alice');
SELECT * FROM users;
```

> All SQL queries use the MySQL protocol. Write operations are forwarded to the master node.

***

### 📚 References

* **Official GitHub:** [RunOnFlux/Flux-Shared-DB](https://github.com/RunOnFlux/Flux-Shared-DB)
* All technical guidance here is derived from the repository’s README, source code, and comments.

***

Let me know if you'd like a downloadable `.md` version or if this needs to be adapted to a GitBook layout specifically.
