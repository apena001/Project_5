# Client-Server-Architecture-Using-A-MySQL-Relational-Database-Management-System
### Example of Client-Server communicatation in action.
Open up your Ubuntu or Windows terminal and run curl command:

`curl -Iv www.raassafety.com`

![Alt text](Images/raams.png)

### TASK – Implement a Client Server Architecture using MySQL Database Management System (DBMS).

### 1.Create and configure two Linux-based virtual servers (EC2 instances in AWS).

 ![Alt text](Images/Ouest1.png)

 ### 2.On mysql server Linux Server install MySQL Server software.

 `sudo apt update`
 
 ![Alt text](Images/sudoUpdate.png)

 `sudo install mysql-server`
 
 ![Alt text](Images/mysql_server.png)

 ### 3.On mysql client Linux Server install MySQL client software.

 `sudo apt update`

 `sudo install mysql-client`
 ![Alt text](Images/mysql_server.png)

 MySQL server uses TCP port 3306 by default, so you will have to open it by creating a new entry in ‘Inbound rules’ in ‘mysql server’ Security Groups.
 ### 3.Mysql server uses TCP port 3306.On the security group, add inbound rules using port 3306.

 ### 4. Configure MySQL server to allow connections from remote hosts..Replace ‘127.0.0.1’ to ‘0.0.0.0’

 `sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf`

 ![Alt text](Images/vi.png)

 ### 5.Restart the server.

 `sudo systemctl restart mysql`

 ### 6.Create a user and password from the defunlt on mysql.

 `sudo mysql -u root -p`

 mysql>`create user "ola"@"%" identified by "password";`
 
 ![Alt text](Images/Screenshot%202023-05-28%20124151.png)

 ### 7.From mysql client Linux Server connect remotely to mysql server Database Engine without using SSH. You must use the mysql utility to perform this action.

 `mysql -h 172.31.44.64 -u ola -p`
 
 ![Alt text](Images/result.png)