At first, we intend to create a PHP application where we require the RDS database to be 
communicated with the PHP application. Our first step towards this process is to first inspect the 
environment by checking the Example VPC, Subnets, Security groups, AMI, and instances. We 
understand that we will have two Private subnets and two public subnets. 4 security groups namely 
ALBSG, Bastion SG, Inventory App SG, and exampleDB. Next, we create a MySQL RDS 
database instance and name the database as exampleDB in accordance with the example VPC. We 
create a standard database service in AWS. Here, I remembered to note my DB name, username, 
password, and database instance identifier. I allocated 20GB of storage. We create a password 
authenticated database. 

After successfully creating a database, our next step was to create a Cloud9 environment. 
We navigate to create a Cloud9 environment in the Amazon Linux 2 platform to ensure direct 
access to the environment. The next task is to create a LAMP (Linux, Apache, MySQL, PHP) web 
server on Amazon Linux2 on the Cloud9 instance. We follow a series of sudo commands in Linux
to install MariaDB and enable the httpd MariaDB server. Here, we need to properly install the 
httpd-MariaDB server and enable it. Then, we download the required PHP code and see if all the 
files are downloaded. We unzip and reload the files in the directory. We Check the public IP of 
the Cloud9 EC2 instance and follow it. The cloud9 will set up an EC2 instance and open port 80 
in the security group. We can access the database that we imported into Cloud9 by copying the 
public IP from the EC2 instance and pasting it into the web browser. We get the required web 
application and under queries, we check if we can access any database tables like population, GDP, 
or mobile phones. At first, we won’t be able to view it as there is no value entered in the data but 
after successful installation of the httpd-MariaDB maria server and linking them to the correct 
parameters in the system manager with proper username, password, endpoint, and DB we will be 
able to access the Queries in the data.

We create an AMI image of the Cloud9 instance for Autoscaling. We follow two basic 
rules while creating load balancers and auto-scaling groups for autoscaling we follow the Private 
subnets and for Load Balancers, it is Public Subnet. Finally, configure the AWS systems manager 
using the parameter store and double-check that everything was in functioning correctly and 
performing as intended. I can link to the ec2 instance by using the load balancer's DNS name, and 
it responded fast. I was not able to successfully view my database from the Domain name under 
queries. I went back to my Load balancer and updated the network settings from Private subnet to 
public subnet. In the end, I refreshed the query again to view the population, Mobile Devices, and 
various other tables present in the database and was able to view them perfectly. 
