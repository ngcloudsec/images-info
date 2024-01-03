# Introduction

Periodically scan top docker images on docker hub with [dep-scan](https://github.com/owasp-dep-scan/dep-scan) and generate the Software Bill-of-Materials (SBoM) and known vulnerabilities data.

## How does it work?

[ORAS cli](https://oras.land/cli/) is used to download the dep-scan binary and the vulnerability database.

```bash
export VDB_HOME=depscan
mkdir -p $VDB_HOME
oras pull ghcr.io/appthreat/vdb:v5 -o $VDB_HOME
oras pull ghcr.io/owasp-dep-scan/dep-scan:v5 -o $VDB_HOME
```

dep-scan is then invoked for each image in the [repo-list](repo-list.txt)

## Viewing reports

You can download the reports from the [latest workflow run](https://github.com/ngcloudsec/images-info/actions).
