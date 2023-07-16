<h1>Apply filters to SQL queries</h1>

<h2>Project description</h2>
My organization is working to make their system more secure. It is my job to ensure the system is safe, investigate all potential security issues, and update employee computers as needed. The following steps provide examples of how I used SQL with filters to perform security-related tasks.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Diskpart</b>

<h2>Secnaria 1 - </h2>
  You recently discovered a potential security incident that occurred after business hours. To investigate this, you need to query the log_in_attempts table and review after hours login activity. Use filters in SQL to create a query that identifies all failed login attempts that occurred after 18:00. (The time of the login attempt is found in the login_time column. The success column contains a value of 0 when a login attempt failed; you can use either a value of 0 or FALSE in your query to identify failed login attempts.) Describe your query and how it works in the Retrieve after hours failed login attempts section of the Apply filters to SQL queries template. 

- <b>Windows 10</b> (21H2)

<h2>SQL Filters walk-through:</h2>

<h2>Retrieve after hours failed login attempts:</h2>

There was a potential security incident that occurred after business hours (after 18:00). All after hours login attempts that failed need to be investigated.

The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours.
<p align="center">
After hours failed login attempts: <br/>
<img src="https://i.imgur.com/KAl9AkG.jpg" height="80%" width="80%" alt="SQL Filters"/>
 
  The first part of the screenshot is my query, and the second part is a portion of the output. This query filters for failed login attempts that occurred after 18:00. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an AND operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is login_time > '18:00', which filters for the login attempts that occurred after 18:00. The second condition is success = FALSE, which filters for the failed login attempts.
<br />
<br />
<h2>Retrieve login attempts on specific dates </h2>

A suspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before needs to be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred on specific dates.

<p align="center">
Login attempts on specific dates: <br/>
<img src="https://i.imgur.com/KAl9AkG.jpg" height="80%" width="80%" alt="SQL Filters"/>

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I started by selecting all data from the log_in_attempts. Then, I used a WHERE clause with an OR operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for logins on 2022-05-08.

<h2>Retrieve login attempts outside of Mexico </h2>

After investigating the organization’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico.

<p align="center">
Login attempts outside of Mexico: <br/>
<img src="https://i.imgur.com/CrQvyps.png" height="80%" width="80%" alt="SQL Filters"/>

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with NOT to filter for countries other than Mexico. I used LIKE with MEX% as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any number of unspecified characters when used with LIKE.

<h2>Retrieve employees in Marketing </h2>

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Marketing department in the East building.

<p align="center">
Employees in Marketing east building: <br/>
<img src="https://i.imgur.com/P0snS3H.png" height="80%" width="80%" alt="SQL Filters"/>

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Marketing department in the East building. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with AND to filter for employees who work in the Marketing department and in the East building. I used LIKE with East% as the pattern to match because the data in the office column represents the East building with the specific office number. The first condition is the department = 'Marketing' portion, which filters for employees in the Marketing department. The second condition is the office LIKE 'East%' portion, which filters for employees in the East building.

<h2>Retrieve all employees not in IT </h2>

The following demonstrates how I created a SQL query to filter for employee machines from employees not in the Information Technology department.

<p align="center">
All employees not in IT: <br/>
<img src="https://i.imgur.com/7AD8xFT.png" height="80%" width="80%" alt="SQL Filters"/>

The first part of the screenshot is my query, and the second part is a portion of the output. The query returns all employees not in the Information Technology department. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with NOT to filter for employees not in this department.

<h2>Employees in Finance or Sales </h2>

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments.

<p align="center">
Employees in Finance or Sales: <br/>
<img src="https://i.imgur.com/bHcs5w5.png" height="80%" width="80%" alt="SQL Filters"/>

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Finance and Sales departments. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with OR to filter for employees who are in the Finance and Sales departments. I used the OR operator instead of AND because I want all employees who are in either department. The first condition is department = 'Finance', which filters for employees from the Finance department. The second condition is department = 'Sales', which filters for employees from the Sales department.

