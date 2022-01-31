# Vprofile-Project

A demo application deployed on AWS with the help of Elastic Beanstalk, CloudFront, Route 53, Amazon Certificate Manager, Amazon RDS, Amazon ElastiCache. This project overcomes the limitations of the Lift and Shift strategy by moving from Infrastructure as a Service(IaaS) to Platform as a Service(PaaS) and Software as a Service(SaaS). Cloud Managed services such as Amazon RDS, Elasticache, CloudFront, Elastic Beanstalk are used.

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

![Screenshot (330)](https://user-images.githubusercontent.com/68735863/151853553-39ebc9a6-bede-4eb5-8e90-f805dbce7233.png)

![Screenshot (329)](https://user-images.githubusercontent.com/68735863/151853574-6e2985c0-456d-470f-a0ca-a6785221ef75.png)

![Screenshot (325)](https://user-images.githubusercontent.com/68735863/151853600-f666dcbb-8cb6-4686-ada5-4809a5200da2.png)

![Screenshot (326)](https://user-images.githubusercontent.com/68735863/151853622-1c5b84da-cb6f-44ff-afb3-24c7aee761b9.png)

![Screenshot (327)](https://user-images.githubusercontent.com/68735863/151853645-94cc96f3-201b-458c-b883-018f7809fc46.png)

![Screenshot (328)](https://user-images.githubusercontent.com/68735863/151853658-5b0b991a-d9d2-42ed-8194-ad4f6fd79e1e.png)
