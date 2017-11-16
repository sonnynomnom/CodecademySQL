# CodecademySQL

`./upload workspaces/sql_unit_4 --type:sql`

```sql
CREATE TABLE albums_new(id INTEGER, name TEXT, artist_id INTEGER, year INTEGER);

INSERT INTO albums_new(id, name, artist_id, year) VALUES (1, 'Blonde', NULL, 2016);
INSERT INTO albums_new(id, name, artist_id, year) VALUES (2, 'Return to Love', NULL, 2016);
INSERT INTO albums_new(id, name, artist_id, year) VALUES (3, 'Haunts EP', NULL, 2017);

UPDATE albums_new
SET id = 15
WHERE name = 'Blonde';

UPDATE albums_new
SET id = 16
WHERE name = 'Return to Love';

UPDATE albums_new
SET id = 17
WHERE name = 'Haunts EP';
```


```sql
INSERT INTO movies(id, name, genre, year, imdb_rating) VALUES (221, 'The Good, the Bad and the Ugly', NULL, NULL, NULL);
INSERT INTO movies(id, name, genre, year, imdb_rating) VALUES (222, 'Dawn of the Dead', 'horror', 1978, NULL);
INSERT INTO movies(id, name, genre, year, imdb_rating) VALUES (223, 'Shawn of the Dead', 'comedy', 2004, NULL);
INSERT INTO movies(id, name, genre, year, imdb_rating) VALUES (224, 'Star Wars: The Force Awakens', 'action', 2015, 8.1);
INSERT INTO movies(id, name, genre, year, imdb_rating) VALUES (225, 'Star Wars: The Last Jedi', 'action', 2017, NULL);
INSERT INTO movies(id, name, genre, year, imdb_rating) VALUES (226, 'The Shining', 'horror', 1985, 8.4);
INSERT INTO movies(id, name, genre, year, imdb_rating) VALUES (227, 'The Devil and Daniel Johnston', NULL, 2005, 8.0);
INSERT INTO movies(id, name, genre, year, imdb_rating) VALUES (228, 'Ali Wong: Baby Cobra', 'comedy', 2016, NULL);
INSERT INTO movies(id, name, genre, year, imdb_rating) VALUES (229, 'The Big Sick', 'romance', 2017, NULL);
INSERT INTO movies(id, name, genre, year, imdb_rating) VALUES (230, 'Deadpool', 'action', 2016, NULL);
```

./upload workspaces/sql_unit_2 --type:sql

```sql
UPDATE movies
SET genre = NULL
WHERE name = 'Ali Wong: Baby Cobra';
```



# Queries

## 14. Case

**Checkpoint 2**

Following this format, edit the previous query and create our very own rating system:

- IMDb ratings above 7 is 'good'
- IMDb ratings above 5 is 'ok'
- everything else is 'mmm'

Finish the `CASE` by renaming it with an alias of your choosing.

**Hint:**

```sql
SELECT name,
 CASE
  WHEN imdb_rating > 7 THEN 'good'
  WHEN imdb_rating > 5 THEN 'ok'
  ELSE 'mmm'
 END AS whatever
FROM movies;
```

The result should have two columns.

**Tests.activeBatsTest('test2.bats', callback);**

@test "The query didn't return any results." {
    touch empty.txt
    run diff output.txt empty.txt
    [ "$status" -eq 1 ]
}

@test "Remove the previous query." {
	sqlite3 output.sqlite "SELECT name,
 CASE
  WHEN genre = 'romance' THEN 'chill'
  WHEN genre = 'comedy' THEN 'chill'
  ELSE 'not chill'
 END AS mood
FROM movies; SELECT name,
 CASE
  WHEN imdb_rating > 7 THEN 'good'
  WHEN imdb_rating > 5 THEN 'ok'
  ELSE 'mmm'
 END AS ratings
FROM movies;" > tmp.txt
  run diff output.txt tmp.txt
  [ "$status" -eq 1 ]
}

