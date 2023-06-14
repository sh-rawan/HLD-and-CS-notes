# Database

## Create command

```sql
CREATE TABLE Users(
    email varchar(50);
    f_name varchar(20);
    userId int;
    UNIQUE(email, phone_number);
    PRIMARY KEY(userId, email);
    FOREIGN KEY(paymentId) REFERENCES Payments(Pid);
    -- field_name field_type Constraints;
);
```

### Types of fields

1. Numeric
    - int, smallint, long
    - float, double precision(5)
2. Character
    - CHAR(n)
    - varchar(n)
    - text
3. Boolean
4. Date
5. Array/JSON

### Constraints

1. NOT NULL
2. marks int DEFAULT 0;
3. UNIQUE(email);
4. PRIMARY KEY(userId);
5. FOREIGN KEY(paymentId) REFERENCES Payments(Pid);

## CRUD

1. Create

```sql
INSERT INTO Users
(email,  userID, f_name) VALUES
("abc@gmail.com", 1, "ABC"),
("xyz@gmail.com", 1, "XYZ")
```

2. Read

```sql
SELECT * FROM users WHERE userId <> 100 OR age > 20 AND height < 177;

-- Regex expression
SELECT * FROM users WHERE emailId LIKE "%@gmail.com";

-- DISTINCT keyword
SELECT DISTINCT emailID from payments;

--  ORDER BY
SELECT * FROM users WHERE userId <> 100 ORDER BY age, height DESC;
-- IS NULL
SELECT * FROM users WHERE mid_name IS NOT NULL;
-- rename column
SELECT emailID, (weight/height)*100 AS BMI FROM users;

-- Symbols =,>,<,<=,>=,<> / !=
```

3. Update

```sql
UPDATE users SET email="abc@gmail.com" WHERE userId=100;
```

4. Delete

```sql
DELETE FROM users WHERE userId=100;

-- If Where is false for all the columns in database then it will delete all the database.
-- And same is the case with updateing the data also
```

5. Joins in SQL

```sql
SELECT * FROM Topic JOIN Videos ON Topic.VID = VIDEOS.VID WHERE Topic_name="Arrays"

-- Inner (JOIN)
-- LEFT JOIN --> keeps always left part and put null in right part if not present
-- RIGHT JOIN
-- OUTER JOIN --> keeps both and puts null in either left or right
-- NATURAL keyword can also be used with the above tables
```

6. Missellenious

```sql
(SELECT email, height, age FROM users WHERE height<170)
UNION / INTERSECT / EXCEPT
(SELECT email, height, age FROM users WHERE age>100);
-- Attributes should always match for both the sets you want to merge.

-- Aggretions on max, min, avg, sum, count
-- Aggretation by using Having clause
SELECT f_name, l_name, max(age) AS max_age FROM users GROUP BY f_name, l_name;
SELECT email, sum(duration) AS total_dur FROM payments GROUP BY email HAVING max(y_o_p) >= 2020;
```

-   Problem -->

    -   HAVING CLAUSE is likw WHERE clause of GROUP BY function

```sql
-- List for every cohort, max problem solved by any student
-- excluding those cohort that have < 5 students
SELECT cohort, max(problem_solved) FROM Users GROUP BY cohort HAVING COUNT(DISTINCT userID) > 5
```
