- When you have new entities and relationships to store in your database, you can create a new database table using the CREATE TABLE statement.

### Create table statement w/ optional table constraint and default value :
> CREATE TABLE IF NOT EXISTS mytable (                         
    column DataType TableConstraint DEFAULT default_value,            
    another_column DataType TableConstraint DEFAULT default_value,          
    …       
);     

- The structure of the new table is defined by its table schema,
- which defines a series of columns.
- Each column has a name, the type of data allowed in that column, an optional table constraint on values being inserted, and an optional default value.

- If there already exists a table with the same name, the SQL implementation will usually throw an error,
- so to suppress the error and skip creating a table if one exists, you can use the IF NOT EXISTS clause.

### DataTypes :
![Screenshot 2024-08-27 162033](https://github.com/user-attachments/assets/faae552e-6eb4-4dba-a553-b71724af4acb)

![Screenshot 2024-08-27 162127](https://github.com/user-attachments/assets/76e4e5db-f54e-487e-a9df-089723047290)

### Exercise
- In this exercise, you'll need to create a new table for us to insert some new rows into.

Tasks : 
Create a new table named Database with the following columns:
– Name A string (text) describing the name of the database
– Version A number (floating point) of the latest version of this database
– Download_count An integer count of the number of times this database was downloaded
This table has no constraints. 

> create table database(                                      
Name varchar(10),Version  float,Download_count integer);


