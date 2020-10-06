psql -d postgres -U db_user

exo1:

CREATE DATABASE db_1;

CREATE TABLE users (id SERIAL PRIMARY KEY, name VARCHAR(30), password VARCHAR(30));

INSERT INTO users (name, password) VALUES ('alice','123'),('bob','456'),('charlie','789');

SELECT \* FROM users;
id | name | password
----+---------+----------
1 | alice | 123
2 | bob | 456
3 | charlie | 789
(3 rows)

exo2:

INSERT INTO users (name,password) VALUES ('dan','101112'),('eve','131415'),('faythe','161718');

id | name | password
----+---------+----------
1 | alice | 123
2 | bob | 456
3 | charlie | 789
4 | dan | 101112
5 | eve | 131415
6 | faythe | 161718
(6 rows)

exo 3:
SELECT \* FROM users WHERE length(password)>3;
id | name | password
----+--------+----------
4 | dan | 101112
5 | eve | 131415
6 | faythe | 161718
(3 rows)

exo4:

ALTER TABLE users ADD COLUMN bio VARCHAR(255);
id | name | password | bio
----+---------+----------+-----
1 | alice | 123 |
2 | bob | 456 |
3 | charlie | 789 |
4 | dan | 101112 |
5 | eve | 131415 |
6 | faythe | 161718 |
(6 rows)

exo5:
UPDATE users SET bio = 'Hello, i'm '||(name);
SELECT \* FROM users;
id | name | password | bio
----+---------+----------+---------------------
1 | alice | 123 | Hello, i am alice
2 | bob | 456 | Hello, i am bob
3 | charlie | 789 | Hello, i am charlie
4 | dan | 101112 | Hello, i am dan
5 | eve | 131415 | Hello, i am eve
6 | faythe | 161718 | Hello, i am faythe
(6 rows)

exo6:

exo7:

SELECT \* FROM USERS WHERE ID%2=1;
id | name | password | bio
----+---------+----------+---------------------
1 | alice | 123 | Hello, i am alice
3 | charlie | 789 | Hello, i am charlie
5 | eve | 131415 | Hello, i am eve
(3 rows)

exo8:

DELETE FROM users WHERE id%2=0;
DELETE 3
db_1=> SELECT \* FROM users;
id | name | password | bio
----+---------+----------+---------------------
1 | alice | 123 | Hello, i am alice
3 | charlie | 789 | Hello, i am charlie
5 | eve | 131415 | Hello, i am eve
(3 rows)

exo9:
