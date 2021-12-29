---
layout: single
title: "Entity Relationship Diagram"
tags: [database]
categories: database

---

## ER Model Basics

**Entity** **Set**: Collection of similar entities which is a a real-world object. Described using a set of **attributes** (Ex: all employees)

- Each entity set has a **key**.
- Each attribute has a **domain**.

**Relationship**: Relationship between two or more entities (Ex: Peter works in the hospital)

- Relationship can have a **descriptive attribute** (Ex: Peter worked in hospital **since** 2012).
- There is ALWAYS a relationship between two entities.

Ex)![image-20211218031352295](/assets/images/image-20211218031352295.png)
'Student' and 'Course' are entities, 'Take' is a relation, and the rest are attributes (email and id are keys)

- An entity can have relation with another entity.

  Ex) <img src="/assets/images/image-20211218031658465.png" alt="image-20211218031658465" style="zoom:50%;" />

#### Constraints

- If an entity can only show up **at most once** in a relationship, an arrow line is used.

- If each entity must show up **at least once** in a relationship, a thick line is used (total participation)

- If each entity must show up **exactly once** in a relationship, a thick arrow is used. 

  ex) <img src="/assets/images/image-20211218034328472.png" alt="image-20211218034328472" style="zoom:67%;" />

  *A course is taught by exactly one professor, student can take any number of courses (normal line) and course must have at least one student taking it.* 

#### Weak Entities

- A weak entity can only be identified uniquely by the primary key of another entity. 

  - A weak entity must always have total participation(have at least one) on the strong entity

    ex) <img src="/assets/images/image-20211218040617586.png" alt="image-20211218040617586" style="zoom:67%;" />
    *'Dependent' is the weak entity, 'name' is the partial key. Dependent can only be uniquely identified by the employee's id.* 

#### ISA ('is a') Hierarchy

- If A ISA B, every A entity is also considered to be a B entity. 

  - Since B is A's parent, the common attributes will be linked to B, and specific attributes will be linked to A.

    ex) ![image-20211218041943474](/assets/images/image-20211218041943474.png)

    *Undergraduate Students and Graduate Students are a Student, and they have specific attributes (year and research_area).*

#### Aggregation

- Used for modeling a relationship between entity set and a relationship set.

- Allows treating a relationship set as an entity set.

  ex) <img src="/assets/images/image-20211218043532960.png" alt="image-20211218043532960" style="zoom:67%;" />

#### Design Choices

- When drawing ER diagrams, decisions are usually subjective and involve thinking about the trade-offs bewteen using entity vs attribute, entity vs relationship, use ISA vs not use ISA, binary vs ternary, etc
- Entity vs Attribute
  - ex) If an employee has **multiple** addresses, addresses should be an entity instead of an attribute. 

#### Grand Example

![image-20211218044513947](/assets/images/image-20211218044513947.png)

- Each course is taught by exactly one professor
- Each professor can teach zero or many courses
- Student registers zero or many courses, and each course must have at least one student.
- Everytime student registers for a course, the current semester is stored.
- Each course belongs to at least one category, and each category can have 0 or many courses.
- Each category forms a hierarchy, where it can have 0 or many super-categories and zero or many sub-categories. 
- Undergraduate students and graduate students are a student, and have same attributes of a student (ISA relationship)
- Undergraduate students have additional attribute of 'year', and graduate students have additional attribute of 'research_area'.
- Each graduate student must have exactly one professor as an advisor. 
- Each professor has zero or many projects, and each project is owned by exactly one professor.
- Each graduate student can work on zero or many projects. 
- When professor leaves the university, all projects under them are also removed (since project is a weak entity that depends on professor) 

#### References

- Course: CSCI4707- Practice of Database Systems
  - Ramakrishnan, R., & Gehrke, J. (2000). *Database Management Systems*. McGraw-Hill. 

