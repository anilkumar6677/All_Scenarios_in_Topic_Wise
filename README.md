# All_Scenarios_in_Topic_Wise

⚡ Simple Transformation Scenarios

🔹 Scenario 1 — Select Specific Columns

Input DataFrame
```
+--------+--------+--------+--------+
| emp_id | name   | dept   | salary |
+--------+--------+--------+--------+
| 1      | Amit   | IT     | 70000  |
| 2      | Riya   | HR     | 90000  |
| 3      | Karan  | IT     | 65000  |
+--------+--------+--------+--------+
```
Transformation

Select only name and salary.

Output
```
+--------+--------+
| name   | salary |
+--------+--------+
| Amit   | 70000  |
| Riya   | 90000  |
| Karan  | 65000  |
+--------+--------+
```
🔹 Scenario 2 — Filter Rows

Input DataFrame
```
+--------+--------+--------+--------+
| emp_id | name   | dept   | salary |
+--------+--------+--------+--------+
| 1      | Amit   | IT     | 70000  |
| 2      | Riya   | HR     | 90000  |
| 3      | Karan  | IT     | 65000  |
+--------+--------+--------+--------+
```
Transformation

Filter employees with salary > 70000.

Output
```
+--------+--------+--------+--------+
| emp_id | name   | dept   | salary |
+--------+--------+--------+--------+
| 2      | Riya   | HR     | 90000  |
+--------+--------+--------+--------+
```
🔹 Scenario 3 — Add New Column

Input DataFrame
```
+--------+--------+--------+
| emp_id | name   | salary |
+--------+--------+--------+
| 1      | Amit   | 70000  |
| 2      | Riya   | 90000  |
| 3      | Karan  | 65000  |
+--------+--------+--------+
```
Transformation

Add a new column bonus = salary * 0.1.

Output
```
+--------+--------+--------+-------+
| emp_id | name   | salary | bonus |
+--------+--------+--------+-------+
| 1      | Amit   | 70000  | 7000  |
| 2      | Riya   | 90000  | 9000  |
| 3      | Karan  | 65000  | 6500  |
+--------+--------+--------+-------+
```
🔹 Scenario 4 — Group By and Aggregate

Input DataFrame
```
+--------+--------+--------+
| emp_id | dept   | salary |
+--------+--------+--------+
| 1      | IT     | 70000  |
| 2      | HR     | 90000  |
| 3      | IT     | 65000  |
| 4      | HR     | 85000  |
+--------+--------+--------+
```
Transformation

Group by dept and compute total salary.

Output
```
+--------+------------+
| dept   | total_salary|
+--------+------------+
| IT     | 135000     |
| HR     | 175000     |
+--------+------------+
```
🔹 Scenario 5 — Rename Column

Input DataFrame
```
+--------+--------+--------+
| emp_id | name   | salary |
+--------+--------+--------+
| 1      | Amit   | 70000  |
| 2      | Riya   | 90000  |
+--------+--------+--------+
```
Transformation

Rename salary → monthly_salary.

Output
```
+--------+--------+---------------+
| emp_id | name   | monthly_salary|
+--------+--------+---------------+
| 1      | Amit   | 70000         |
| 2      | Riya   | 90000         |
+--------+--------+---------------+
```




🔥 Scenario 1 — Inner Join: Employees With Matching Departments

📘 Description

Perform an inner join to return only employees who have a matching department in the department table.

🔹 Input: employees
```
+--------+--------+--------+
| emp_id | name   | dept_id|
+--------+--------+--------+
| 1      | Amit   | 10     |
| 2      | Riya   | 20     |
| 3      | Karan  | 30     |
+--------+--------+--------+
```
🔹 Input: departments
```
+--------+-------------+
| dept_id| dept_name   |
+--------+-------------+
| 10     | IT          |
| 20     | HR          |
+--------+-------------+
```
🔹 Output
```
+--------+--------+--------+-------------+
| emp_id | name   | dept_id| dept_name   |
+--------+--------+--------+-------------+
| 1      | Amit   | 10     | IT          |
| 2      | Riya   | 20     | HR          |
+--------+--------+--------+-------------+
```
🔥 Scenario 2 — Left Join: Employees Without Departments

📘 Description

Find all employees and attach department names where available.
Employees without a department should show NULL.

🔹 Input: employees
```
+--------+--------+--------+
| emp_id | name   | dept_id|
+--------+--------+--------+
| 1      | Amit   | 10     |
| 2      | Riya   | 20     |
| 3      | Karan  | 30     |
+--------+--------+--------+
```
🔹 Input: departments
```
+--------+-------------+
| dept_id| dept_name   |
+--------+-------------+
| 10     | IT          |
| 20     | HR          |
+--------+-------------+
```

