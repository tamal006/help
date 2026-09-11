CREATE TABLE student (
    student_id NUMBER PRIMARY KEY,
    name VARCHAR2(50),
    dept VARCHAR2(20),
    marks NUMBER(5,2)
);



INSERT INTO student VALUES (1, 'Alice', 'CSE', 75.5);
INSERT INTO student VALUES (2, 'Bob', 'IT', 68.0);
INSERT INTO student VALUES (3, 'Charlie', 'ECE', 82.0);
INSERT INTO student VALUES (4, 'David', 'MECH', 65.0);
INSERT INTO student VALUES (5, 'Eve', 'CSE', 90.0);
INSERT INTO student VALUES (6, 'Frank', 'IT', 72.5);
COMMIT;

SELECT * FROM student 
WHERE dept IN ('CSE', 'IT', 'ECE');


SELECT * FROM student 
WHERE marks > 70;


SELECT * FROM student 
WHERE dept NOT IN ('CSE', 'IT');


SELECT * FROM student 
WHERE marks > (SELECT AVG(marks) FROM student);


-- In Ascending Order
SELECT * FROM student 
ORDER BY marks ASC;

-- In Descending Order
SELECT * FROM student 
ORDER BY marks DESC;