# aganitha_fullstack

Problem Statement:
System design
consider the following problem. 

Assume that you are processing a stream of files for students. Each file contains the records for many students. Each record contains the student id with scholarship money. Naturally, a student may have more than one scholarship and each student is enrolled in one college. 

Consider the following system: 
1. It takes a record, determines which student the record belongs to, looks up the college that the student belongs to and sends the record to the respective college program.
2. For each college, a different system keeps track of the following:
- Total scholarship amount they should be receiving from the donor
- Min, max, and average scholarship amount per student in that college.
- Stats about scholarships (such as grant counts and cumulative amounts), for range of grant amount: 0 - 10K, 10K-20K, 20K-30K, 30K-40K, 40K-50K and > 50K. 

Modules:
•	Student Module
•	College Admin/Staff
•	Super Admin
USECASE Diagram:
 
Class Diagram:
 
In Addition to it:
We have a table which consist all the sponsors details along with the amount received from them, which is linked to scholarship table and admin table.
System Flow:
 
 


 



The system is initialised with a student to college mapping file. Suppose in the middle of processing, we get an update to the mapping file. Can your design accommodate such updates? Specifically address the following: a) How does the system allow for such updates? Where does the system store the mapping data? b) How do the college systems update all the numbers they are keeping track of?

Solution:
When system is initialized with a student to college mapping file, 
A)	Yes, we can achieve that by, system needs to load that data into a temporary storage for mapping and even if any changes will happen then it doesn’t affect the persistent data. So that we can achieve the data integrity.
B)	When the computation done at end/server side, then it should communicate with the college system and give the access along with the details to update their data, it has to be done in periodically or if any change occurs in the end/server side. With this we can update the data without any in-consistencies and can achieve data integrity.