🔹 Output
```
+--------+--------+--------+-------------+
| emp_id | name   | dept_id| dept_name   |
+--------+--------+--------+-------------+
| 1      | Amit   | 10     | IT          |
| 2      | Riya   | 20     | HR          |
| 3      | Karan  | 30     | NULL        |
+--------+--------+--------+-------------+
```
🔥 Scenario 3 — Right Join: All Departments Even Without Employees

📘 Description

Return every department, even if no employee belongs to it.

🔹 Input: employees
```
+--------+--------+--------+
| emp_id | name   | dept_id|
+--------+--------+--------+
| 1      | Amit   | 10     |
| 2      | Riya   | 20     |
+--------+--------+--------+
```
🔹 Input: departments
```
+--------+-------------+
| dept_id| dept_name   |
+--------+-------------+
| 10     | IT          |
| 20     | HR          |
| 30     | Finance     |
+--------+-------------+
```
🔹 Output
```
+--------+--------+--------+-------------+
| emp_id | name   | dept_id| dept_name   |
+--------+--------+--------+-------------+
| 1      | Amit   | 10     | IT          |
| 2      | Riya   | 20     | HR          |
| NULL   | NULL   | 30     | Finance     |
+--------+--------+--------+-------------+
```
🔥 Scenario 4 — Full Outer Join: All Employees & All Departments

📘 Description

Return every employee and every department.
Missing matches should show NULL on either side.

🔹 Input: employees
```
+--------+--------+--------+
| emp_id | name   | dept_id|
+--------+--------+--------+
| 1      | Amit   | 10     |
| 2      | Riya   | 20     |
| 3      | Karan  | 30     |
+--------+--------+--------+
```
🔹 Input: departments
```
+--------+-------------+
| dept_id| dept_name   |
+--------+-------------+
| 10     | IT          |
| 20     | HR          |
| 40     | Support     |
+--------+-------------+
```
🔹 Output
```
+--------+--------+--------+-------------+
| emp_id | name   | dept_id| dept_name   |
+--------+--------+--------+-------------+
| 1      | Amit   | 10     | IT          |
| 2      | Riya   | 20     | HR          |
| 3      | Karan  | 30     | NULL        |
| NULL   | NULL   | 40     | Support     |
+--------+--------+--------+-------------+
```
🔥 Scenario 5 — Anti Join: Employees Without Matching Department

📘 Description

Find employees whose department is not present in the department table.

🔹 Input: employees
```
+--------+--------+--------+
| emp_id | name   | dept_id|
+--------+--------+--------+
| 1      | Amit   | 10     |
| 2      | Riya   | 20     |
| 3      | Karan  | 30     |
+--------+--------+--------+
```
🔹 Input: departments
```
+--------+-------------+
| dept_id| dept_name   |
+--------+-------------+
| 10     | IT          |
| 20     | HR          |
+--------+-------------+
```
🔹 Output
```
+--------+--------+--------+
| emp_id | name   | dept_id|
+--------+--------+--------+
| 3      | Karan  | 30     |
+--------+--------+--------+
```

🔥 Scenario 6 — Semi Join: Employees With Existing Departments Only

📘 Description

A semi join returns rows from the left table (employees) that have matching rows in the right table (departments).
Unlike inner join, it does not include columns from the right table.

🔹 Input: employees
```
+--------+--------+--------+
| emp_id | name   | dept_id|
+--------+--------+--------+
| 1      | Amit   | 10     |
| 2      | Riya   | 20     |
| 3      | Karan  | 30     |
+--------+--------+--------+
```
🔹 Input: departments
```
+--------+-------------+
| dept_id| dept_name   |
+--------+-------------+
| 10     | IT          |
| 20     | HR          |
+--------+-------------+
```
🔹 Output
```
+--------+--------+--------+
| emp_id | name   | dept_id|
+--------+--------+--------+
| 1      | Amit   | 10     |
| 2      | Riya   | 20     |
+--------+--------+--------+
```
🔥 Scenario 7 — Cross Join: Cartesian Product of Employees and Departments

📘 Description

A cross join returns all possible combinations of rows from both tables.
Useful for generating all pairings.

🔹 Input: employees
```
+--------+--------+
| emp_id | name   |
+--------+--------+
| 1      | Amit   |
| 2      | Riya   |
+--------+--------+
```
🔹 Input: departments
```
+--------+-------------+
| dept_id| dept_name   |
+--------+-------------+
| 10     | IT          |
| 20     | HR          |
+--------+-------------+
```
🔹 Output
```
+--------+--------+--------+-------------+
| emp_id | name   | dept_id| dept_name   |
+--------+--------+--------+-------------+
| 1      | Amit   | 10     | IT          |
| 1      | Amit   | 20     | HR          |
| 2      | Riya   | 10     | IT          |
| 2      | Riya   | 20     | HR          |
+--------+--------+--------+-------------+
```
🔥 Scenario 8 — Self Join: Employees and Their Managers

