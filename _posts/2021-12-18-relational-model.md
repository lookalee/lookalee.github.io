---
layout: single
title: "Relational Model & SQL Queries"
tags: [database]
categories: database
toc: yes

---

## Relational Model & SQL Queries

- Relational Model is the most widely used model. A relation can be thought of a set of rows (or tuples) of records.

- SQL Query Example:

  ![image-20211218051522206](/assets/images/image-20211218051522206.png)

**SQL Queries to translate this ER diagram**:

CREATE TABLE Student (email, name, gpa, PRIMARY KEY(email)); 

CREATE TABLE Professor (email, name, PRIMARY KEY(email)); 

CREATE TABLE Course (id, name, credits, pemail NOT NULL, 
		PRIMARY KEY(id), 
		FOREIGN KEY pemail REFERENCES Professor(email));

CREATE TABLE Register (email, cid, semester, 
		PRIMARY KEY(email, cid), 
		FOREIGN KEY email REFERENCES Student(email), 
		FOREIGN KEY cid REFERENCES Course(cid));

CREATE TABLE Category (id, PRIMARY KEY(id)); 

CREATE TABLE Course_Belong_to (cid, catid, 
		PRIMARY KEY(cid, catid), 
		FOREIGN KEY cid REFERENCES Course(id),
		FOREIGN KEY catid REFERENCES Category(id)); 

CREATE TABLE Cate_Belong_to (sub, super, 
		PRIMARY KEY(sub, super), 
		FOREIGN KEY sub REFERENCES Category(id), 		FOREIGN KEY super REFERENCES Category(id));

CREATE TABLE Undergraduate (email, year, 		PRIMARY KEY(email), 
		FOREIGN KEY email REFERENCES Student(email) ON DELETE CASCADE); 

CREATE TABLE Graduate (email, research_area, advisor NOT NULL 
		PRIMARY KEY(email), 
		FOREIGN KEY email REFERENCES Student(email) ON DELETE CASCADE, 
		FOREIGN KEY advisor REFERENCES Professor(email));

CREATE TABLE Project (id, name, owner NOT NULL 
		PRIMARY KEY(id, name, owner), 
		FOREIGN KEY owner REFERENCES Professor(email) ON DELETE CASCADE); 

CREATE TABLE Host (email, id, name, 
		PRIMARY KEY(email, id, name), 
		FOREIGN KEY email REFERENCES Graduate_Student(email), 
		FOREIGN KEY (id, name) REFERENCES Projects(id, name) ON DELETE CASCADE);

#### References

- Course: CSCI4707- Practice of Database Systems
  - Ramakrishnan, R., & Gehrke, J. (2000). *Database Management Systems*. McGraw-Hill. 

