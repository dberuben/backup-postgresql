Base on # https://github.com/prodrigestivill/docker-postgres-backup-local

helm Chart
```
helm upgrade --install backup-postgresql .

```

### Environment Variables
Most variables are the same as in the [official postgres image](https://hub.docker.com/_/postgres/).

| env variable | description |
|--|--|
| BACKUP_KEEP_DAYS | Number of daily backups to keep before removal. Defaults to `7`. |
| BACKUP_KEEP_WEEKS | Number of weekkly backups to keep before removal. Defaults to `4`. |
| BACKUP_KEEP_MONTHS | Number of monthly backups to keep before removal. Defaults to `6`. |
| POSTGRES_DB | Comma or space separated list of postgres databases to backup. Required. |
| POSTGRES_HOST | Postgres connection parameter; postgres host to connect to. Required. |
| POSTGRES_PASSWORD | Postgres connection parameter; postgres password to connect with. Required. |
| POSTGRES_PORT | Postgres connection parameter; postgres port to connect to. Defaults to `5432`. |
| POSTGRES_USER | Postgres connection parameter; postgres user to connect with. Required. |
| AZURE_STORAGE_ACCOUNT | Storage Account Name |
| AZURE_STORAGE_KEY | The key |
| CONTAINER_NAME | Container where you push backup |
| SCHEDULE | [Cron-schedule](http://godoc.org/github.com/robfig/cron#hdr-Predefined_schedules) specifying the interval between postgres backups. Defaults to `@daily`. |