📘 Description

A self join is when a table joins with itself.
In this example, we assume employees have a manager_id pointing to another employee.

🔹 Input: employees
```
+--------+--------+-----------+
| emp_id | name   | manager_id|
+--------+--------+-----------+
| 1      | Amit   | 3         |
| 2      | Riya   | 3         |
| 3      | Karan  | NULL      |
+--------+--------+-----------+
```
🔹 Output
```
+--------+--------+-----------+--------+
| emp_id | name   | manager_id| manager|
+--------+--------+-----------+--------+
| 1      | Amit   | 3         | Karan  |
| 2      | Riya   | 3         | Karan  |
| 3      | Karan  | NULL      | NULL   |
+--------+--------+-----------+--------+
```



🪟 Window Functions — Complete Scenarios

🔥 Scenario 1 — Row Number: Employees Ordered by Salary

📘 Description

Assign a unique row number to each employee ordered by salary.

🔹 Input: employees
```
+--------+--------+--------+
| emp_id | name   | salary |
+--------+--------+--------+
| 1      | Amit   | 70000  |
| 2      | Riya   | 90000  |
| 3      | Karan  | 65000  |
| 4      | Sohan  | 85000  |
+--------+--------+--------+
```
🔹 Output
```
+--------+--------+--------+-----------+
| emp_id | name   | salary | row_number|
+--------+--------+--------+-----------+
| 3      | Karan  | 65000  | 1         |
| 1      | Amit   | 70000  | 2         |
| 4      | Sohan  | 85000  | 3         |
| 2      | Riya   | 90000  | 4         |
+--------+--------+--------+-----------+
```
🔥 Scenario 2 — Rank: Employees Ordered by Salary

📘 Description

Assign a rank; ties get the same rank, but gaps are created in ranks for duplicates.

🔹 Input: employees
```
+--------+--------+--------+
| emp_id | name   | salary |
+--------+--------+--------+
| 1      | Amit   | 70000  |
| 2      | Riya   | 90000  |
| 3      | Karan  | 70000  |
| 4      | Sohan  | 85000  |
+--------+--------+--------+
```
🔹 Output
```
+--------+--------+--------+------+
| emp_id | name   | salary | rank |
+--------+--------+--------+------+
| 1      | Amit   | 70000  | 1    |
| 3      | Karan  | 70000  | 1    |
| 4      | Sohan  | 85000  | 3    |
| 2      | Riya   | 90000  | 4    |
+--------+--------+--------+------+
```
🔥 Scenario 3 — Dense Rank: Employees Ordered by Salary

📘 Description

Assign a dense rank; ties get the same rank but no gaps are created in rank sequence.

🔹 Input: employees
```
+--------+--------+--------+
| emp_id | name   | salary |
+--------+--------+--------+
| 1      | Amit   | 70000  |
| 2      | Riya   | 90000  |
| 3      | Karan  | 70000  |
| 4      | Sohan  | 85000  |
+--------+--------+--------+
```
🔹 Output
```
+--------+--------+--------+-----------+
| emp_id | name   | salary | dense_rank|
+--------+--------+--------+-----------+
| 1      | Amit   | 70000  | 1         |
| 3      | Karan  | 70000  | 1         |
| 4      | Sohan  | 85000  | 2         |
| 2      | Riya   | 90000  | 3         |
+--------+--------+--------+-----------+
```
🔥 Scenario 4 — Lag Function: Previous Month Sales

📘 Description

Retrieve the previous row value for each employee’s salary (or sales).

🔹 Input: sales
```
+--------+-------+
| month  | sales |
+--------+-------+
| Jan    | 1000  |
| Feb    | 2000  |
| Mar    | 3000  |
| Apr    | 4000  |
+--------+-------+
```
🔹 Output
```
+--------+-------+------+
| month  | sales | lag  |
+--------+-------+------+
| Jan    | 1000  | NULL |
| Feb    | 2000  | 1000 |
| Mar    | 3000  | 2000 |
| Apr    | 4000  | 3000 |
+--------+-------+------+
```
🔥 Scenario 5 — Lead Function: Next Month Sales

📘 Description

Retrieve the next row value for each employee’s salary (or sales).