@test "Type the code in the code editor using the appropriate clauses." {
  	sqlite3 output.sqlite "SELECT name,
 CASE
  WHEN imdb_rating > 7 THEN 'good'
  WHEN imdb_rating > 5 THEN 'ok'
  ELSE 'mmm'
 END AS ratings
FROM movies;"  > tmp.txt
  	run diff output.txt tmp.txt
  	[ "$status" -eq 0 ]
}


## Project

```sql

CREATE TABLE nomnom(name TEXT, neighborhood TEXT, cuisine TEXT, review INTEGER, price TEXT, health TEXT);


INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Peter Luger Steak House', 'Brooklyn', 'Steak', 4.4, '$$$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Jongro BBQ', 'Midtown', 'Korean', 4.5, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Pocha 32', 'Midtown', 'Korean', 4.0, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Nom Wah Tea Parlor', 'Chinatown', 'Chinese', 4.2, '$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Roberta''s', 'Brooklyn', 'Pizza', 4.4, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Speedy Romeo', 'Brooklyn', 'Pizza', 4.4, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Bunna Cafe', 'Brooklyn', 'Ethiopian', 4.6, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Massawa', 'Uptown', 'Ethiopian', 4.0, '$$', NULL);

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Buddha Bodai', 'Chinatown', 'Vegetarian', 4.2, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Nan Xiang Xiao Long Bao', 'Queens', 'Chinese', 4.2, '$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Mission Chinese Food', 'Downtown', 'Chinese', 3.9, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Baohaus', 'Downtown', 'Chinese', 4.2, '$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('al di la Trattoria', 'Brooklyn', 'Italian', 4.4, '$$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Locanda Vini & Olii', 'Brooklyn', 'Italian', 4.4, '$$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Rao''s', 'Uptown', 'Italian', 4.2, '$$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Minca', 'Downtown', 'Japanese', 4.4, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Kenka', 'Downtown', 'Japanese', 4.3, '$', 'B');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Yakitori Taisho', 'Downtown', 'Japanese', 4.1, '$', 'B');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Xi''an Famous Foods', 'Midtown', 'Chinese', 4.4, '$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Shake Shack', 'Midtown', 'American', 4.4, '$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('The Halal Guys', 'Midtown', 'Mediterranean', 4.4, '$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Foodcademy', 'Midtown', 'American', 4.4, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Sonnyboy''s', 'Brooklyn', 'Chinese', 4.2, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('The Cole Romano Experience', 'Brooklyn', 'Italian', 2.1, '$$$$$', 'C');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Timbo Slice', 'Brooklyn', 'Pizza', 2.8, '$', 'B');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Scorpio Sisters', 'Downtown', 'American', 4.2, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('N.E.D', 'Uptown', 'American', 4.2, '$$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Great NY Noodletown', 'Chinatown', 'Chinese', 4.1, '$$', 'B');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Golden Unicorn', 'Chinatown', 'Chinese', 3.8, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Wo Hop', 'Chinatown', 'Chinese', 4.2, '$$', NULL);

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Di Fara Pizza', 'Brooklyn', 'Pizza', 4.2, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Kang Ho Dong Baekjeong', 'Midtown', 'Korean', 4.3, '$$$', 'C');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Roti Roll Bombay Frankie', 'Uptown', 'Indian', 4.2, '$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Jacob''s Pickles', 'Uptown', 'American', NULL, '$$', NULL);

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Dan and John''s Wings', 'Downtown', 'American', 4.5, '$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Ping''s Seafood', 'Chinatown', 'Chinese', 4.2, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('XO Kitchen', 'Chinatown', 'Chinese', 4.0, '$', 'B');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Carbone', 'Downtown', 'Italian', 4.3, '$$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('I Sodi', 'Downtown', 'Italian', 4.5, '$$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Lilia', 'Brooklyn', 'Italian', 4.4, '$$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Enid''s', 'Brooklyn', 'Soul Food', 4.0, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Jajaja', 'Downtown', 'Vegetarian', 4.5, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Smalls Jazz Club', 'Downtown', 'American', NULL, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Russ & Daughters', 'Downtown', 'American', 4.6, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('The Meatball Shop', 'Downtown', 'American', 4.2, '$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Dirt Candy', 'Downtown', 'Vegetarian', 4.4, '$$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Ippudo', 'Downtown', 'Japanese', 4.4, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('St. Anselm', 'Brooklyn', 'Steak', 4.5, '$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Marea', 'Midtown', 'Italian', 4.5, '$$$$', 'A');

INSERT INTO nomnom(name, neighborhood, cuisine, review, price, health) VALUES ('Lighthouse', 'Brooklyn', 'American', 4.6, '$$', NULL);

```





