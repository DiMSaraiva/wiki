---
id: pos-errors
title: Common Node Errors
sidebar_label: Node Errors
description: Common questions on validator operations
keywords:
  - docs
  - matic
  - polygon
  - validator
  - faq
image: https://wiki.polygon.technology/img/polygon-logo.png
---

This guide aims to provide solutions for common errors you might encounter while interacting with Polygon PoS. If you come across an error that is not listed here, please consult Polygon Support or community forums for additional help.

## Table of Node Errors

| Error                                         | Component  | Description                                                      | Cause                                           | Solution                                                                                     |
|-----------------------------------------------|------------|------------------------------------------------------------------|--------------------------------------------------|----------------------------------------------------------------------------------------------|
| `Failed to Unlock Account`                     | Bor        | Unable to find or unlock the specified Ethereum account.         | Incorrect paths for `password.txt` and Keystore files. | <ol><li>Move keystore to `/etc/bor/dataDir/keystore` or `/var/lib/bor/keystore/` (binaries.)</li><li>Move `password.txt` to `/etc/bor/dataDir/` or `/var/lib/bor/` (binaries.)</li><li>Update `/etc/bor/metadata`.</li></ol>|
| `Wrong Block.Header.AppHash`                   | Heimdall   | Stuck on a specific block and cannot proceed.                    | Block synchronization issue.                      | <ol><li>Stop Heimdall (`sudo service heimdalld stop`).</li><li>Reset (`heimdalld unsafe-reset-all`).</li><li>Resync (Download & extract snapshot).</li></ol>                           |
| `Unknown db_backend leveldb`                   | General    | The specified database backend in the configuration is unrecognized. | Invalid `db_backend` configuration.             | Modify the `db_backend` setting to `goleveldb` in `config.toml`.                             |
| `Object "start" is unknown`                    | Validator  | The bridge program being executed is incorrect.                  | Wrong "bridge" program in use.                    | Execute the correct bridge program using `~/go/bin/bridge` or `$GOBIN/bridge`.               |
| `dpkg: error processing archive`               | Sys Admin  | A package conflict occurs during installation.                   | Pre-existing Matic installation.                  | Execute `sudo dpkg -r matic-node` to remove the conflicting package.                          |
| `Gas Exceeded`                                 | Validator  | The gas limit for a transaction has been exceeded.               | Incorrect stake or fee amount formatting.         | Ensure that stake and fee amounts are formatted with 18 decimals.                             |
| `Unable to unmarshall config`                  | General    | The configuration file contains errors.                          | Typos, missing elements, or outdated config files.| Remove any old or incorrect config files and set up the configuration again.                  |
| `Wrong Block.Header.AppHash (Infura)`          | Heimdall   | Infura request limits have been reached.                         | Infura request quota exceeded.                    | Generate a new Infura API key and update it in the `config.toml` file.                        |
| `Failed Sanity Checks in Heimdall`             | Heimdall   | Address book warnings are displayed in the logs.                 | Address book warnings.                            | Usually can be ignored if connected to sufficient peers.                                      |
| `Node Not Signing Checkpoints`                 | Heimdall   | Not signing any checkpoints.                                     | Missing `ETH_RPC_URL` in `heimdall-config.toml`.  | Add the correct `ETH_RPC_URL` and restart Heimdall.                                           |
| `Heimdall Pong Timeout`                        | Heimdall   | Connection timeouts are occurring.                               | Network connectivity issues.                      | Restart the Heimdall service.                                                                 |
| `Error: Wrong Block.Header.AppHash in Heimdall`| Heimdall   | Stuck on a specific block.                                       | Incorrect block header hash.                      | Reset Heimdall and sync from the snapshot again.                                               |
| `WAL File Corruption in Heimdall`              | Heimdall   | The Write-Ahead Log (WAL) file is corrupted.                     | Corrupted WAL file.                               | Repair the WAL file as per the provided commands.                                              |
| `Bor Unable to Find Peers`                     | Bor        | Not connecting to any peers.                                     | Network connectivity issues.                      | Check TrustedNodes and StaticNodes in `config.toml` and restart Bor.                           |
