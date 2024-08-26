- Our queries are getting fairly complex, but we have nearly introduced all the important parts of a SELECT query. 
- One thing that you might have noticed is that if the GROUP BY clause is executed after the WHERE clause (which filters the rows which are to be grouped), 
- then how exactly do we filter the grouped rows?

- Luckily, SQL allows us to do this by adding an additional HAVING clause which is used specifically with the GROUP BY clause to allow us to filter grouped rows from the result set.

#### Select query with HAVING constraint:
> SELECT group_by_column, AGG_FUNC(column_expression) AS aggregate_result_alias, …             
FROM mytable              
WHERE condition             
GROUP BY column                
HAVING group_condition;

- The HAVING clause constraints are written the same way as the WHERE clause constraints, and are applied to the grouped rows. 
- With our examples, this might not seem like a particularly useful construct,
- but if you imagine data with millions of rows with different properties,
- being able to apply additional constraints is often necessary to quickly make sense of the data.

#### Exercise : 
- For this exercise, you are going to dive deeper into Employee data at the film studio.
- Think about the different clauses you want to apply for each task.

Table: employees:                       
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

#### Tasks:
Find the number of Artists in the studio (without a HAVING clause):
> SELECT count(name) FROM employees             
where role="Artist";


Find the number of Employees of each role in the studio:
> SELECT role, COUNT(*)           
FROM employees      
GROUP BY role;           

Find the total number of years employed by all Engineers:
> SELECT role, SUM(years_employed)           
FROM employees        
GROUP BY role          
HAVING role = "Engineer";                     