🔹 Input: sales
```
+--------+-------+
| month  | sales |
+--------+-------+
| Jan    | 1000  |
| Feb    | 2000  |
| Mar    | 3000  |
| Apr    | 4000  |
+--------+-------+
```
🔹 Output
```
+--------+-------+------+
| month  | sales | lead |
+--------+-------+------+
| Jan    | 1000  | 2000 |
| Feb    | 2000  | 3000 |
| Mar    | 3000  | 4000 |
| Apr    | 4000  | NULL |
+--------+-------+------+
```
🔥 Scenario 6 — NTILE: Divide Employees into 3 Buckets by Salary

📘 Description

Assign employees to N buckets based on salary.

🔹 Input: employees
```
+--------+--------+--------+
| emp_id | name   | salary |
+--------+--------+--------+
| 1      | Amit   | 70000  |
| 2      | Riya   | 90000  |
| 3      | Karan  | 65000  |
| 4      | Sohan  | 85000  |
| 5      | Neha   | 75000  |
+--------+--------+--------+
```
🔹 Output
```
+--------+--------+--------+-------+
| emp_id | name   | salary | ntile |
+--------+--------+--------+-------+
| 3      | Karan  | 65000  | 1     |
| 1      | Amit   | 70000  | 1     |
| 5      | Neha   | 75000  | 2     |
| 4      | Sohan  | 85000  | 2     |
| 2      | Riya   | 90000  | 3     |
+--------+--------+--------+-------+
```
🔥 Scenario 7 — Percent Rank: Employees by Salary

📘 Description

Calculate percent rank of employees by salary (value between 0 and 1).

🔹 Input: employees
```
+--------+--------+--------+
| emp_id | name   | salary |
+--------+--------+--------+
| 1      | Amit   | 70000  |
| 2      | Riya   | 90000  |
| 3      | Karan  | 65000  |
| 4      | Sohan  | 85000  |
+--------+--------+--------+
```
🔹 Output
```
+--------+--------+--------+-------------+
| emp_id | name   | salary | percent_rank|
+--------+--------+--------+-------------+
| 3      | Karan  | 65000  | 0.0         |
| 1      | Amit   | 70000  | 0.3333      |
| 4      | Sohan  | 85000  | 0.6667      |
| 2      | Riya   | 90000  | 1.0         |
+--------+--------+--------+-------------+
```
🔥 Scenario 8 — Moving Average: 3-Month Cumulative Sales

📘 Description

Compute a 3-month moving average using a window function.

🔹 Input: sales
```
+--------+-------+
| month  | sales |
+--------+-------+
| Jan    | 1000  |
| Feb    | 2000  |
| Mar    | 3000  |
| Apr    | 4000  |
| May    | 5000  |
+--------+-------+
```
🔹 Output
```
+--------+-------+----------------+
| month  | sales | moving_average |
+--------+-------+----------------+
| Jan    | 1000  | 1000           |
| Feb    | 2000  | 1500           |
| Mar    | 3000  | 2000           |
| Apr    | 4000  | 3000           |
| May    | 5000  | 4000           |
+--------+-------+----------------+
```


📊 Aggregations — Complete Scenarios

🔥 Scenario 1 — Sum and Count: Total Salary per Department

📘 Description

Calculate total salary and count of employees per department.

🔹 Input: employees
```
+--------+--------+--------+--------+
| emp_id | name   | dept   | salary |
+--------+--------+--------+--------+
| 1      | Amit   | IT     | 70000  |
| 2      | Riya   | HR     | 90000  |
| 3      | Karan  | IT     | 65000  |
| 4      | Sohan  | HR     | 85000  |
| 5      | Neha   | IT     | 75000  |
+--------+--------+--------+--------+
```
🔹 Output
```
+--------+------------+-------+
| dept   | total_salary | count|
+--------+------------+-------+
| IT     | 210000     | 3     |
| HR     | 175000     | 2     |
+--------+------------+-------+
```
🔥 Scenario 2 — Average and Max: Salary per Department

📘 Description

Calculate average and maximum salary per department.

🔹 Input: employees
```
+--------+--------+--------+--------+
| emp_id | name   | dept   | salary |
+--------+--------+--------+--------+
| 1      | Amit   | IT     | 70000  |
| 2      | Riya   | HR     | 90000  |
| 3      | Karan  | IT     | 65000  |
| 4      | Sohan  | HR     | 85000  |
| 5      | Neha   | IT     | 75000  |
+--------+--------+--------+--------+
```
🔹 Output
```
+--------+-------------+-----------+
| dept   | avg_salary  | max_salary|
+--------+-------------+-----------+
| IT     | 70000       | 75000     |
| HR     | 87500       | 90000     |
+--------+-------------+-----------+
```
🔥 Scenario 3 — Count Distinct: Unique Departments

📘 Description

Count the distinct departments in the employee table.

