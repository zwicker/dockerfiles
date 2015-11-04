# dockerfiles

This docker repo exists on docker hub under zwicker/postgres.

```
docker pull zwicker/postgres
docker run --name <container-name> -e POSTGRES_DB=<db> -e POSTGRES_USER=<user> -e POSTGRES_PASSWORD=<password> -v <data-dir>:/var/lib/postgresql/data -p 5432 -d zwicker/postgres
```
