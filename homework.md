# SQL Homework

The Dominion Cinema are having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

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

Use the supplied data as the source of data to answer the questions.  Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1. Return ALL the data in the 'movies' table.

SELECT * FROM movies;

 id |                title                | year | show_time 
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 15:40
  2 | The Incredible Hulk                 | 2008 | 23:45
  3 | Iron Man 2                          | 2010 | 17:45
  4 | Thor                                | 2011 | 14:40
  5 | Captain America: The First Avenger  | 2011 | 17:05
  6 | Avengers Assemble                   | 2012 | 12:30
  7 | Iron Man 3                          | 2013 | 18:00
  8 | Thor: The Dark World                | 2013 | 18:55
  9 | Batman Begins                       | 2005 | 16:30
 10 | Captain America: The Winter Soldier | 2014 | 19:20
 11 | Guardians of the Galaxy             | 2014 | 12:10
 12 | Avengers: Age of Ultron             | 2015 | 23:40
 13 | Ant-Man                             | 2015 | 18:20
 14 | Captain America: Civil War          | 2016 | 22:00
 15 | Doctor Strange                      | 2016 | 16:30
(15 rows)

2. Return ONLY the name column from the 'people' table

SELECT name FROM people;

       name        
-------------------
 Chris Bacon
 John Campbell
 Jane Cargill
 Patrick Collins
 Stephanie Devine
 Ben Faulkner
 Cameron Fulton
 Tegan Gallacher
 Gregor Gilchrist
 Claire Hilditch
 Graeme Bell
 Winnie Ho
 Adam Leel
 Lewis MacNee
 Adam Nattrass
 William Robertson
 Jordan Said
 Logan Smith
 Frederico Zucca
(19 rows)

3. Return ONLY your name from the 'people' table.

SELECT name FROM people WHERE name = 'Claire Hilditch';

      name       
-----------------
 Claire Hilditch
(1 row)


4. The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.

DELETE FROM movies WHERE title = 'Batman Begins';
SELECT * FROM movies;

DELETE 1
 id |                title                | year | show_time 
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 15:40
  2 | The Incredible Hulk                 | 2008 | 23:45
  3 | Iron Man 2                          | 2010 | 17:45
  4 | Thor                                | 2011 | 14:40
  5 | Captain America: The First Avenger  | 2011 | 17:05
  6 | Avengers Assemble                   | 2012 | 12:30
  7 | Iron Man 3                          | 2013 | 18:00
  8 | Thor: The Dark World                | 2013 | 18:55
 10 | Captain America: The Winter Soldier | 2014 | 19:20
 11 | Guardians of the Galaxy             | 2014 | 12:10
 12 | Avengers: Age of Ultron             | 2015 | 23:40
 13 | Ant-Man                             | 2015 | 18:20
 14 | Captain America: Civil War          | 2016 | 22:00
 15 | Doctor Strange                      | 2016 | 16:30
(14 rows)

5. Create a new entry in the 'people' table with the name of one of the instructors.

INSERT INTO people (name) VALUES ('John Harper');
SELECT name FROM people;

       name        
-------------------
 Chris Bacon
 John Campbell
 Jane Cargill
 Patrick Collins
 Stephanie Devine
 Ben Faulkner
 Cameron Fulton
 Tegan Gallacher
 Gregor Gilchrist
 Claire Hilditch
 Graeme Bell
 Winnie Ho
 Adam Leel
 Lewis MacNee
 Adam Nattrass
 William Robertson
 Jordan Said
 Logan Smith
 Frederico Zucca
 John Harper
(20 rows)


6. Sadly, Graeme has hurt himself and wont be able to make it, Delete his entry from the 'people' table

DELETE FROM people WHERE name = 'Graeme Bell';
SELECT name FROM people;

DELETE 1
       name        
