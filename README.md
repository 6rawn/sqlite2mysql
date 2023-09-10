# mysql2sqlite3-sample

## Procedure

```
$ docker compose up -d

$ curl -L -O https://www.sqlitetutorial.net/wp-content/uploads/2018/03/chinook.zip
$ unzip chinook.zip && rm chinook.zip

$ sqlite3 chinook.db
sqlite> .tables
sqlite> .schema employees
sqlite> .dump <table name>
sqlite> .exit

$ docker compose exec -it node-1 bash
$ mysql -uroot -pmysql -e "CREATE DATABASE chinook;"
$ exit

$ pip3 install sqlite3-to-mysql
$ sqlite3mysql -f ./chinook.db -h localhost -u root -p -d chinook

$ docker compose exec -it node-1 bash
$ mysql -uroot -pmysql
mysql> use chinook
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
mysql> show tables;
+-------------------+
| Tables_in_chinook |
+-------------------+
| albums            |
| artists           |
| customers         |
| employees         |
| genres            |
| invoice_items     |
| invoices          |
| media_types       |
| playlist_track    |
| playlists         |
| tracks            |
+-------------------+
11 rows in set (0.00 sec)

```
