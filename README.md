# TASK
##task which are given everyday........

# 1-08-2023
MY SQL 
create one instance.use any ami (ubuntu).then inside that instance install my sql -[sudo apt update] [sudo apt install mysql-server].
after installing my sql, create a user (%) with password -[create user "(type your username)"@"(hostname(local,%))" IDENTIFIED BY "(type your password here)"].
after creating user, Access the user from your local system and make some tables or data in it....

# SOLUTION-----------
### first of all we have to create an instance using ubuntu AMI.
### launch the instance and connect it through ssh on terminal.
```
ssh -i "your key" ubuntu@(your publicip).compute-1.amazonaws.com
```
### after connecting the instance, type -
```
(sudo apt update)
```
### in cmd in terminal.
### install my sql server,
### type - 
```
sudo apt install mysql-server
```
type (sudo mysql) to use mysql services
to create a user type these command given below-
show databases;
use mysql;
use tables;
describe user;
select user from user;
CREATE USER "(type your username)"@"(hostname(local,%))" IDENTIFIED BY "(type your password here)" 
after creating user in mysql press ctrl+D and exit from mysql.
to use your user which you created recently,
type (mysql -u your_username -p)
we have to remember that sql services run on port 3306 so we have to create INBOUND and OUTBOUND RULES to pass the traffic.
click on security groups tab > security > you can see inbound rules tab.click on right side of the tab to edit inbound rules.
select mysql/aurora for type and 3306 port > choose MY_IP for CIDR. and then save it.
same we have to do with OUTBOUND RULES >select mysql/aurora for type and 3306 port > choose MY_IP for CIDR. and then save it.
now we have to open a new terminal on our LOCAL COMPUTER to access the mysql user which we created on instance.
to access the user we created on instance we have to type this command on our local computer terminal.
type- mysql -u (username) -h (ip address) -P (port 3306) -p
then ENTER password.
somehow we are unable to access it so we have to change some permissions in mysql.conf.d
to access mysql.conf.d path is - /etc/mysql/mysql.conf.d
```
