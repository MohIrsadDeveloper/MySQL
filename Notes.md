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