a 9. Create table named student with con which contains name, with student id, dept. on this table and marks of semester, based display the information, who belongs to either CSE or IT, ECE.

Display the students who have got the marks more than 70%

Display students who don't belong tes CSE or 10 IT.

Display students who got marks> avg. marks.

Display the records of the students according to ASC order and DESC order.

Sure — this looks like a SQL/MySQL practice question. I'll correct the wording and give you the complete queries.

1. Create student table
CREATE TABLE student (
    student_id INT PRIMARY KEY,
    name VARCHAR(50),
    dept VARCHAR(20),
    marks INT
);
2. Insert some sample data
INSERT INTO student (student_id, name, dept, marks)
VALUES
(1, 'Rahul', 'CSE', 85),
(2, 'Amit', 'IT', 72),
(3, 'Priya', 'ECE', 65),
(4, 'Riya', 'CSE', 55),
(5, 'Arjun', 'ME', 90),
(6, 'Sneha', 'IT', 68),
(7, 'Karan', 'ECE', 78);
3. Display students who belong to CSE, IT, or ECE
Using IN:

SELECT *
FROM student
WHERE dept IN ('CSE', 'IT', 'ECE');
4. Display students who got marks more than 70%
SELECT *
FROM student
WHERE marks > 70;
5. Display students who don't belong to CSE or IT
Using NOT IN:

SELECT *
FROM student
WHERE dept NOT IN ('CSE', 'IT');
6. Display students who got marks greater than the average marks
First, SQL calculates the average using AVG():

SELECT *
FROM student
WHERE marks > (SELECT AVG(marks) FROM student);
This is called a subquery.

For the sample data:

Average = 73.28 approximately
So students with marks above the average will be displayed.

7. Display records in ascending order of marks
SELECT *
FROM student
ORDER BY marks ASC;
ASC = smallest → largest.

8. Display records in descending order of marks
SELECT *
FROM student
ORDER BY marks DESC;
DESC = largest → smallest.

Complete answer
-- Create table
CREATE TABLE student (
    student_id INT PRIMARY KEY,
    name VARCHAR(50),
    dept VARCHAR(20),
    marks INT
);

-- Insert records
INSERT INTO student VALUES
(1, 'Rahul', 'CSE', 85),
(2, 'Amit', 'IT', 72),
(3, 'Priya', 'ECE', 65),
(4, 'Riya', 'CSE', 55),
(5, 'Arjun', 'ME', 90),
(6, 'Sneha', 'IT', 68),
(7, 'Karan', 'ECE', 78);

-- CSE, IT or ECE
SELECT * FROM student
WHERE dept IN ('CSE', 'IT', 'ECE');

-- Marks greater than 70
SELECT * FROM student
WHERE marks > 70;

-- Not CSE or IT
SELECT * FROM student
WHERE dept NOT IN ('CSE', 'IT');

-- Marks greater than average
SELECT * FROM student
WHERE marks > (SELECT AVG(marks) FROM student);

-- Ascending order
SELECT * FROM student
ORDER BY marks ASC;

-- Descending order
SELECT * FROM student
ORDER BY marks DESC;
Important SQL concepts in this question: IN, NOT IN, WHERE, AVG(), subquery, and ORDER BY ASC/DESC.


No file chosen