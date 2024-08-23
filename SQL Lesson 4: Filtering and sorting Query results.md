- Even though the data in a database may be unique, the results of any particular query may not be –
- take our Movies table for example, many different movies can be released the same year.
- In such cases, SQL provides a convenient way to discard rows that have a duplicate column value by using the DISTINCT keyword.

### Select query with unique results
SELECT DISTINCT column, another_column, …
FROM mytable
WHERE condition(s);

#### Ordering results:
Unlike our neatly ordered table in the last few lessons, most data in real databases are added in no 
particular column order. As a result, it can be difficult to read through and understand the results of a 
query as the size of a table increases to thousands or even millions rows.

#### To help with this, SQL provides a way to sort your results by a given column in ascending or descending order using the "ORDER BY" clause.

### Select query with ordered results
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC;

When an ORDER BY clause is specified, each row is sorted alpha-numerically based on the specified column's value. 
In some databases, you can also specify a collation to better sort data containing international text.

#### Limiting results to a subset
Another clause which is commonly used with the ORDER BY clause are the LIMIT and OFFSET clauses, which are a useful optimization to indicate to the database the subset of the results you care about.
The LIMIT will reduce the number of rows to return, and the optional OFFSET will specify where to begin counting the number rows from.

#### Select query with limited rows
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC
LIMIT num_limit OFFSET num_offset;


### Exercise
There are a few concepts in this lesson, but all are pretty straight-forward to apply. To spice things up, we've gone and scrambled the Movies table for you in the exercise to better mimic what kind of data you might see in real life. 
Try and use the necessary keywords and clauses introduced above in your queries.

Table: movies
id	title	director	year	length_minutes
1	Monsters, Inc.	Pete Docter	2001	92
2	Toy Story	John Lasseter	1995	81
3	Finding Nemo	Andrew Stanton	2003	107
4	The Incredibles	Brad Bird	2004	116
5	Toy Story 2	John Lasseter	1999	93
6	Cars 2	John Lasseter	2011	120
7	Cars	John Lasseter	2006	117
8	Up	Pete Docter	2009	101
9	Monsters University	Dan Scanlon	2013	110
10	Brave	Brenda Chapman	2012	102
11	Toy Story 3	Lee Unkrich	2010	103
12	WALL-E	Andrew Stanton	2008	104
13	A Bug's Life	John Lasseter	1998	95
14	Ratatouille	Brad Bird	2007	115


### List all directors of Pixar movies (alphabetically), without duplicates:
SELECT DISTINCT director FROM movies
ORDER BY director ASC;


### List the last four Pixar movies released (ordered from most recent to least):
select title from movies 
order by year desc
limit 4;


### List the first five Pixar movies sorted alphabetically:
select title from movies
order by title asc
limit 5;


### List the next five Pixar movies sorted alphabetically:
select title from movies
order by title asc
limit 5 offset 5;


