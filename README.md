<h1>SQL Query Filters</h1>


<h2>Scenario</h2>
You are a security professional at a large organization. Part of your job is to investigate security issues to help keep the system secure. You recently discovered some potential security issues that involve login attempts and employee machines.
<br />
<br/>
Your task is to examine the organization’s data in their employees and log_in_attempts tables. You’ll need to use SQL filters to retrieve records from different datasets and investigate the potential security issues.

<h2>Program walk-through:</h2>

<p align="center">
<b>Retrieve After Hours Failed Login Attempts</b> <br/>
There was a potential security incident that occurred after business hours (after 18:00). All after hours login attempts that failed need to be investigated.
<br />
<br />
The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours. 
<br />
<br />
<img src="https://imgur.com/7mX3X94.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The first part of the screensot is my  query, and the second part is a portion of the output. This query filters for failed login attempts that occurred after 18:00. First, I started by selecting all data from the <b><i>log_in_attempts</i></b> table. Then, I used a <b><i>WHERE</i></b> clause with an <b><i>AND</i></b> operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is <b><i>login_time > '18:00'</i></b>, which filters for the login attempts that occurred after 18:00. The second condition is <b><i>success = FALSE</i></b>, which filters for the failed login attempts. 
<br />
<br />
<b>Retrieve Login Attempts on Specific Dates</b>  <br/>
A suspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before needs to be investigated.
<br />
<br />
The following code demonstrates how I created a SQL query to filter for login attempts that occurred on specific dates.
<br />
<br />
<img src="https://imgur.com/S95VlmA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I started by selecting all data from the <b><i>log_in_attempts</i></b> table. Then, I used a <b><i>WHERE</i></b> clause with an <b><i>OR</i></b> operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is <b><i>login_date = '2022-05-09'</i></b>, which filters for logins on 2022-05-09. The second condition is <b><i>login_date = '2022-05-08'</i></b>, which filters for logins on 2022-05-08.
<br />
<br />
<b>Retrieve Login Attempts Outside of Mexico:</b> <br/>
After investigating the organization’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.
<br />
<br />
The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico. 
<img src="https://imgur.com/f6WJBOZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the <b><i>log_in_attempts</i></b> table. Then, I used a <b><i>WHERE</i></b> clause with <b><i>NOT</i></b> to filter for countries other than Mexico. I used <b><i>LIKE</i></b> with <b><i>MEX%</i></b> as the pattern to match because the dataset represents Mexico as <b><i>MEX</i></b> and <b><i>MEXICO</i></b>. The percentage sign <b><i>(%)</i></b> represents any number of unspecified characters when used with <b><i>LIKE</i></b>. 
<br />
<br />
<b>Retrieve Employees in Marketing:</b>  <br/>
My team wants to update the computers for certain employees in the Marketing department. To do this, I have to get information on which employee machines to update.
<br />
<br />
The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Marketing department in the East building.
<br />
<img src="https://imgur.com/pWr7Gmw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Marketing department in the East building. First, I started by selecting all data from the <b><i>employees</i></b> table. Then, I used a <b><i>WHERE</i></b> clause with <b><i>AND</i></b> to filter for employees who work in the Marketing department and in the East building. I used <b><i>LIKE</i></b> with <b><i>East%</i></b> as the pattern to match because the data in the <b><i>office</i></b> column represents the East building with the specific office number. The first condition is <b><i>department = 'Marketing'</i></b> portion, which filters for employees in the Marketing department. The second condition is the <b><i>office LIKE 'East%'</i></b> portion, which filters for employees in teh East building
<br />
<br />
<b>Retrieve Employees in Finance or Sales</b>  <br/>
The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments.
<br />
<br />
The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments.
<br />
<img src="https://imgur.com/vqbRnO0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Finance and Sales departments. First, I started by selecting all data from the <b><i>employees</i></b> table. Then, I used a <b><i>WHERE</i></b> clause with <b><i>OR</i></b> to filter for employees who are in the Finance and Sales departments. I used the <b><i>OR</i></b> operator instead of <b><i>AND</i></b> because I want all employees who are in either department. The first condition is <b><i>department = 'Finance'</i></b>, which filters for employees from the Finance department. The second condition is <b><i>department = 'Sales'</i></b>, which filters for employees from the Sales department.
<br />
<br />
<b>Retrieve All Employees Not in IT</b>  <br/>
My team needs to make one more security update on employees who are not in the Information Technology department. To make the update, I first have to get information on these employees.
<br />
<br />
The following demonstrates how I created a SQL query to filter for employee machines from employees not in the  Information Technology department.
<br />
<img src="https://imgur.com/2R1dZCw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The first part of the screenshot is my query, and second part is a portion of the output. The query returns all employees not in the Information Technology department. First, I started by selecting all data from the <b><i>employees</i></b> table. Then, I used a <b><i>WHERE</i></b> clause with <b><i>NOT</i></b> to filter for employees not in this department
<br />
<br />
<h2>Summary:</h2>
I applied filters to SQL queries to get specific information on login attempts and employee machines. I used two different tables, <b><i>log_in_attempts</i></b> and <b><i>employees</i></b>. I used <b><i>AND</i></b>, <b><i>OR</i></b>, and <b><i>NOT</i></b> operators to filter for the specific information needed for each task. I also used <b><i>LIKE</i></b> and the percentage sign <b><i>(%)</i></b> wildcard to filter for patterns.
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
