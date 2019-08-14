Base on # https://github.com/prodrigestivill/docker-postgres-backup-local

helm Chart
```
helm upgrade --install backup-postgresql .

```

### Environment Variables
Most variables are the same as in the [official postgres image](https://hub.docker.com/_/postgres/).

| env variable | description |
|--|--|
| BACKUP_DIR | Directory to save the backup at. Defaults to `/backups`. |
| BACKUP_KEEP_DAYS | Number of daily backups to keep before removal. Defaults to `7`. |
| BACKUP_KEEP_WEEKS | Number of weekkly backups to keep before removal. Defaults to `4`. |
| BACKUP_KEEP_MONTHS | Number of monthly backups to keep before removal. Defaults to `6`. |
| HEALTHCHECK_PORT | Port listening for cron-schedule health check. Defaults to `8080`. |
| POSTGRES_DB | Comma or space separated list of postgres databases to backup. Required. |
| POSTGRES_DB_FILE | Alternative to POSTGRES_DB, but with one database per line, for usage with docker secrets. |
| POSTGRES_EXTRA_OPTS | Additional options for `pg_dump`. Defaults to `-Z9`. |
| POSTGRES_HOST | Postgres connection parameter; postgres host to connect to. Required. |
| POSTGRES_PASSWORD | Postgres connection parameter; postgres password to connect with. Required. |
| POSTGRES_PASSWORD_FILE | Alternative to POSTGRES_PASSWORD, for usage with docker secrets. |
| POSTGRES_PORT | Postgres connection parameter; postgres port to connect to. Defaults to `5432`. |
| POSTGRES_USER | Postgres connection parameter; postgres user to connect with. Required. |
| POSTGRES_USER_FILE | Alternative to POSTGRES_USER, for usage with docker secrets. |
| AZURE_STORAGE_ACCOUNT | Storage Account Name |
| AZURE_STORAGE_KEY | The key |
| CONTAINER_NAME | Container where you push backup |
| SCHEDULE | [Cron-schedule](http://godoc.org/github.com/robfig/cron#hdr-Predefined_schedules) specifying the interval between postgres backups. Defaults to `@daily`. |

