<!-- EASY ASSIGNMENT -->

<!-- Task 1 Input -->

mysql> select first_name, last_name
    -> FROM student;

<!-- Take 1 Output -->

+------------+-----------+
| first_name | last_name |
+------------+-----------+
| Eric       | Ephram    |
| Greg       | Gould     |
| Adam       | Ant       |
| Howard     | Hess      |
| Charles    | Caldwell  |
| James      | Joyce     |
| Doug       | Dumas     |
| Kevin      | Kraft     |
| Frank      | Fountain  |
| Brian      | Biggs     |
+------------+-----------+
10 rows in set (0.00 sec)

<!-- Task 2 Input -->

mysql> SELECT *
    -> FROM student
    -> WHERE years_of_experience < 8;

<!-- Task 2 Output -->

+------------+------------+-----------+---------------------+------------+
| student_id | first_name | last_name | years_of_experience | start_date |
+------------+------------+-----------+---------------------+------------+
|          1 | Eric       | Ephram    |                   2 | 2016-03-31 |
|          2 | Greg       | Gould     |                   6 | 2016-09-30 |
|          3 | Adam       | Ant       |                   5 | 2016-06-02 |
|          4 | Howard     | Hess      |                   1 | 2016-02-28 |
|          5 | Charles    | Caldwell  |                   7 | 2016-05-07 |
|          8 | Kevin      | Kraft     |                   3 | 2016-04-15 |
|         10 | Brian      | Biggs     |                   4 | 2015-12-25 |
+------------+------------+-----------+---------------------+------------+
7 rows in set (0.00 sec)

<!-- Task 3 Input -->

mysql> SELECT last_name, start_date, student_id
    -> FROM student
    -> ORDER BY last_name ASC;

<!-- Task 3 Output -->
+-----------+------------+------------+
| last_name | start_date | student_id |
+-----------+------------+------------+
| Ant       | 2016-06-02 |          3 |
| Biggs     | 2015-12-25 |         10 |
| Caldwell  | 2016-05-07 |          5 |
| Dumas     | 2016-07-04 |          7 |
| Ephram    | 2016-03-31 |          1 |
| Fountain  | 2016-01-31 |          9 |
| Gould     | 2016-09-30 |          2 |
| Hess      | 2016-02-28 |          4 |
| Joyce     | 2016-08-27 |          6 |
| Kraft     | 2016-04-15 |          8 |
+-----------+------------+------------+
10 rows in set (0.00 sec)

<!-- Task 4 Input -->

mysql> SELECT * FROM student WHERE first_name IN ("Adam", "James", "Frank") ORDER BY last_name DESC;

<!-- Task 4 Output -->

+------------+------------+-----------+---------------------+------------+
| student_id | first_name | last_name | years_of_experience | start_date |
+------------+------------+-----------+---------------------+------------+
|          6 | James      | Joyce     |                   9 | 2016-08-27 |
|          9 | Frank      | Fountain  |                   8 | 2016-01-31 |
|          3 | Adam       | Ant       |                   5 | 2016-06-02 |
+------------+------------+-----------+---------------------+------------+
3 rows in set (0.00 sec)

<!-- Task 5 Input -->

mysql> SELECT first_name, last_name, start_date
    -> FROM student
    -> WHERE start_date BETWEEN "2016-01-01" AND "2016-06-30"
    -> ORDER BY start_date DESC;

<!-- Task 5 Output -->

+------------+-----------+------------+
| first_name | last_name | start_date |
+------------+-----------+------------+
| Adam       | Ant       | 2016-06-02 |
| Charles    | Caldwell  | 2016-05-07 |
| Kevin      | Kraft     | 2016-04-15 |
| Eric       | Ephram    | 2016-03-31 |
| Howard     | Hess      | 2016-02-28 |
| Frank      | Fountain  | 2016-01-31 |
+------------+-----------+------------+
6 rows in set (0.00 sec)

<!-- Task 6 Input -->

<!-- MEDIUM ASSIGNMENT -->

<!-- Explain assignment -->

+----------------+------------------+------+-----+---------+----------------+
| Field          | Type             | Null | Key | Default | Extra          |
+----------------+------------------+------+-----+---------+----------------+
| assignment_id  | int(11) unsigned | NO   | PRI | NULL    | auto_increment |
| student_id     | int(11)          | NO   |     | NULL    |                |
| assignment_nbr | int(11)          | NO   |     | NULL    |                |
| class_id       | int(11)          | YES  |     | NULL    |                |
| grade_id       | int(11) unsigned | NO   | MUL | NULL    |                |
+----------------+------------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)

<!-- Select * on the assignment table  -->

+---------------+------------+----------------+----------+----------+
| assignment_id | student_id | assignment_nbr | class_id | grade_id |
+---------------+------------+----------------+----------+----------+
|             1 |          2 |              1 |        1 |        1 |
|             2 |          3 |              1 |        1 |        2 |
|             3 |          4 |              1 |        1 |        3 |
|             4 |          4 |              1 |        2 |        4 |
|             5 |          4 |              1 |        2 |        5 |
+---------------+------------+----------------+----------+----------+
5 rows in set (0.00 sec)

<!-- Explain grade -->

+-------+------------------+------+-----+---------+----------------+
| Field | Type             | Null | Key | Default | Extra          |
+-------+------------------+------+-----+---------+----------------+
| id    | int(11) unsigned | NO   | PRI | NULL    | auto_increment |
| grade | varchar(30)      | NO   |     | NULL    |                |
+-------+------------------+------+-----+---------+----------------+
2 rows in set (0.00 sec)

<!-- Select * on the grade table -->

+----+-----------------------------+
| id | grade                       |
+----+-----------------------------+
|  1 | Incomplete                  |
|  2 | Complete and unsatisfactory |
|  3 | Complete and satisfactory   |
|  4 | Exceeds expectations        |
|  5 | Not graded                  |
+----+-----------------------------+
5 rows in set (0.00 sec)


<!-- HARD ASSIGNMENT -->

<!-- Explain on Assignment Table with added student_id foreign key -->

+----------------+------------------+------+-----+---------+----------------+
| Field          | Type             | Null | Key | Default | Extra          |
+----------------+------------------+------+-----+---------+----------------+
| assignment_id  | int(11) unsigned | NO   | PRI | NULL    | auto_increment |
| student_id     | int(11) unsigned | NO   | MUL | NULL    |                |
| assignment_nbr | int(11)          | NO   |     | NULL    |                |
| class_id       | int(11)          | YES  |     | NULL    |                |
| grade_id       | int(11) unsigned | NO   | MUL | NULL    |                |
+----------------+------------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)

<!-- Testing constraint by trying to add a row to assignment table for a student that doesn't exist -->

ERROR 1452 (23000): Cannot add or update a child row: a foreign key constraint fails (`tiy`.`assignment`, CONSTRAINT `fk_student_id` FOREIGN KEY (`student_id`) REFERENCES `student` (`student_id`))
mysql>