🔹 Input: employees
```
+--------+--------+--------+
| emp_id | name   | dept   |
+--------+--------+--------+
| 1      | Amit   | IT     |
| 2      | Riya   | HR     |
| 3      | Karan  | IT     |
| 4      | Sohan  | HR     |
| 5      | Neha   | Finance|
+--------+--------+--------+
```
🔹 Output
```
+-------------------+
| distinct_dept_cnt |
+-------------------+
| 3                 |
+-------------------+
```
🔥 Scenario 4 — Cube: Salary Aggregation by Dept and Location

📘 Description

Use cube to aggregate salary across multiple dimensions (dept, location).

🔹 Input: employees
```
+--------+--------+--------+----------+--------+
| emp_id | name   | dept   | location | salary |
+--------+--------+--------+----------+--------+
| 1      | Amit   | IT     | NY       | 70000  |
| 2      | Riya   | HR     | NY       | 90000  |
| 3      | Karan  | IT     | SF       | 65000  |
| 4      | Sohan  | HR     | SF       | 85000  |
+--------+--------+--------+----------+--------+
```
🔹 Output
```
+--------+----------+------------+
| dept   | location | total_salary|
+--------+----------+------------+
| IT     | NY       | 70000      |
| IT     | SF       | 65000      |
| HR     | NY       | 90000      |
| HR     | SF       | 85000      |
| IT     | NULL     | 135000     |
| HR     | NULL     | 175000     |
| NULL   | NY       | 160000     |
| NULL   | SF       | 150000     |
| NULL   | NULL     | 310000     |
+--------+----------+------------+
```
🔥 Scenario 5 — Rollup: Salary by Dept then Total

📘 Description

Use rollup to calculate salary by department and overall total.

🔹 Input: employees
```
+--------+--------+--------+--------+
| emp_id | name   | dept   | salary |
+--------+--------+--------+--------+
| 1      | Amit   | IT     | 70000  |
| 2      | Riya   | HR     | 90000  |
| 3      | Karan  | IT     | 65000  |
| 4      | Sohan  | HR     | 85000  |
+--------+--------+--------+--------+
```
🔹 Output
```
+--------+------------+
| dept   | total_salary|
+--------+------------+
| IT     | 135000     |
| HR     | 175000     |
| NULL   | 310000     |
+--------+------------+
```
🔥 Scenario 6 — Approx Count Distinct: Approximate Unique Employees

📘 Description

Use approx_count_distinct for fast distinct count estimation.

🔹 Input: employees
```
+--------+--------+--------+
| emp_id | name   | dept   |
+--------+--------+--------+
| 1      | Amit   | IT     |
| 2      | Riya   | HR     |
| 3      | Karan  | IT     |
| 4      | Sohan  | HR     |
| 5      | Neha   | IT     |
+--------+--------+--------+
```
🔹 Output
```
+---------------------------+
| approx_distinct_emp_count |
+---------------------------+
| 5                         |
+---------------------------+
```
🔥 Scenario 7 — Min/Max Salary per Dept

📘 Description

Compute minimum and maximum salary per department.

🔹 Input: employees
```
+--------+--------+--------+--------+
| emp_id | name   | dept   | salary |
+--------+--------+--------+--------+
| 1      | Amit   | IT     | 70000  |
| 2      | Riya   | HR     | 90000  |
| 3      | Karan  | IT     | 65000  |
| 4      | Sohan  | HR     | 85000  |
+--------+--------+--------+--------+
```
🔹 Output
```
+--------+-----------+-----------+
| dept   | min_salary| max_salary|
+--------+-----------+-----------+
| IT     | 65000     | 70000     |
| HR     | 85000     | 90000     |
+--------+-----------+-----------+
```
🔥 Scenario 8 — Group By with Filter: Salary > 70000 per Dept

📘 Description

Aggregate salary per department only for employees earning > 70000.

🔹 Input: employees
```
+--------+--------+--------+--------+
| emp_id | name   | dept   | salary |
+--------+--------+--------+--------+
| 1      | Amit   | IT     | 70000  |
| 2      | Riya   | HR     | 90000  |
| 3      | Karan  | IT     | 65000  |
| 4      | Sohan  | HR     | 85000  |
| 5      | Neha   | IT     | 75000  |
+--------+--------+--------+--------+
```
🔹 Output
```
+--------+------------+
| dept   | total_salary|
+--------+------------+
| IT     | 75000      |
| HR     | 175000     |
+--------+------------+
```


🕒 Date/Time Logic — Complete Scenarios

🔥 Scenario 1 — Extract Year, Month, Day from Date

📘 Description

Extract year, month, and day from a timestamp column.

