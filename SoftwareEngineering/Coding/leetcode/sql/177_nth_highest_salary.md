# Nth Highest Salary

## Description
Write a SQL query to get the nth highest salary from the Employee table.
```
+----+--------+
| Id | Salary |
+----+--------+
| 1  | 100    |
| 2  | 200    |
| 3  | 300    |
+----+--------+
```
For example, given the above Employee table, the nth highest salary where n = 2 is 200. If there is no nth highest salary, then the query should return null.
```
+------------------------+
| getNthHighestSalary(2) |
+------------------------+
| 200                    |
+------------------------+
```

## Optimal solution
- Code
```
CREATE FUNCTION getNthHighestSalary(N INT) RETURNS INT
BEGIN
    SET N = N-1;
  RETURN (
      # Write your MySQL query statement below.
      SELECT DISTINCT
            Salary
      FROM
            Employee
      ORDER BY 
            Salary DESC
      LIMIT
            1
      OFFSET
            M
  );
END
```
- Performance
  - Runtime: 167 ms, faster than 98.89% of MySQL online submissions for Nth Highest Salary.
  - Memory Usage: 0B, less than 100.00% of MySQL online submissions for Nth Highest Salary.