# SQL Homework

The Codeclan Cinema is having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'

```
# terminal
createdb marvel
```

Next, run the provided SQL script to populate your database:

```
# terminal
psql -d marvel -f marvel.sql
```

Use the supplied data as the source of data to answer the questions. Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1.  Return ALL the data in the 'movies' table.

SELECT * FROM movies;

id |                title                | year | show_time
----+-------------------------------------+------+-----------
 1 | Iron Man                            | 2008 | 19:05
 2 | The Incredible Hulk                 | 2008 | 16:55
 3 | Iron Man 2                          | 2010 | 20:30
 4 | Thor                                | 2011 | 15:40
 5 | Captain America: The First Avenger  | 2011 | 12:35
 6 | Avengers Assemble                   | 2012 | 19:35
 7 | Iron Man 3                          | 2013 | 16:10
 8 | Thor: The Dark World                | 2013 | 12:55
 9 | Batman Begins                       | 2005 | 22:55
10 | Captain America: The Winter Soldier | 2014 | 12:15
11 | Guardians of the Galaxy             | 2014 | 17:45
12 | Avengers: Age of Ultron             | 2015 | 15:35
13 | Ant-Man                             | 2015 | 19:20
14 | Captain America: Civil War          | 2016 | 16:00
15 | Doctor Strange                      | 2016 | 12:10
16 | Guardians of the Galaxy 2           | 2017 | 21:50
17 | Spider-Man: Homecoming              | 2017 | 17:25
18 | Thor: Ragnarok                      | 2017 | 23:30
19 | Black Panther                       | 2018 | 23:35
(19 rows)

2.  Return ONLY the name column from the 'people' table

SELECT name FROM people;

name         
---------------------
 Geraldine Antonelli
 Eric Downie
 Aurimas Drungilas
 Sarah Grant
 Adam Hidvegi
 Nathan Langridge
 Sreenandini Mallela
 Kevin McDonalds
 Paul Melville
 Rebecca Still
 Stan Tarnev
 Christopher Wales
 Ally Conway
(13 rows)

3.  Oops! Someone spelled Kevin's surname wrong! Change it to reflect the proper spelling (McDermott).

UPDATE people SET name = 'Kevin McDermott' WHERE name = 'Kevin McDonalds';
SELECT name FROM people;

UPDATE 1
        name         
---------------------
 Geraldine Antonelli
 Eric Downie
 Aurimas Drungilas
 Sarah Grant
 Adam Hidvegi
 Nathan Langridge
 Sreenandini Mallela
 Paul Melville
 Rebecca Still
 Stan Tarnev
 Christopher Wales
 Ally Conway
 Kevin McDermott
(13 rows)

4.  Return ONLY Stan Tarnev's name from the 'people' table.

SELECT name FROM people WHERE name = 'Stan Tarnev';

name     
-------------
 Stan Tarnev
(1 row)

5.  The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.

DELETE FROM movies WHERE title = 'Batman Begins';
SELECT * FROM movies;

id |                title                | year | show_time
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 19:05
  2 | The Incredible Hulk                 | 2008 | 16:55
  3 | Iron Man 2                          | 2010 | 20:30
  4 | Thor                                | 2011 | 15:40
  5 | Captain America: The First Avenger  | 2011 | 12:35
  6 | Avengers Assemble                   | 2012 | 19:35
  7 | Iron Man 3                          | 2013 | 16:10
  8 | Thor: The Dark World                | 2013 | 12:55
 10 | Captain America: The Winter Soldier | 2014 | 12:15
 11 | Guardians of the Galaxy             | 2014 | 17:45
 12 | Avengers: Age of Ultron             | 2015 | 15:35
 13 | Ant-Man                             | 2015 | 19:20
 14 | Captain America: Civil War          | 2016 | 16:00
 15 | Doctor Strange                      | 2016 | 12:10
 16 | Guardians of the Galaxy 2           | 2017 | 21:50
 17 | Spider-Man: Homecoming              | 2017 | 17:25
 18 | Thor: Ragnarok                      | 2017 | 23:30
 19 | Black Panther                       | 2018 | 23:35
(18 rows)

6.  We forgot one of the main characters! Add Colin Bell to the 'people' table

INSERT INTO people (name) VALUES ('Colin Bell');
SELECT name from people;

name         
---------------------
Geraldine Antonelli
Eric Downie
Aurimas Drungilas
Sarah Grant
Adam Hidvegi
Nathan Langridge
Sreenandini Mallela
Kevin McDonalds
Paul Melville
Rebecca Still
Stan Tarnev
Christopher Wales
Ally Conway
Colin Bell
(14 rows)

7.  Ally has decided to hijack our movie evening, Remove him from the table of people.

DELETE FROM people WHERE name = 'Ally Conway';
SELECT name from PEOPLE;

name         
---------------------
 Geraldine Antonelli
 Eric Downie
 Aurimas Drungilas
 Sarah Grant
 Adam Hidvegi
 Nathan Langridge
 Sreenandini Mallela
 Kevin McDonalds
 Paul Melville
 Rebecca Still
 Stan Tarnev
 Christopher Wales
(12 rows)

8.  The cinema has just heard that they will be holding an exclusive midnight showing of 'Avengers: Infinity War'!! Create a new entry in the 'movies' table to reflect this.

INSERT INTO movies (title, year, show_time) VALUES ('Avengers: Infinity War', 2018, '00:00');
SELECT * FROM movies;

id |                title                | year | show_time
----+-------------------------------------+------+-----------
 1 | Iron Man                            | 2008 | 19:05
 2 | The Incredible Hulk                 | 2008 | 16:55
 3 | Iron Man 2                          | 2010 | 20:30
 4 | Thor                                | 2011 | 15:40
 5 | Captain America: The First Avenger  | 2011 | 12:35
 6 | Avengers Assemble                   | 2012 | 19:35
 7 | Iron Man 3                          | 2013 | 16:10
 8 | Thor: The Dark World                | 2013 | 12:55
 9 | Batman Begins                       | 2005 | 22:55
10 | Captain America: The Winter Soldier | 2014 | 12:15
11 | Guardians of the Galaxy             | 2014 | 17:45
12 | Avengers: Age of Ultron             | 2015 | 15:35
13 | Ant-Man                             | 2015 | 19:20
14 | Captain America: Civil War          | 2016 | 16:00
15 | Doctor Strange                      | 2016 | 12:10
16 | Guardians of the Galaxy 2           | 2017 | 21:50
17 | Spider-Man: Homecoming              | 2017 | 17:25
18 | Thor: Ragnarok                      | 2017 | 23:30
19 | Black Panther                       | 2018 | 23:35
20 | Avengers: Infinity War              | 2018 | 00:00
(20 rows)

9.  The cinema would like to make the Iron Man movies a triple billing. Find out the show time of "Iron Man 2" and set the show time of "Iron Man 3" to start two hours later.

SELECT show_time FROM movies WHERE title = 'Iron Man 2';
UPDATE movies SET show_time = '22:30' WHERE title = 'Iron Man 3';
SELECT title, show_time FROM movies WHERE title LIKE 'Iron Man%';

show_time
-----------
20:30
(1 row)

UPDATE 1
  title    | show_time
------------+-----------
Iron Man   | 19:05
Iron Man 2 | 20:30
Iron Man 3 | 22:30
(3 rows)

## Extension

1.  Research how to delete multiple entries from your table in a single command.
