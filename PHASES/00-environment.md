# phase 00 — environment

## prerequisite

docker or local mysql installed; .net sdk installed per course.

## goal

mysql container runs; `FourthWallCafe` database exists; you can connect from host.

## steps you do

1. read [docker-compose.yml](../../docker-compose.yml) — note port `3306` and password in env.  
2. run compose; run [setup-database.sh](../../setup-database.sh) or execute `db/setup.sql` the way your instructor showed.  
3. verify: connect with mysql client or gui; see tables from `setup.sql`.

## sanity check

`SELECT COUNT(*) FROM Server;` returns a positive number.

## common mistakes

- wrong password in connection string  
- forgot to expose port 3306  
- script ran against wrong database name  

## reflection

what single string will you put in `appsettings.json` for the connection?
