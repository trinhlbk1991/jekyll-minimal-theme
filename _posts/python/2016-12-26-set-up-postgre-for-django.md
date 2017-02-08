## 1. Install postgre

## 2. Create a Database
```
CREATE DATABASE myproject;
```
Remember to end all commands at an SQL prompt with a semicolon.

## 3. Create a User

```
CREATE USER myprojectuser WITH PASSWORD 'password';
```

Afterwards, we'll modify a few of the connection parameters for the user we just created. This will speed up database operations so that the correct values do not have to be queried and set each time a connection is established.

We are setting the default encoding to UTF-8, which Django expects. We are also setting the default transaction isolation scheme to "read committed", which blocks reads from uncommitted transactions. Lastly, we are setting the timezone. By default, our Django projects will be set to use UTC:

```
ALTER ROLE myprojectuser SET client_encoding TO 'utf8';
ALTER ROLE myprojectuser SET default_transaction_isolation TO 'read committed';
ALTER ROLE myprojectuser SET timezone TO 'UTC';
```

Now, all we need to do is give our database user access rights to the database we created:

```
GRANT ALL PRIVILEGES ON DATABASE myproject TO myprojectuser;
```