🔹 Input: employees
```
+--------+--------+-------------------+
| emp_id | name   | joining_date      |
+--------+--------+-------------------+
| 1      | Amit   | 2014-02-20 09:00:00 |
| 2      | Riya   | 2014-06-11 09:00:00 |
| 3      | Karan  | 2015-03-15 10:30:00 |
+--------+--------+-------------------+
```
🔹 Output
```
+--------+--------+------+-------+---+
| emp_id | name   | year | month | day|
+--------+--------+------+-------+---+
| 1      | Amit   | 2014 | 2     | 20|
| 2      | Riya   | 2014 | 6     | 11|
| 3      | Karan  | 2015 | 3     | 15|
+--------+--------+------+-------+---+
```
🔥 Scenario 2 — Date Difference: Days Between Joining Dates

📘 Description

Calculate the difference in days between two dates.

🔹 Input: employees
```
+--------+--------+-------------------+
| emp_id | name   | joining_date      |
+--------+--------+-------------------+
| 1      | Amit   | 2014-02-20        |
| 2      | Riya   | 2014-06-11        |
| 3      | Karan  | 2015-03-15        |
+--------+--------+-------------------+
```
🔹 Output (difference in days from first employee)
```
+--------+--------+-------------------+-------------+
| emp_id | name   | joining_date      | days_diff   |
+--------+--------+-------------------+-------------+
| 1      | Amit   | 2014-02-20        | 0           |
| 2      | Riya   | 2014-06-11        | 111         |
| 3      | Karan  | 2015-03-15        | 388         |
+--------+--------+-------------------+-------------+
```
🔥 Scenario 3 — Add/Subtract Days/Months: Calculate Probation End Date

📘 Description

Add 3 months to joining date to calculate probation end date.

🔹 Input: employees
```
+--------+--------+-------------------+
| emp_id | name   | joining_date      |
+--------+--------+-------------------+
| 1      | Amit   | 2014-02-20        |
| 2      | Riya   | 2014-06-11        |
| 3      | Karan  | 2015-03-15        |
+--------+--------+-------------------+
```
🔹 Output
```
+--------+--------+-------------------+-------------------+
| emp_id | name   | joining_date      | probation_end_date|
+--------+--------+-------------------+-------------------+
| 1      | Amit   | 2014-02-20        | 2014-05-20        |
| 2      | Riya   | 2014-06-11        | 2014-09-11        |
| 3      | Karan  | 2015-03-15        | 2015-06-15        |
+--------+--------+-------------------+-------------------+
```
🔥 Scenario 4 — Current Timestamp: Mark Data Ingestion Time

📘 Description

Add a column with current timestamp to record ingestion time.

🔹 Input: employees
```
+--------+--------+
| emp_id | name   |
+--------+--------+
| 1      | Amit   |
| 2      | Riya   |
| 3      | Karan  |
+--------+--------+
```
🔹 Output
```
+--------+--------+-----------------------+
| emp_id | name   | ingestion_time        |
+--------+--------+-----------------------+
| 1      | Amit   | 2025-12-12 12:00:00  |
| 2      | Riya   | 2025-12-12 12:00:00  |
| 3      | Karan  | 2025-12-12 12:00:00  |
+--------+--------+-----------------------+
```
(Timestamp is system current time when the query is run.)



🔥 Scenario 5 — Timezone Conversion: Convert UTC to IST

📘 Description

Convert timestamp from UTC to IST (+5:30 hours).

🔹 Input: employees
```
+--------+--------+-------------------+
| emp_id | name   | joining_date_utc  |
+--------+--------+-------------------+
| 1      | Amit   | 2014-02-20 09:00:00 |
| 2      | Riya   | 2014-06-11 09:00:00 |
+--------+--------+-------------------+
```
🔹 Output
```
+--------+--------+-------------------+-------------------+
| emp_id | name   | joining_date_utc  | joining_date_ist |
+--------+--------+-------------------+-------------------+
| 1      | Amit   | 2014-02-20 09:00:00 | 2014-02-20 14:30:00 |
| 2      | Riya   | 2014-06-11 09:00:00 | 2014-06-11 14:30:00 |
+--------+--------+-------------------+-------------------+
```
🔥 Scenario 6 — Extract Weekday: Find Day of the Week

📘 Description

Extract weekday name from joining date.

🔹 Input: employees
```
+--------+--------+-------------------+
| emp_id | name   | joining_date      |
+--------+--------+-------------------+
| 1      | Amit   | 2014-02-20        |
| 2      | Riya   | 2014-06-11        |
| 3      | Karan  | 2015-03-15        |
+--------+--------+-------------------+
```
🔹 Output
```
+--------+--------+-------------------+-----------+
| emp_id | name   | joining_date      | weekday   |
+--------+--------+-------------------+-----------+
| 1      | Amit   | 2014-02-20        | Thursday  |
| 2      | Riya   | 2014-06-11        | Wednesday |
| 3      | Karan  | 2015-03-15        | Sunday    |
+--------+--------+-------------------+-----------+
```
🔥 Scenario 7 — Unix Timestamp: Convert Date to Epoch Seconds

