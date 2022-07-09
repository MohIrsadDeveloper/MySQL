1.) What is Database?

    1. Overview =>
        1. Database is the collection of organized data which is structured or unstructured. The database's primary goal is to store a huge amont of data.
        2. Many Dynamic websites on the Internet today are store in dabases.
        3. There are many Types of Databases which are explained in this article.

    2. Components of Database => There are five Components in which a database is divided.
        1. Hardware
        2. Software
        3. Data
        4. Procedures
        5. Database Access Language

    3. Types of Databases =>
        1. Filed-Based databases => 1968s
        2. Relational databases => 1980s
        3. Object-oriented databases
        4. Distributed databases
        5. NoSQL databases
        6. Graph Databases
        7. Open source Databases
        8. Cloud databases
        9. Evolution of Database

4. A database is an organized collection of data that enables simple and efficient storage, retrieval, and modification of data. There are 11 fundamental types of databases:

Centralized database.
Cloud database.
Commercial database.
Distributed database.
End-user database.
Graph database.
Hierarchical database.
Network database.
NoSQL database.
Objected-oriented database.
Relational database.

<!-- Relational and Non Relational Databases -->
1. Overview =>
     Relational and Non-relational databases are two kinds of management systems that allow us to create databases that will help us in managing complex data. A relational database is structured, whereas NoSQL is semi-structured or unstructured. In the relational database(SQL), it consists of tables(fields and records), whereas non-relational database data is stored in form of graphs, documents(XML, JSON).

2. Introduction =>
    There are two types of database management systems:
        1. Relational Databases.
        2. Non-Relational Databases.

    1. Relational Database =>
        1. A relational database or relational database management system(RDBMS) stores data in the form of a table. The table consists of rows and columns, and in a relational database rows are referred to as records, and columns are referred to as fields

        2. The term relational database was first coined in year 1970s by E.F. Codd at IBM and later in 1974 Donald D. Chamberlin and Raymond F. Boyce released SQL or standard Query Language, which allows the user to interact with the relational database system.

        
MySQL Commands =>
    <!-- Some of The Most Important SQL Commands -->
        1. SELECT - extracts data from a database
        2. UPDATE - updates data in a database
        3. DELETE - deletes data from a database
        4. INSERT INTO - inserts new data into a database
        5. CREATE DATABASE - creates a new database
        6. ALTER DATABASE - modifies a database
        7. CREATE TABLE - creates a new table
        8. ALTER TABLE - modifies a table
        9. DROP TABLE - deletes a table
        10. CREATE INDEX - creates an index (search key)
        11. DROP INDEX - deletes an index



<!-- Using W3Cube -->
         <!-- DATABASE -->
1. Create Database => CREATE DATABASE <DATABASE_NAME>;
2. Use Database => USE <DATABASE_NAME>;
3. Drop Database => DROP DATABASE <DATABASE_NAME>;
4. Show Current Database => <DATABASES>;

        <!-- TABLES -->
1. Create Table => CREATE TABLE <TABLE_NAME> (
                        column1 datatype,
                        column2 datatype,
                        column3 datatype,
                        ....
                    );

2. Show Tables => SHOW TABLES;
3. 

        <!-- INSERT DATA INTO TABLE -->
<!-- INSERT SINGLE ROW -->
1. INSERT INTO <TABLE_NAME> (column1, column2, column3, ...)
    VALUES (value1, value2, value3, ...);
2. Show All Data => SELECT * FROM <TABLE_NAME>;
3. Show Particular Column => SELECT <COLUMN_NAME> FROM <TABLE_NAME>;
<!-- INSERT MULTIPLE ROWS -->
1. INSERT INTO <TABLE_NAME> (column1, column2, column3, ...)
    VALUES (value1, value2, value3, ...),
            (value1, value2, value3, ...),
            (value1, value2, value3, ...);
<!-- IF TABLE COLUMN AND DATA INSERT IS EQUAL -->
1. INSERT INTO <TABLE_NAME> VALUES (value1, value2, value3, ...);
    or
    INSERT INTO <TABLE_NAME> VALUES
    (value1, value2, value3, ...),
    (value1, value2, value3, ...),
    (value1, value2, value3, ...);

