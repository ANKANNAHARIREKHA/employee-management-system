SQL
CREATE TABLE employees (
  emp_id NUMBER PRIMARY KEY,
  emp_name VARCHAR2(50),
  department VARCHAR2(50),
  salary NUMBER,
  join_date DATE
);SQL
INSERT INTO departments VALUES (1, 'IT');
INSERT INTO departments VALUES (2, 'HR');
SQL
INSERT INTO employees VALUES (101, 'Ravi', 'IT', 30000, SYSDATE);
INSERT INTO employees VALUES (102, 'Sita', 'HR', 25000, SYSDATE);
SQL
SELECT * FROM employees;
SQL
SELECT e.emp_name, d.dept_name
FROM employees e
JOIN departments d
ON e.department = d.dept_name;
SQL
SELECT * FROM employees WHERE salary > 25000;
SQL
CREATE OR REPLACE PROCEDURE update_salary(
  p_emp_id NUMBER,
  p_salary NUMBER
)
AS
BEGIN
  UPDATE employees
  SET salary = p_salary
  WHERE emp_id = p_emp_id;

  DBMS_OUTPUT.PUT_LINE('Salary Updated');
END;SQL
SQL
SELECT * FROM employees;BEGIN
  update_salary(101, 50000);
END;
