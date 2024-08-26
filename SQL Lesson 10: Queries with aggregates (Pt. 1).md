- In addition to the simple expressions that we introduced last lesson, SQL also supports the use of aggregate expressions (or functions) that allow you to summarize information about a group of rows of data.
- With the Pixar database that you've been using, aggregate functions can be used to answer questions like, "How many movies has Pixar produced?", or "What is the highest grossing Pixar film each year?".

#### Select query with aggregate functions over all rows: 
> SELECT AGG_FUNC(column_or_expression) AS aggregate_description, …                   
FROM mytable                    
WHERE constraint_expression;

- Without a specified grouping, each aggregate function is going to run on the whole set of result rows and return a single value.
- And like normal expressions, giving your aggregate functions an alias ensures that the results will be easier to read and process.

![comman agg fnc](https://github.com/user-attachments/assets/f5ea2adf-5519-4b7a-a544-1b76b2f8c2ec)


### Grouped aggregate functions
- In addition to aggregating across all the rows, you can instead apply the aggregate functions to individual groups of data within that group (ie. box office sales for Comedies vs Action movies).
- This would then create as many results as there are unique groups defined as by the GROUP BY clause.

#### Select query with aggregate functions over groups : 
> SELECT AGG_FUNC(column_or_expression) AS aggregate_description, …             
FROM mytable                
WHERE constraint_expression                       
GROUP BY column;


- The GROUP BY clause works by grouping rows that have the same value in the column specified.

### Exercise :
- For this exercise, we are going to work with our Employees table.
- Notice how the rows in this table have shared data,
- which will give us an opportunity to use aggregate functions to summarize some high-level metrics about the teams.

Table: employees :                       
role	name	building	years_employed            
Engineer	Becky A.	1e	4           
Engineer	Dan B.	1e	2          
Engineer	Sharon F.	1e	6       
Engineer	Dan M.	1e	4         
Engineer	Malcom S.	1e	1         
Artist	Tylar S.	2w	2          
Artist	Sherman D.	2w	8           
Artist	Jakob J.	2w	6         
Artist	Lillia A.	2w	7       
Artist	Brandon J.	2w	7        
Manager	Scott K.	1e	9         
Manager	Shirlee M.	1e	3         
Manager	Daria O.	2w	6                           

Tasks : 
Find the longest time that an employee has been at the studio:
> SELECT max(years_employed) as max_years_employed FROM employees;                

For each role, find the average number of years employed by employees in that role:
> SELECT role, AVG(years_employed) as Average_years_employed                 
FROM employees           
GROUP BY role;                                                 

Find the total number of employee years worked in each building:
> SELECT role, AVG(years_employed) as Average_years_employed                   
FROM employees            
GROUP BY role;
>

