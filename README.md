# Electron test

[Electron](https://www.electronjs.org/)

# Database connection
Use docker for create a database for testing

```bash
docker run --name mysql-generic -p 3306:3306 -e MYSQL_ROOT_PASSWORD=R00T -d mysql:5.7
```
You can access to container bash

```bash
docker exec -it mysql-generic bash
```

```bash
mysql -uroot -p
```

And load a test database.

```bash
CREATE DATABASE control_comedor;
CREATE USER 'admin'@'%' IDENTIFIED BY '4dm1n';
GRANT ALL PRIVILEGES ON control_comedor.* TO 'admin'@'%';
```

```bash
USE control_comedor;
CREATE TABLE IF NOT EXISTS users (user_id int(10) NOT NULL AUTO_INCREMENT, user_name VARCHAR(80) NOT NULL, CONSTRAINT key1 PRIMARY KEY (user_id));
INSERT INTO users VALUES (1, "Juan Manuel Ruiz");
INSERT INTO users VALUES (2, "Marco A Gallardo");
INSERT INTO users VALUES (3, "Faustino Neri Larios");
```