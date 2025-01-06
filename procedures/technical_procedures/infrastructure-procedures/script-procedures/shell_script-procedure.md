# shell script procedures

## Description

Find in this document all procedures related to shell script.

### error management


```shell
set -euo pipefail
```

### Header

header example :
```shell
# ------------------------------------------------------------------
# - Filename: main_postgresql_backup.sh
# - Author : ottomatic
# - Dependency : logs.sh
# - Description : script that backup a postgresql database.
# - Creation date :2024-11-18
# - Bash version : 5.2.15(1)-release
# ------------------------------------------------------------------
```

### function

function comment example :
```shell
checkMandatoryVariable() {
### valid that all variables tagged as mandatory are defined ###
    log "checking mandatory variables existence"
    for var in "${MANDATORY_VAR_LIST[@]}"; do
        if [[ -z "${var+x}" ]]; then
            error "$var is not defined or is empty."
            return 1
        fi
    done
}
```