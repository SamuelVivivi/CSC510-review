# Review Ques 8

## Data Anomalies

Consider the following design where every data point is stuffed into one matrix. In the following:
-    ST is some number that refers to the shipping status (e.g 20 means order shipped and 30 means received)
-    PNO are parts
-    QTY is quantity
-    SNO is some shipping number (shipping ID)

```
--------------------------------
| SNO | ST | PNO | QTY | CLR   |
--------------------------------
| S1  | 20 | P1  | 300 | red   |
| S1  | 20 | P2  | 200 | blue  |
| S1  | 20 | P2  | 400 | blue  |
| S1  | 20 | P4  | 200 | gray  |
| S1  | 20 | P5  | 100 | black |
| S1  | 20 | P6  | 100 | white |
| S2  | 30 | P1  | 300 | red   |
| S2  | 30 | P2  | 400 | blue  |
| S3  | 30 | P2  | 200 | blue  |
| S4  | 20 | P2  | 200 | gray  |
| S4  | 20 | P4  | 300 | gray  |
| S4  | 20 | P5  | 400 | black |
--------------------------------
```

1.    What is CRUD? What commonly-used web-programming pattern supports CRUD?

CRUD= create, read, update, delete. RESTful service.

2.    What is insert anomaly? Show how the above design suffers from it. How can SQL solve it.

An Insert Anomaly occurs when certain attributes cannot be inserted into the database without the presence of other attributes.

Problem: If our warehouse receives 1000 new parts, which no one has ordered yet, then it cannot be added to our matrix database (without some bogus null fields-- which significantly complicate long term maintenance).

Diagnosis: the above one-matrix design has too many data dependencies between cells in each row.

Treatment: Separate the cells into different tables such that each cell is now dependent on only one special cells in the table (the primary key).

Example: In the above 3 table design, it would be possible to insert new Parts without demanding that they exist in an order.


3.    What is delete anomaly? Show how the above design suffers from it. How can SQL solve it.

A Delete Anomaly exists when certain attributes are lost because of the deletion of other attributes. 

Problem: If we complete all our shipments for S1 and S4 (above), and we delete those rows from our one-matrix, we would lose access to the fact that we ship those a part called P5. This would be a problem if anyone calls us up to ask if we can supply them with P5.

Diagnosis: As before, we have not separated out or dependent and non-dependent variables. The fact that we hold P5 is a separate concept to whether or not P5 is in any shipment.

Treatment: As before. Separate the cells into tables defined by primary keys.

Example: In the above 3 table design, it would be possible to complete all shipments, archive away rows in the Shipment to some long-term storage facility, and still have access to what Parts we hold in the warehouse.

4.    What is update anomaly? Show how the above design suffers from it. How can SQL solve it. 

An Update Anomaly exists when one or more instances of duplicated data is updated, but not all. 

Problem: There is a bug in the above one-matrix example. Can you see? Look at the colors for the P2 part? Note that they are usually blue but in S4 it is labeled gray. Someone has made a mistake?

Diagnosis: When the definition of things is repeated in multiple places, then it is all to easy to update properties here and forget to do it there, there, and there as well.

Treatment: As before, if everything is separated logically, then information about one thing is stored in one place only. Which means we could update color in one place and that color is now global across the hole database.

Example: In the above 3 table design, it would be possible to add a color filed to Part holding the unique color of that part. Updates to that color would then refer to all those Parts.

5.    What is normalization?

Database Normalization, or simply normalization, is the process of organizing the columns (attributes) and tables (relations) of a relational database to reduce data redundancy and improve data integrity. Normalization is also the process of simplifying the design of a database so that it achieves the optimum structure. 

6.    What are the advantages of normalization?

Reduces Data Duplication; Groups Data Logically; Enforces Referential Integrity on Data

7.    What are the disadvantages of normalization?

Slows Database Performance; Requires Detailed Analysis and Design; 

8.    What is nosql?

A NoSQL database provides a mechanism for storage and retrieval of data which is modeled in means other than the tabular relations used in relational databases. The data structures used by NoSQL databases (e.g. key-value, wide column, graph, or document) are different from those used by default in relational databases, making some operations faster in NoSQL.

9.    How does nosql address data anomalies (hint: trick question)

In NoSQL, you don't design your database based on the relationships between data entities. You design your database based on the queries you will run against it, so it doesn't have those anamalies like SQL. 


12.    What kind of applications should use nosql. Give an example and explain.

If optimizing to increase flexibility and scalability, then NoSQL

13.    What kind of applications should not use nosql? Give an example and explain.

If optimizing to reduce the long term maintenance cost of highly structured somewhat static data, then SQL;

