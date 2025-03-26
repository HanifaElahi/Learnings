# Types of SQL

SQL (Structured Query Language) is used to interact with databases. It has different types of commands that help in managing and retrieving data efficiently. Here’s a simple breakdown with real-life examples:

---

## 1. Data Query Language (DQL)

- **Purpose:** Fetch data from the database.

- **Common Command:** `SELECT`

- **Example:**

  ```sql
  SELECT * FROM students WHERE grade = 'A';
  ```

  *Scenario:* A school administrator wants to see a list of students who scored an 'A' grade in their exams.

---

## 2. Data Definition Language (DDL)

- **Purpose:** Define and modify database structures.

- **Common Commands:** `CREATE`, `ALTER`, `DROP`, `TRUNCATE`

- **Example:**

  ```sql
  CREATE TABLE employees (
      id INT PRIMARY KEY, 
      name VARCHAR(50), 
      salary DECIMAL(10,2)
  );
  ```

  *Scenario:* A company is setting up a new HR system and needs to create a table to store employee records.

  ```sql
  ALTER TABLE employees ADD COLUMN department VARCHAR(50);
  ```

  *Scenario:* The company later decides to include employee department details in the table.

---

## 3. Data Manipulation Language (DML)

- **Purpose:** Modify data in tables.

- **Common Commands:** `INSERT`, `UPDATE`, `DELETE`

- **Example:**

  ```sql
  INSERT INTO employees (id, name, salary) VALUES (1, 'Alice', 50000);
  ```

  *Scenario:* A new employee, Alice, joins the company, and her details are added to the system.

  ```sql
  UPDATE employees SET salary = 55000 WHERE id = 1;
  ```

  *Scenario:* Alice gets a salary raise, so the HR team updates her record.

  ```sql
  DELETE FROM employees WHERE id = 1;
  ```

  *Scenario:* Alice resigns, and her record needs to be removed from the database.

---

## 4. Data Control Language (DCL)

- **Purpose:** Control user access to data.

- **Common Commands:** `GRANT`, `REVOKE`

- **Example:**

  ```sql
  GRANT SELECT ON employees TO user1;
  ```

  *Scenario:* A manager needs access to view employee details, so they are granted read-only permissions.

  ```sql
  REVOKE SELECT ON employees FROM user1;
  ```

  *Scenario:* The manager changes roles and no longer requires access, so the permission is revoked.

---

## 5. Transaction Control Language (TCL)

- **Purpose:** Manage database transactions.

- **Common Commands:** `COMMIT`, `ROLLBACK`, `SAVEPOINT`

- **Example:**

  ```sql
  BEGIN;
  UPDATE employees SET salary = 55000 WHERE id = 1;
  COMMIT;
  ```

  *Scenario:* The HR team processes salary updates and commits changes to ensure they are saved.

  ```sql
  BEGIN;
  UPDATE employees SET salary = 60000 WHERE id = 2;
  SAVEPOINT before_bonus;
  UPDATE employees SET salary = 65000 WHERE id = 2;
  ROLLBACK TO before_bonus;
  COMMIT;
  ```

  *Scenario:* The HR team updates an employee’s salary but decides to revert part of the change while keeping the previous modification.

---

### Summary

SQL has different types of commands to handle different tasks:

- **DQL**: Get data (`SELECT`) - *Used for fetching student grades, product prices, etc.*
- **DDL**: Structure the database (`CREATE`, `ALTER`, `DROP`) - *Used when setting up company databases, adding new fields, etc.*
- **DML**: Change data (`INSERT`, `UPDATE`, `DELETE`) - *Used for adding new employees, updating salaries, removing inactive records, etc.*
- **DCL**: Manage permissions (`GRANT`, `REVOKE`) - *Used for controlling who can view or modify data.*
- **TCL**: Manage transactions (`COMMIT`, `ROLLBACK`) - *Used when making financial transactions or salary updates that should be either saved or rolled back.*

These SQL types help in efficiently working with databases across various real-world applications. 🚀