# Multiple Tables





## 2. Primary Key

**Narrative**

The primary key in the `artists` is literally an `id` value for a record. We're going to use this value to connect `artists` to the `albums` they have produced.

**Checkpoint 1**

We have created a table named `albums` for you. Create a second table named `artists`.

In the code editor, type:

```sql
CREATE TABLE artists(id INTEGER PRIMARY KEY, name TEXT);
```

**Tests.activeBatsTest('test.bats', callback);**

table_exists() {
  sqlite3 output.sqlite "SELECT * FROM $1 LIMIT 1"
}

column_exists?() {
  sqlite3 output.sqlite "SELECT $2 FROM $1"
}

@test "Create an 'artists' table" {
  run table_exists artists
  [ "$status" -eq 0 ]
}

@test "Include an id column" {
  run column_exists? artists id
  [ "$status" -eq 0 ]
}

@test "Include a name column" {
  run column_exists? artists name
  [ "$status" -eq 0 ]
}

@test "Artists table should be empty." {
  run sqlite3 output.sqlite "SELECT COUNT(*) FROM artists"
  [ "$output" -eq 0 ]
}

@test "Artists table should have two columns." {
  run sqlite3 output.sqlite "INSERT INTO artists VALUES(1,2)"
  [ "$status" -eq 0 ]
}

@test "Artists table should have a primary key." {
  run sqlite3 output.sqlite "INSERT INTO artists(id) VALUES(1)"
  [ "$status" -eq 19 ]
}

@test "Delete data inserted for tests" {
  sqlite3 output.sqlite "DELETE FROM artists WHERE id > 0"
}








**Checkpoint 1**

Sometimes our data needs a massive change, type the following to recreate our `albums` table safely even if the table doesn't exist.

```sql
 DROP TABLE IF EXISTS albums;

 CREATE TABLE IF NOT EXISTS albums(
    id INTEGER PRIMARY KEY,
    name TEXT,
    artist_id INTEGER,
    year INTEGER);
```

**Tests.activeBatsTest('test.bats', callback);**

table_exists() {
  sqlite3 output.sqlite "SELECT * FROM $1 LIMIT 1"
}

column_exists?() {
  sqlite3 output.sqlite "SELECT $2 FROM $1"
}

@test "Create an 'albums' table" {
  run table_exists albums
  [ "$status" -eq 0 ]
}

@test "Include an id column" {
  run column_exists? albums id
  [ "$status" -eq 0 ]
}

@test "Include a name column" {
  run column_exists? albums name
  [ "$status" -eq 0 ]
}

@test "Include a year column" {
  run column_exists? albums year
  [ "$status" -eq 0 ]
}

@test "Include a artist_id column" {
  run column_exists? albums artist_id
  [ "$status" -eq 0 ]
}

@test "Albums table should be empty." {
  run sqlite3 output.sqlite "SELECT COUNT(*) FROM albums"
  [ "$output" -eq 0 ]
}

@test "Albums table should have four columns." {
  run sqlite3 output.sqlite "INSERT INTO albums VALUES(1,2,3,4)"
  [ "$status" -eq 0 ]
}

@test "Albums table should have a primary key." {
  run sqlite3 output.sqlite "INSERT INTO albums(id) VALUES(1)"
  [ "$status" -eq 19 ]
}

@test "Delete data inserted for tests" {
  sqlite3 output.sqlite "DELETE FROM albums WHERE id > 0"
}




## 8. Multiple Table Creation (DELETED)

**Narrative**

