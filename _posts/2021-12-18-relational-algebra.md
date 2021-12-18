---
layout: single
title: "Relational Algebra"
tags: [database]
categories: database


---

## Relational Algebra

![image-20211218055501407](/assets/images/image-20211218055501407.png)

**Example**:

Considering the following relations...

Student(sid, name, gpa) 
Course(cid, name, department) 
Registers(sid, cid, semester)

1. Relational Algebra to find the name of students who take course with cid = CSCI5708 in Spring 2021 semester:

![image-20211218063817351](/assets/images/image-20211218063817351.png)

SQL Query for above:

SELECT S.name
FROM Students S, Registers R
WHERE S.sid = R.sid AND
		R.cid ="CSCI5708" AND R.semester="Spring 2021";

2. Relational Algebra to find the student id(s) that have taken all courses in the Computer Science department:

![image-20211218065359702](/assets/images/image-20211218065359702.png)

3. Relational Algebra to find the name of the student with the highest gpa. 

![image-20211218065434476](/assets/images/image-20211218065434476.png)

4. Relational Algebra to find the student id(s) who have taken the same course in exactly two different semesters. 

![image-20211218065454254](/assets/images/image-20211218065454254.png)

5. Relational Algebra to find  the  combination  of  student  id(s)  who  have  taken  the  same  exact  courses.  Each combination of student id(s) must only appear once.

![image-20211218065514216](/assets/images/image-20211218065514216.png)





#### References

- Course: CSCI4707- Practice of Database Systems
  - Ramakrishnan, R., & Gehrke, J. (2000). *Database Management Systems*. McGraw-Hill. 

