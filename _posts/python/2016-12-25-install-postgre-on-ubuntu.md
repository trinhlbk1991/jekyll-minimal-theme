---
category: "Python"
---


## 1. Add PostgreSQL Apt Repository

```
$ sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" >> /etc/apt/sources.list.d/pgdg.list'
$ wget -q https://www.postgresql.org/media/keys/ACCC4CF8.asc -O - | sudo apt-key add -
```

## 2. Install PostgreSQL

```
$ sudo apt-get update
$ sudo apt-get install postgresql postgresql-contrib
```

## 3. Connect to PostgreSQL
After installing PostgreSQL database server, by default it creates a user `postgres` with role `postgres`. 
It also creates a system account with same name `postgres`. 
So to connect to postgres server, login to your system as user postgres and connect database.

```
$ sudo su - postgres
$ psql
```

Now you are logged in to PostgreSQL database server. To check login info use following command from database command prompt.