📘 Description

Convert a timestamp to Unix epoch seconds.

🔹 Input: employees
```
+--------+--------+-------------------+
| emp_id | name   | joining_date      |
+--------+--------+-------------------+
| 1      | Amit   | 2014-02-20 09:00:00 |
| 2      | Riya   | 2014-06-11 09:00:00 |
+--------+--------+-------------------+
```
🔹 Output
```
+--------+--------+-------------------+-----------+
| emp_id | name   | joining_date      | epoch_sec |
+--------+--------+-------------------+-----------+
| 1      | Amit   | 2014-02-20 09:00:00 | 1392877200 |
| 2      | Riya   | 2014-06-11 09:00:00 | 1402477200 |
+--------+--------+-------------------+-----------+

```


🛠 Complex Transformations — Complete Scenarios

🔥 Scenario 1 — Explode Array Column

📘 Description

Convert an array column into multiple rows using explode.

🔹 Input: employees
```
+--------+--------+----------------+
| emp_id | name   | skills         |
+--------+--------+----------------+
| 1      | Amit   | [Java, Spark]  |
| 2      | Riya   | [Python, SQL]  |
+--------+--------+----------------+
```
🔹 Output
```
+--------+--------+-------+
| emp_id | name   | skill |
+--------+--------+-------+
| 1      | Amit   | Java  |
| 1      | Amit   | Spark |
| 2      | Riya   | Python|
| 2      | Riya   | SQL   |
+--------+--------+-------+
```
🔥 Scenario 2 — Struct Column Extraction

📘 Description

Extract fields from a struct column into separate columns.

🔹 Input: employees
```
+--------+--------+--------------------------+
| emp_id | name   | address                  |
+--------+--------+--------------------------+
| 1      | Amit   | {city: "NY", zip: 10001}|
| 2      | Riya   | {city: "SF", zip: 94105}|
+--------+--------+--------------------------+
```
🔹 Output
```
+--------+--------+------+-------+
| emp_id | name   | city | zip   |
+--------+--------+------+-------+
| 1      | Amit   | NY   | 10001 |
| 2      | Riya   | SF   | 94105 |
+--------+--------+------+-------+
```
🔥 Scenario 3 — Map Column Lookup

📘 Description

Fetch values from a map column using a key.

🔹 Input: employees
```
+--------+--------+----------------------+
| emp_id | name   | contact              |
+--------+--------+----------------------+
| 1      | Amit   | {"email":"a@x.com", "phone":"123"}|
| 2      | Riya   | {"email":"r@y.com", "phone":"456"}|
+--------+--------+----------------------+
```
🔹 Output (extract email)
```
+--------+--------+------------+
| emp_id | name   | email      |
+--------+--------+------------+
| 1      | Amit   | a@x.com    |
| 2      | Riya   | r@y.com    |
+--------+--------+------------+
```
🔥 Scenario 4 — Pivot Table: Salary per Department

📘 Description

Pivot employees by department, show salary per employee.

🔹 Input: employees
```
+--------+--------+--------+
| emp_id | name   | dept   |
+--------+--------+--------+
| 1      | Amit   | IT     |
| 2      | Riya   | HR     |
| 3      | Karan  | IT     |
| 4      | Sohan  | HR     |
+--------+--------+--------+
```
🔹 Output
```
+--------+-----+-----+
| dept   | emp1| emp2|
+--------+-----+-----+
| IT     | Amit| Karan|
| HR     | Riya| Sohan|
+--------+-----+-----+
```
🔥 Scenario 5 — Unpivot Columns into Key-Value Pairs

📘 Description

Convert multiple columns into key-value rows using stack or melt.

🔹 Input: employees
```
+--------+--------+--------+--------+
| emp_id | name   | salary | bonus  |
+--------+--------+--------+--------+
| 1      | Amit   | 70000  | 5000   |
| 2      | Riya   | 90000  | 6000   |
+--------+--------+--------+--------+
```
🔹 Output
```
+--------+--------+------+-------+
| emp_id | name   | type | value |
+--------+--------+------+-------+
| 1      | Amit   | salary| 70000|
| 1      | Amit   | bonus | 5000 |
| 2      | Riya   | salary| 90000|
| 2      | Riya   | bonus | 6000 |
+--------+--------+------+-------+
```
🔥 Scenario 6 — JSON Column Parsing