-------------------
 Chris Bacon
 John Campbell
 Jane Cargill
 Patrick Collins
 Stephanie Devine
 Ben Faulkner
 Cameron Fulton
 Tegan Gallacher
 Gregor Gilchrist
 Claire Hilditch
 Winnie Ho
 Adam Leel
 Lewis MacNee
 Adam Nattrass
 William Robertson
 Jordan Said
 Logan Smith
 Frederico Zucca
(18 rows)


7. Somehow the list of people includes two people named 'Adam'. Change these entries to the proper names (Jeff 3, Jeff 3.2)

SELECT * FROM people;
UPDATE people SET name = 'Jeff 3' WHERE id = 15;
UPDATE people SET name = 'Jeff 3.2' WHERE id = 13;
SELECT * FROM people;

UPDATE 1
UPDATE 1
 id |       name        
----+-------------------
  1 | Chris Bacon
  2 | John Campbell
  3 | Jane Cargill
  4 | Patrick Collins
  5 | Stephanie Devine
  6 | Ben Faulkner
  7 | Cameron Fulton
  8 | Tegan Gallacher
  9 | Gregor Gilchrist
 10 | Claire Hilditch
 11 | Graeme Bell
 12 | Winnie Ho
 14 | Lewis MacNee
 16 | William Robertson
 17 | Jordan Said
 18 | Logan Smith
 19 | Frederico Zucca
 15 | Jeff 3
 13 | Jeff 3.2
(19 rows)

8. The cinema has just heard that they will be holding an exclusive midnight showing of 'Guardians of the Galaxy 2'!! Create a new entry in the 'movies' table to reflect this.

INSERT INTO movies (title, year, show_time) VALUES ('Guardians of the Galaxy 2', 2016, '00:00');
SELECT * FROM movies;


 id |                title                | year | show_time 
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 15:40
  2 | The Incredible Hulk                 | 2008 | 23:45
  3 | Iron Man 2                          | 2010 | 17:45
  4 | Thor                                | 2011 | 14:40
  5 | Captain America: The First Avenger  | 2011 | 17:05
  6 | Avengers Assemble                   | 2012 | 12:30
  7 | Iron Man 3                          | 2013 | 18:00
  8 | Thor: The Dark World                | 2013 | 18:55
  9 | Batman Begins                       | 2005 | 16:30
 10 | Captain America: The Winter Soldier | 2014 | 19:20
 11 | Guardians of the Galaxy             | 2014 | 12:10
 12 | Avengers: Age of Ultron             | 2015 | 23:40
 13 | Ant-Man                             | 2015 | 18:20
 14 | Captain America: Civil War          | 2016 | 22:00
 15 | Doctor Strange                      | 2016 | 16:30
 16 | Guardians of the Galaxy 2           | 2016 | 00:00
(16 rows)

9. The cinema would also like to make the Guardian movies a back to back feature. Update the 'Guardians of the Galaxy' show time from 12:10 to 21:30

SELECT * FROM movies;
UPDATE movies SET show_time = '21:30' WHERE id = 11;
SELECT * FROM movies WHERE title = 'Guardians of the Galaxy';

UPDATE 1
 id |          title          | year | show_time 
----+-------------------------+------+-----------
 11 | Guardians of the Galaxy | 2014 | 21:30
(1 row)

10. Fix Federico's name!

UPDATE people SET name = 'Federico Zucca' WHERE name = 'Frederico Zucca';
SELECT * FROM people;

 id |       name        
----+-------------------
  1 | Chris Bacon
  2 | John Campbell
  3 | Jane Cargill
  4 | Patrick Collins
  5 | Stephanie Devine
  6 | Ben Faulkner
  7 | Cameron Fulton
  8 | Tegan Gallacher
  9 | Gregor Gilchrist
 10 | Claire Hilditch
 11 | Graeme Bell
 12 | Winnie Ho
 13 | Adam Leel
 14 | Lewis MacNee
 15 | Adam Nattrass
 16 | William Robertson
 17 | Jordan Said
 18 | Logan Smith
 19 | Federico Zucca
(19 rows)

## Extension

1. Research how to delete multiple entries from your table in a single command.


