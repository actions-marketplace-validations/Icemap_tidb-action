# TiDB Action

English | [中文](/README-zh.md)

## Description

- This is an unofficial [GitHub Action](https://github.com/features/actions), using Docker to deploy a TiDB.
- This library is developed based on [mirromutth/mysql-action](https://github.com/mirromutth/mysql-action).

## How to use

Minimal configuration:

```yaml
steps:
- uses: Icemap/tidb-action@v1.0
```

Full configuration:

```yaml
steps:
- uses: Icemap/tidb-action@v1.0
  with:
    port: 4001 # Optional, default is 4000, the port on which TiDB will run
    version: "v6.1.0" # Optional, default is v6.2.0, the version TiDB is running
    config: |
[tikv-client.async-commit]
safe-window = 0
allowed-clock-drift = 0 # Optional, default is empty, if you need special TiDB configuration, write the configuration here
    inner port: 4001 # Optional, defaults to 4000, refers port inside the TiDB container, which is a configuration that is only used if you change the port in the config param
```
