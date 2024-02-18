<h1>Applying Filters To SQL Queries</h1>

<h2>Languages and Utilities Used</h2>

- <b>SQL</b> 
- <b>Table Formats Document</b>

<h2>Description</h2>

My (fictitious)organization has asked me to make the system more secure. It is my job to investigate any potential security issues, update any employee machines as needed, and make sure that the overall system is secure. The following is an example of how I use SQL with filters to perform security related tasks. 
<br />

<h2>Retrieving After Hours Failed Login Attempts</h2>
After business hours (18:00), there was an incident where login attempts were detected after business hours, which warranting investigation into all failed login attempts. 

Below is the SQL query I developed to filter and analyze the failed login attempts that occurred after business hours:
<p align="center">
<img src="https://imgur.com/8gbcSf8.png" height="80%" width="80%" alt="Failed Login Attempts After Business Hours"/> </p>

This query filters for failed login attempts after 18:00. First, I started by selecting all data from the log_in_attempts table. I then used a WHERE clause with an AND operator to filter my results to output only login attempts that happened after 18:00 and were unsuccessful. The first condition is login_time > '18:00', which filters for the login attempts that occurred after 18:00. The second condition is success = FALSE, which filters for the failed login attempts



<h2>Retrieving Login Attempts On Specific Dates</h2>

An event that occurred on 2022-05-09 was found to be suspicious, which prompted the need for investigation into any login activity that occurred on that date or the day before. 

To facilitate the investigation, I have crafted an SQL query that effectively filters and identifies login attempts that occurred on the specified dates. The code below demonstrates the query:
<p align="center">
<img src="https://imgur.com/OPtvtNe.png" height="80%" width="80%" alt="Login Attempts On Specific Dates"/> </p>

The first part is the query. The second part is the output that returned all login attempts that occurred on 2022-05-09 or 2022-05-08. 

First, I started by selecting all of the data from the log_in_attempts table. I then used a WHERE clause with an OR operator to filter the results to output only login attempts that happened on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for logins on 2022-05-08.


<h2>Retrieving Login Attempts Outside Of Mexico</h2>

Upon thorough examination of the organization's login attempt data, it has come to my attention that there may be a concern with the login attempts originating outside of Mexico. It is essential to conduct a detailed investigation into these particular login activities. 

To address this issue, I have formulated an SQL query that filters and isolates login attempts originating from locations outside of Mexico. The code below showcases the implementation of this SQL query:
<p align="center">
<img src="https://imgur.com/gDgj0KY.png" height="80%" width="80%" alt="Login Attempts Outside Of Mexico"/> </p>

The first part is the query, while the second is the output that returned all the login attempts that occurred outside of Mexico. 

First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with NOT to filter the countries that aren't Mexico. I used LIKE with MEX% as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any number of unspecified characters when used with LIKE.


<h2>Retrieving Employees In Marketing</h2>

As a part of my team's efforts to upgrade the computers for specific employees in the Marketing department, I needed to gather information about which employee machines needed updates.

To achieve this, I developed a SQL query to filter and identify employee machines belonging to the Marketing department within the East building. The following code snippet showcases how I implemented this query:
<p align="center">
<img src="https://imgur.com/6GhNHNb.png" height="80%" width="80%" alt="Retrieving Employees In Marketing"/> </p>

The first part of the screenshot is my query, while the second part is the output that returned all employees in the Marketing department that are in the East building. 

I started by selecting all data from the employees table. Then, I used a WHERE clause with AND to filter for employees in the Marketing department and in the East building. I used LIKE with East% because the data in the office column represents the East building with the specific office number. The first condition is the department = 'Marketing' portion, which filters for employees in the Marketing department. The second condition is the office LIKE 'East%' portion, which filters for employees in the East building.

<h2>Retrieving Employees In Finance Or Sales</h2>

In addition to the general system updates, the machines for the employees in the Finance and Sales departments needed to be updated. A different security update is required, so I have to get information on employees only from these two departments. 

This portion demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments. The following code exemplifies how this query was created to ensure the targeted updates are applied accordingly.
<p align="center">
<img src="https://imgur.com/6q16Rj7.png" height="80%" width="80%" alt="Retrieving Employees In Finance Or Sales"/> </p>

The first part is my query, while the second part is a part of the output that shows a return of all employees in the Finance and Sales departments.

I started by selecting all data from the employees table. Then, I used a WHERE clause with OR to filter for employees who are in the Finance and Sales departments. I used the OR operator instead of AND because I want all employees who are in either the Finance or Sales department. The first condition is department = 'Finance’.  This filters for employees from the Finance department. While the second condition is department = 'Sales', which filters for employees from the Sales department.


<h2>Retrieving All Employees Not In IT</h2>

I needed to make one more security update on employees who are not in the Information Technology department. To make the update, I first have to get information on  employees that work in that particular department. The screenshot below shows how I created a SQL query to filter for employee machines from employees who are not in the Information Technology department.
<p align="center">
<img src="https://imgur.com/l3j8WoD.png" height="80%" width="80%" alt="Retrieving All Employees Not In IT"/> </p>

The first part is my query, and the second part is a small part of the output that returned all employees not in the Information Technology department. I started by selecting all data from the employees table. Then, I used a WHERE clause with NOT to filter for employees not in this department


<h2>Summary</h2>

I added filters to SQL queries to get specific information on login attempts and employee machines from two tables, log_in_attempts and employees. I used AND, OR, and NOT operators to combine the filters for each task. I also used LIKE and the percentage sign (%) wildcard to look for patterns.