<!-- SELECT Query with WHERE Cluase -->
1. Select all Column => SELECT * FROM <TABLE_NAME>;
2. Select Some Column => SELECT column1, column2, ... FROM <TABLE_NAME>;
3. Select using Alias =>   SELECT name AS "Student Name", age AS "AGE" FROM <TABLE_NAME>;
4. Where => The WHERE clause is used to filter records.
            SELECT * FROM <TABLE_NAME> WHERE <CONDITIONS>;
        <!-- CONDITIONS -->
        1. = equals
        2. != not equal
        3. > greater than
        4. < less than
        5. >= greater than or equal
        6. <= less than or equal
    ex. => SELECT * FROM  <students> WHERE AGE >= 18;

<!-- MySQL constraints -->
1. NOT NULL
2. UNIQUE
3. DEFAULT
4. CHECK
5. FOREGIN KEY
6. PRIMARY KEY

EX. => CREATE TABLE students (
    id INT NOT NULL UNIQUE,
    name varchar(100) not null,
    email varchar(150) not null unique,
    age tinyint check (age >= 18),
    stutus boolean default 1
);
    => INSERT INTO students (id, name, email, age)
                    VALUES (1, "abdul", "abdul@gmail.com", 16); // give error as age not correct;

<!-- AND, OR & NOT -->
1. AND Operator : MySQL logical AND operator compares two expressions and returns true if both of the expressions are true.
        Syntax :
            SELECT * FROM <TABLE_NAME> WHERE <CONDITION1> AND <CONDITION2>;
        Ex. =>
            SELECT * FROM students WHERE age >= 18 AND age <= 25;

2. OR Operator : MySQL OR operator compares two expressins and returns TRUE if either of the expressions is TRUE.
        Syntax :
            SELECT * FROM <TABLE_NAME> WHERE <CONDITION1> OR <CONDITION2>;
        Ex. =>
            SELECT * FROM students <TABLE_NAME> WHERE city = "Mumbai" OR city = "Pune";

3. NOT Operator : MySQL NOT operator reverses or negates the Inputs.
        Syntax :
            SELECT * FROM <TABLE_NAME> WHERE NOT <CONDITION1> AND NOT <CONDITION2>;
        EX. =>
            SELECE * FROM students WHERE NOT city = "Mumbai";
4. IN Operator => The IN operator allows you to specify multiple values in a WHERE clause.
                  The IN operator is a shorthand for multiple OR conditions.
        Syntax : 
            SELECT * FROM <TABLE_NAME> WHERE <COLUMN_NAME> IN (VALUE1, VALUE2, ...);
        EX. =>
            SELECT * FROM students WHERE age IN (19, 20, 21, 23);
5. LIKE Operators =>  The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.
        1. The percent sign (%) represents zero, one, or multiple characters.
        2. The underscore sign(_) represents one, single character
    <!-- Patterns -->
    1. LIKE 'a%' => Starts with "a";
    2. LIKE '%a' => End with "a";
    3. LIKE '%or%' => Have "or" in any position
    4. LIKE '_r%' => Have 'r' in the second position
    5. LIKE 'a_%' => Start with "a" and are atleast 2 characters in length
    6. LIKE 'a__%' => Start with "a" and are atleast 3 characters in length
    7. LIKE 'a%o' => Start with "a" and ends with "o"

    <!-- Example of above patterns -->
    1. SELECT * FROM students WHERE name LIKE "a%";
    2. SELECT * FROM students WHERE name LIKE "%a";
    3. SELECT * FROM students WHERE name LIKE "%a%";
    4. SELECT * FROM students WHERE name LIKE "_a%";
    5. SELECT * FROM students WHERE name LIKE "a_%";
    6. SELECT * FROM students WHERE name LIKE "a__%";
    7. SELECT * FROM students WHERE name LIKE "a%l";

<!-- Data with Between & Not Between -->
1. SELECT * FROM students WHERE age BETWEEN <value1> AND <value2>;
    Ex. =>
        SELECT * FROM students WHERE age BETWEEN 20 AND 30;

2. SELECT * FROM students WHERE age NOT BETWEEN <value1> AND <value2>;
    Ex. =>
        SELECT * FROM students WHERE age NOT BETWEEN 20 AND 30;

<!-- Order By AND Distinct in MySQL -->
1. SELECT * FROM <TABLE_NAME> ORDER BY <COLUMN_NAME> ASC | DESC;
    Ex. =>
        <!-- for name -->
        SELECT * FROM students ORDER BY name ASC;
        SELECT * FROM students ORDER BY name DESC;
        <!-- for age -->
        SELECT * FROM students ORDER BY age ASC;
        SELECT * FROM students ORDER BY age DESC;

