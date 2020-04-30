# OnlineExam
Project on Examination system using JDBC

OBJECTIVE
The Objective of this application is to provide a platform where students can take their tests of any particular subject in Multiple Choice questions. As the name suggests the application should work online ,but in the project from which the idea is been taken does not work online .so to make the project work online so that multiple users can access this concurrently and can submit their solutions of the test and can generate their marks in the output and store the result in the database there were multiple ways  to do so here it is done using Java database Connectivity and Mysql as the Relational database making it a Relational Database Management System .

USER’s OF SYSTEM

This System can be used by the students who have to appear in the examination or test also by the Teachers and Facultys who have to Evaluate the marks of the Students. The system contains a database where there are tables which contains the Marks of the student along with their Enrollment Numbers. The same database can contain multiple tables containing information of students according to their Enrollments so that table can relate with this marks table and can communicate with this both table can combine and join to give the result as the table having student data with their marks.

TOOLS USED

Tools used to make this system are

1.	NetBeans 8.0.1
2.	Mysql  5.5

Language:Java,Mysql

Front End:Swing

Backend:Mysql

HOW TO INSTALL THIS PROJECT
This Folder has a Text document copy the text from that text document and paste that into Mysql command client and there is another folder that contains the Java files copy that folder and paste that folder in the C:/documents/NetBeansProject
HOW PROJECT WORKS
The project is very simple in architecture and also in use, it Starts directly from questions as the questions begin in the first question when the submit button is clicked the connection with mysql is initiated and a Temporary Table called counter with a single column Marks is created and if the answer to first question is correct the value for marks is initialized with 1 or if the answer is wrong the value is assigned 0 and query is executed after execution the window for question number two pops up


![](https://github.com/VatsalParekhgit/OnlineExam/blob/master/q1.PNG)

After the submit button on question two is pressed the marks column in counter gets updated and the update query executes and increases the marks by 1 from initial value if the answer submitted is wrong then nothing is done to the table and the table remains same, this logic can be applied to as many questions as teacher wants and can be used without any issue

![](https://github.com/VatsalParekhgit/OnlineExam/blob/master/q2.PNG)

After all questions answers are submitted and the submit on the last question is clicked a new window pops that asks the user to enter their unique Enrollment Number if the entry from that roll number is already present then the message box pops that the  record is already present and program terminates if not then the record is inserted with given enrollment number and the marks taken from Counter table by using the INSERT SELECT CLAUSE and then the temporary table COUNTER is deleted using DROP command.

![](https://github.com/VatsalParekhgit/OnlineExam/blob/master/reg1.PNG)

![](https://github.com/VatsalParekhgit/OnlineExam/blob/master/reg2.PNG)





CLASS DIAGRAM



![](https://github.com/VatsalParekhgit/OnlineExam/blob/master/OnlineExaminationSystem-ClassDiagram.JPG)




Data Flow Diagram



![](https://github.com/VatsalParekhgit/OnlineExam/blob/master/5e1bff407fba3.jpg)


ER Diagram


![](https://github.com/VatsalParekhgit/OnlineExam/blob/master/5e1bff3fefa38.jpg)

Activity Diagram


![](https://github.com/VatsalParekhgit/OnlineExam/blob/master/Examination%20Management%20System_4.jpeg)


Sequence Diagram

![](https://github.com/VatsalParekhgit/OnlineExam/blob/master/sequnce-diagram-for-online-examination-system-6-638.jpg)