```sql
 DROP TABLE IF EXISTS albums;

 CREATE TABLE IF NOT EXISTS albums(
   id INTEGER PRIMARY KEY,
   name TEXT,
   artist_id INTEGER,
   year INTEGER);
```

`DROP TABLE IF EXISTS` is a SQL command that will drop a table or do nothing, depending on if the table already exists. Usually if you attempt to drop a table that does not exist your SQL client will throw an error but in this case, it will fail silently. This is best for situations where your data is in an unknown state and you intend to reseed it.

`CREATE TABLE IF NOT EXISTS`, by contrast, will create a table or do nothing, depending on if the table already exists. These two are frequently used together when a database has an external source of truth and the two have fallen out of sync.

**Checkpoint 1**

Of course, usually, we will want to recreate the table somewhat differently than before. Let's fix something about that albums table this time. Type:

```sql
 DROP TABLE IF EXISTS albums;

 CREATE TABLE IF NOT EXISTS albums(
   id INTEGER PRIMARY KEY,
   name TEXT,
   year INTEGER,
   artist_id INTEGER,
   FOREIGN KEY(artist_id) REFERENCES artist(id)
 );
```

**Tests.activeBatsTest('test.bats', callback);**

table_exists() {
  sqlite3 output.sqlite "SELECT * FROM $1 LIMIT 1"
}

column_exists?() {
  sqlite3 output.sqlite "SELECT $2 FROM $1"
}

get_lowercase_schema() {
	sqlite3 output.sqlite "SELECT sql FROM sqlite_master WHERE TYPE='table' AND NAME='$1'" | tr -d '\n' | tr '[[:upper:]]' '[[:lower:]]'
}

@test "Create an 'albums' table" {
  run table_exists albums
  [ "$status" -eq 0 ]
}

@test "Include an id column" {
  run column_exists? albums id
  [ "$status" -eq 0 ]
}

@test "Include a name column" {
  run column_exists? albums name
  [ "$status" -eq 0 ]
}

@test "Include a year column" {
  run column_exists? albums year
  [ "$status" -eq 0 ]
}

@test "Include a artist_id column" {
  run column_exists? albums artist_id
  [ "$status" -eq 0 ]
}

@test "Albums table should be empty." {
  run sqlite3 output.sqlite "SELECT COUNT(*) FROM albums"
  [ "$output" -eq 0 ]
}

@test "Albums table should have four columns." {
  run sqlite3 output.sqlite "INSERT INTO albums VALUES(1,2,3,4)"
  [ "$status" -eq 0 ]
}

@test "Albums table should have a primary key." {
  run sqlite3 output.sqlite "INSERT INTO albums(id) VALUES(1)"
  [ "$status" -eq 19 ]
}  

@test "Make sure the columns have appropriate constraints set." {
  run get_lowercase_schema albums
  [[ $output =~ foreign[[:space:]]*key\(artist_id\)[[:space:]]*references[[:space:]]*artist\(id\) ]]
}

@test "Delete data inserted for tests" {
  sqlite3 output.sqlite "DELETE FROM albums WHERE id > 0"
}

**Config**

Command to be run the first time user starts this exercise.

cp ./.exercise_1.sqlite db.sqlite



## 9. Foreign Key Constraints (DELETED)

**Narrative**

```sql
 DROP TABLE IF EXISTS albums;

 CREATE TABLE IF NOT EXISTS albums(
   id INTEGER PRIMARY KEY,
   name TEXT,
   year INTEGER,
   artist_id INTEGER,
   FOREIGN KEY(artist_id) REFERENCES artist(id)
 );
```

`FOREIGN KEY` can also be a _constraint_, specified using this syntax.

`artist_id` is a column belonging to the table currently being defined.

If we try to `INSERT` data into our `albums` table where the new value for `artist_id` does not match an `id` in our `artist` table, we can't. This is valuable for validating our data (and making sure we don't insert the wrong information into our database)!

**Checkpoints**

In this lesson we learned about relationships between tables in relational databases. We also learned how to query data from multiple tables using SQL.

Let's summarize what we've learned so far.

**Config**

Command to be run the first time user starts this exercise.

cp ./.exercise_1.sqlite db.sqlite