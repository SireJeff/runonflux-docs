# Option 5 – Restore Flux Blockchain

Downloads a fresh bootstrap snapshot and restarts your Flux daemon when your node falls out of sync.

***

### When to Run

* Node shows increasing block lag under **Option 3**
* Node has been offline for an extended period

***

### How to Use

1.  **Clean old snapshot**

    ```bash
    rm -f $HOME/flux_explorer_bootstrap.tar.gz
    ```
2. Select **5** in the toolbox.
3. Choose **1: Download bootstrap** when prompted.
4. Confirm removal of any existing archive.
5. Wait as the script benchmarks download servers, fetches, and unpacks the snapshot.
