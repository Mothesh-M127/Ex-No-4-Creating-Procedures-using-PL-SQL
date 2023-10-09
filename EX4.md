# Ex. No: 4 Creating Procedures using PL/SQL

### AIM: 
    To create a procedure using PL/SQL.

### Algorithm:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a procedure named as insert_employee data.
3. Inside the procdure block, write the query for inserting the values into the employee table.
4. End the procedure.
5. Call the insert_employee data procedure to insert the values into the employee table.
6. Display the employee table

### Program:
CREATE OR REPLACE PROCEDURE insert_employee_data AS 
BEGIN

	INSERT INTO employee(empid, empname, dept, salary)
	VALUES (1,'mani', 'HR', 50000);

	INSERT INTO employee (empid, empname, dept, salary)
	VALUES (2, 'JEEVI' , 'IT', 60000);

	INSERT INTO employee (empid, empname, dept, salary)
	VALUES (3, 'JEEVAkumar' , 'FINANCE', 55000);

	COMMIT;

	FOR emp_rec IN (SELECT * FROM employee) LOOP
		DBMS_OUTPUT.PUT_LINE('Employee ID:' || emp_rec.empid || ', Employee Name:' || emp_rec.empname || ', Department:' || 	emp_rec.dept || ', Salary:' || emp_rec.salary);
	END LOOP;
END;
/
### Output:

### Result:
    Thus, procedure is created using PL/SQL.