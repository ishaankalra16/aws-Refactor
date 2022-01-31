# Vprofile-Project

A demo application deployed on AWS with the help of Elastic Beanstalk, CloudFront, Route 53, Amazon Certificate Manager, Amazon RDS, Amazon ElastiCache. This project overcomes the limitations of Lift and Shift strategy by moving from Infrastructure as a Service(IaaS) to Platform as a Service(PaaS) and Software as a Service(SaaS). Cloud Managed services such as Amazon RDS, Elasticache, CloudFront, Elastic Beanstalk are used.

# Prerequisites
#
- JDK 1.8 or later
- Maven 3 or later
- MySQL 5.6 or later

# Technologies 
- Spring MVC
- Spring Security
- Spring Data JPA
- Maven
- JSP
- MySQL

# Architecture 

<img width="960" alt="Screenshot (323)" src="https://user-images.githubusercontent.com/68735863/151782790-87adc898-0b56-4248-ba92-335869b3fedb.png">

Users can view the application with the help of a URL. which will be resolved to an endpoint from Amazon Route 53. The endpoint will be of Amazon CloudFront content delivery network, which will cache many things so as to serve the global audience. From there, the request will be redirected to an application load balancer which will be part of the Elastic Beanstalk service. The ALB will further pass the request to the EC2 instances which will be configured as an auto-scaling group, and also the part of the Elastic Beanstalk application. Amazon CloudWatch alarms will be used to monitor auto-scaling groups and will scale out/in based on the requirement. The Artifact will be stored in an S3 bucker and any artifact can be deployed with the click of a button. Instead of using Rabbit MQ, Memcached and MYSQL, we will be using services offered by amazon for our backend services such as AmazonMQ, ElastiCache, and Amazon RDS.

# Database
Here,we used Mysql DB 
MSQL DB Installation Steps for Linux ubuntu 14.04:
- $ sudo apt-get update
- $ sudo apt-get install mysql-server

Then look for the file :
- /src/main/resources/accountsdb
- accountsdb.sql file is a mysql dump file.we have to import this dump to mysql db server
- > mysql -u <user_name> -p accounts < accountsdb.sql

# Screenshots

![Screenshot (330)](https://user-images.githubusercontent.com/68735863/151782882-c6da1e9f-d04b-4454-92f1-d4d4ff1f351f.png)

![Screenshot (329)](https://user-images.githubusercontent.com/68735863/151782922-d98aead5-6146-4ea1-84aa-e23bf919938c.png)

![Screenshot (325)](https://user-images.githubusercontent.com/68735863/151782963-ecabc7ef-8175-44d1-9464-40a79150e62c.png)

![Screenshot (326)](https://user-images.githubusercontent.com/68735863/151782982-96d7fe44-0de3-4f8d-83fd-97888f28efbe.png)

![Screenshot (327)](https://user-images.githubusercontent.com/68735863/151783047-101f0eb5-9710-4953-a80c-bf641340c987.png)

![Screenshot (328)](https://user-images.githubusercontent.com/68735863/151783063-360f3307-c7fa-40e7-8a36-1de49ca47de3.png)