📘 Description

Extract fields from a JSON string column.

🔹 Input: employees
```
+--------+--------+-----------------------------+
| emp_id | name   | json_data                   |
+--------+--------+-----------------------------+
| 1      | Amit   | {"city":"NY","zip":10001}  |
| 2      | Riya   | {"city":"SF","zip":94105}  |
+--------+--------+-----------------------------+
```
🔹 Output
```
+--------+--------+------+-------+
| emp_id | name   | city | zip   |
+--------+--------+------+-------+
| 1      | Amit   | NY   | 10001 |
| 2      | Riya   | SF   | 94105 |
+--------+--------+------+-------+
```
🔥 Scenario 7 — Nested Column Transformation

📘 Description

Flatten nested struct/array to multiple columns.

🔹 Input: employees
```
+--------+--------+--------------------------------+
| emp_id | name   | projects                       |
+--------+--------+--------------------------------+
| 1      | Amit   | [{"name":"Proj1","budget":1000},{"name":"Proj2","budget":2000}]|
| 2      | Riya   | [{"name":"Proj3","budget":1500}]|
+--------+--------+--------------------------------+
```
🔹 Output
```
+--------+--------+---------+--------+
| emp_id | name   | project | budget |
+--------+--------+---------+--------+
| 1      | Amit   | Proj1   | 1000   |
| 1      | Amit   | Proj2   | 2000   |
| 2      | Riya   | Proj3   | 1500   |
+--------+--------+---------+--------+

```


🌳 Complex DataFrame Schemas — Flattened printSchema Examples

🔥 Scenario 1 — Nested Structs

📘 Input DataFrame
```
root
 |-- emp_id: string (nullable = true)
 |-- name: string (nullable = true)
 |-- address: struct (nullable = true)
 |    |-- city: string (nullable = true)
 |    |-- state: string (nullable = true)
 |    |-- zip: integer (nullable = true)
```
🔹 Flattened Schema
```
root
 |-- emp_id: string (nullable = true)
 |-- name: string (nullable = true)
 |-- address_city: string (nullable = true)
 |-- address_state: string (nullable = true)
 |-- address_zip: integer (nullable = true)
```
🔥 Scenario 2 — Array of Structs

📘 Input DataFrame
```
root
 |-- emp_id: string (nullable = true)
 |-- name: string (nullable = true)
 |-- projects: array (nullable = true)
 |    |-- element: struct (containsNull = true)
 |    |    |-- name: string (nullable = true)
 |    |    |-- budget: integer (nullable = true)
```
🔹 Flattened Schema
```
root
 |-- emp_id: string (nullable = true)
 |-- name: string (nullable = true)
 |-- projects_name: string (nullable = true)
 |-- projects_budget: integer (nullable = true)
```
🔥 Scenario 3 — Map Column

📘 Input DataFrame
```
root
 |-- emp_id: string (nullable = true)
 |-- name: string (nullable = true)
 |-- contact: map (nullable = true)
 |    |-- key: string
 |    |-- value: string (valueContainsNull = true)
```
🔹 Flattened Schema
```
root
 |-- emp_id: string (nullable = true)
 |-- name: string (nullable = true)
 |-- contact_email: string (nullable = true)
 |-- contact_phone: string (nullable = true)
```
🔥 Scenario 4 — Multiple Nested Levels

📘 Input DataFrame
```
root
 |-- emp_id: string (nullable = true)
 |-- name: string (nullable = true)
 |-- dept: struct (nullable = true)
 |    |-- name: string (nullable = true)
 |    |-- manager: struct (nullable = true)
 |    |    |-- mgr_id: string (nullable = true)
 |    |    |-- mgr_name: string (nullable = true)
```
🔹 Flattened Schema
```
root
 |-- emp_id: string (nullable = true)
 |-- name: string (nullable = true)
 |-- dept_name: string (nullable = true)
 |-- dept_manager_mgr_id: string (nullable = true)
 |-- dept_manager_mgr_name: string (nullable = true)
```
🔥 Scenario 5 — JSON Column with Nested Fields

📘 Input DataFrame
```
root
 |-- emp_id: string (nullable = true)
 |-- name: string (nullable = true)
 |-- json_data: string (nullable = true)

```
(json_data example: {"address":{"city":"NY","zip":10001}, "skills":["Java","Spark"]})

🔹 Flattened Schema
```
root
 |-- emp_id: string (nullable = true)
 |-- name: string (nullable = true)
 |-- json_address_city: string (nullable = true)
 |-- json_address_zip: integer (nullable = true)
 |-- json_skills: array (nullable = true)
 |    |-- element: string (containsNull = true)
```







