# dbms-lab
CREATE TABLE Location (        LCode number (3) PRIMARY KEY, Name varchar2 (10));  
 ​  
 ​CREATE TABLE Job (        JCode number (3) PRIMARY KEY, Name varchar2 (10));  
 ​  
 ​CREATE TABLE Dept (        Deptno number (2) PRIMARY KEY,  Name varchar2 (10),   
 ​Location number (3)   REFERENCES    LOCATION (LCODE));  
 ​  
 ​  
 ​CREATE TABLE Employee(        Empno number(2) PRIMARY KEY, Ename varchar2(10),    
 ​Job number(3) REFERENCES   JOB(JCODE),   
 ​Mgr_no number(2) REFERENCES EMPLOYEE(EMPNO),  
 ​Hiredate date, Salary number(10), Commission number(8),    
 ​Deptno number(2) REFERENCES   DEPT(DEPTNO));  
 ​  
 ​INSERT INTO Job VALUES (667,'Clerk');  
 ​INSERT INTO Job VALUES (668,'Staff');  
 ​INSERT INTO Job VALUES (669,'Analyst');  
 ​INSERT INTO Job VALUES (671,'Manager');  
 ​INSERT INTO Job VALUES (672,'President');  
 ​  
 ​  
 ​INSERT INTO location VALUES (122,'Kakinada');  
 ​INSERT INTO location VALUES (124,'Hyderabad');  
 ​INSERT INTO location VALUES (123,'Bangalore');  
 ​INSERT INTO location VALUES (167,'Vijayawada');  
 ​  
 ​  
 ​INSERT INTO dept VALUES (10,'Accounting',122);  
 ​INSERT INTO dept VALUES (20,'Research',124);  
 ​INSERT INTO dept VALUES (30,'Sales',123);  
 ​INSERT INTO dept VALUES (40,'Operations',167);  
 ​INSERT INTO dept VALUES (12,'Research',122);  
 ​INSERT INTO dept VALUES (13,'Sales',122);  
 ​INSERT INTO dept VALUES (14,'Operations',122);  
 ​INSERT INTO dept VALUES (23,'Sales',124);  
 ​INSERT INTO dept VALUES (24,'Operations',124);  
 ​INSERT INTO dept VALUES (34,'Operations',123);  
 ​INSERT INTO dept VALUES (43,'Sales',167);  
 ​  
 ​  
 ​INSERT INTO employee VALUES (1,'Venkat',672,null,'01-FEB-2006',1200000,10000,40);  
 ​INSERT INTO employee VALUES (2,'Nirmala',671,1,'02-MAR-2007',800000,50000,20);  
 ​INSERT INTO employee VALUES (3,'Pradeep',669,1,'10-OCT-2005',1000000,null,40);  
 ​INSERT INTO employee VALUES (4,'Srinivas',669,1,'08-MAY-2005',1000000,null,30);  
 ​INSERT INTO employee VALUES (5,'Krishna',668,2,'09-OCT-2005',500000,20000,12);  
 ​INSERT INTO employee VALUES (6,'Deepa',668,3,'09-NOV-2007',600000,null,23);  
 ​INSERT INTO employee VALUES (7,'Keerthi',668,4,'05-JUN-2006',600000,null,24);  
 ​INSERT INTO employee VALUES (8,'Aravind',671,1,'21-JAN-2006',800000,600000,30);  
 ​INSERT INTO employee VALUES (9,'Srikanth',668,8,'18-NOV-2006',400000,500000,34);  
 ​INSERT INTO employee VALUES (10,'Suresh',667,3,'12-DEC-2008',120000,null,23);  
 ​INSERT INTO employee VALUES (11,'Rahul',667,9,'11-MAR-2008',80000,null,30);  
 ​INSERT INTO employee VALUES (12,'Kumar',667,4,'16-MAR-2008',120000,null,20);  
 ​  
 ​  
 ​QUERIES:  
 ​select  empno,salary,salary+commission from Employ   
 ​EMPNO         SALARY         SALARY+COMMISSION  
 ​1         1200000         1210000  
 ​3         1000000            
 ​4         1000000            
 ​6         600000            
 ​7         600000            
 ​8         800000         1400000  
 ​9         400000         900000  
 ​10         120000            
 ​11         80000           
 ​2)  
 ​select empno,ename from Employ where commission is not null  
 ​EMPNO         ENAME  
 ​1         Venkat  
 ​8         Aravind  
 ​9         Srikanth   
 ​  
 ​3)  
 ​select empno,ename from Employ where commission is null  
 ​EMPNO         ENAME  
 ​3         Pradeep  
 ​4         Srinivas  
 ​6         Deepa  
 ​7         Keerthi  
 ​10         Suresh  
 ​11         Rahul   
 ​  
 ​4)  
 ​select ename from Employ where job=667 and salary>10000  
 ​ENAME  
 ​Suresh  
 ​Rahul   
 ​  
 ​5)  
 ​select ename from Employ where ename like 'S%'  
 ​ENAME  
 ​Srinivas  
 ​Srikanth  
 ​Suresh   
 ​  
 ​6)  
 ​select ename from Employ where ename like '%s'  
 ​ENAME  
 ​Srinivas   
 ​  
 ​7)  
 ​  
 