2. SELECT DISTINCT <COLUMN_NAME> FROM <TABLE_NAME>;
    Ex. =>
        <!-- for age -->
        SELECT DISTINCT age FROM students;
        <!-- for city with order -->
        SELECT DISTINCT city FROM students ORDER BY ASC;
        SELECT DISTINCT city FROM students ORDER BY DESC;

<!-- IS NULL AND IS NOT NULL Operators -->
    syntax :
        SELECT * FROM students WHERE <COLUMN_NAME> IS NULL | IS NOT NULL;
    Ex. =>
        SELECT * FROM students WHERE

<!-- LIMIT AND OFFSET -->
1. LIMIT => If want to LIMIT, the number of results that are returned you can simply use the LIMIT command with several rows to LIMIT by.
    LIMIT is use with any command like WHERE, ORDER BY, etc.

    syntax :
        SELECT * FROM <TABLE_NAME> LIMIT [NUMBER TO LIMIT BY];
    Ex. =>
        SELECT * FROM students LIMIT 10;

2. OFFSET => OFFSET is used to LIMIT with pagination like from 5th to 10th and 10th to 16th and so on.
    OFFSET always use with LIMIT command.

    Syntax :
        SELECT * FROM students LIMIT [NUMBER TO LIMIT BY] OFFSET [OFFSET LIMIT];
    Ex. =>
        SELECT * FROM students LIMIT 10 OFFSET 1;
        SELECT * FROM students LIMIT 10 OFFSET 10;

<!-- Aggregate Functions : SUM, MIN, MAX & AVG -->
1. COUNT() : Returns the number of rows in a database table.
    Syntax :
        SELECT COUNT(<COLUMN_NAME>) FROM <TABLE_NAME>;

    Ex. =>
        SELECT COUNT(id) FROM students WHERE fees > 5000;

2. SUM() : Returns the total sum of a numeric column.
    Syntax :
        SELECT SUM(<COLUMN_NAME>) FROM <TABLE_NAME>;

    Ex. =>
        SELECT SUM(age) FROM students;

3. AVG() : Calculates the average of a set of values.
    Syntax :
        SELECT AVG(<COLUMN_NAME>) FROM <TABLE_NAME>;

    Ex. =>
        SELECT AVG(age) FROM students;

4. MIN() : Returns the lowest value (minimum) in a set of non-NULL values.
    Syntax :
        SELECT MIN(<COLUMN_NAME>) FROM <TABLE_NAME>;

    Ex. =>
        SELECT MIN(age) FROM students;

5. MAX() : Returns the greatest value (maximum) in a set of non-NULL values.
    Syntax :
        SELECT MAX(<COLUMN_NAME>) FROM <TABLE_NAME>;
    Ex. =>
        SELECT MAX(age) FROM students;

<!-- UPDATE Query -->
1. UPDATE => UPDATE Query is used to make updation on fields. In Update Command Where Clause is mandetory.
    Syntax :
        UPDATE <TABLE_NAME> SET 
        field1 = <new-value1>,
        field2 = <new-value2> [WHERE Clause];

    Ex. =>
        UPDATE students SET age = 20 WHERE id = 2;
        UPDATE students SET
        age = 30 WHERE id  = 5;

<!-- DELETE Query -->
1. DELETE => Delete command only remove the data or field then not change the primary key.
             If we insert new records then it will insert with new primary key.
    Syntax :
        DELETE FROM <TABLE_NAME> [WHERE Clause];

    Ex. =>
        DELETE FROM students WHERE id = 5;

<!-- PRIMARY KEY AND FOREIGN KEY -->
1. Commit =>
    Syntax :
        COMMIT;

2. Rollback =>
    Syntax :
        ROLLBACK;

<!-- PRIMARY KEY AND FOREIGN KEY -->
1. Primary key =>
            1. Primary key always contains unique data
            2. It cannot be null
            3. There must be a single primary key
    Syntax :    
        CREATE TABLE <TABLE_NAME> (
            id INT NOT NULL AUTO_INCREMENT,
            name VARCHAR(50) NOT NULL,
            age INT NOT NULL,
            city VARCHAR(10) NOT NULL,
            PRIMARY KEY(id)
        );

2. Foreign Key =>
            1. The foreign key is used to link two tables.
            2. A foreign key in one table (child table) is used to point PRIMARY KEY in another table (parent table)
    Syntax :
        CREATE TABLE <TABLE_NAME> (
            id INT NOT NULL AUTO_INCREMENT,
            name VARCHAR(50) NOT NULL,
            age INT NOT NULL,
            city INT NOT NULL,
            PRIMARY KEY(id),
            FOREIGN KEY (city) REFERENCES cities  (cid)
        );