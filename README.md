Project: Build CI/CD Pipeline for Blue/Green Deployment
=======================================================

About
-----
From Udacity:
> In this project you will first create a pipeline that spins up 3 servers and uses Ansible to deploy an application on the servers. Once those servers are running, you will create another pipeline to confirm that servers were configured as expected. You’ll then uses the "Blue/Green" deployment strategy to deploy additional features to those servers.

Supporting Courses:

 * Build CI/CD Pipelines, Monitoring & Logging
 
Screenshots
-----------

Setup IAM credentials properly
![IAM Credentials](screenshots/screenshot-01.png?raw=true)

Launch EC2 instance
![EC2 Instance](screenshots/screenshot-02.png?raw=true)

Jenkins is installed and running
![Jenkins installed](screenshots/screenshot-03.png?raw=true)

Blue Ocean is enabled
![Blue Ocean enabled](screenshots/screenshot-04.png?raw=true)

Barebones Pipeline is added
![Pipeline added](screenshots/screenshot-05.png?raw=true)

Publishes the static site to S3
![Published static site](screenshots/screenshot-06.png?raw=true)

Linter catches issues with HTML
![Linter failure](screenshots/screenshot-07.png?raw=true)

Jenkinsfile is demonstrated
![Pipeline completes successfully](screenshots/screenshot-08.png?raw=true)

Grading (by Udacity)
--------------------

Criteria                              |Highest Grade Possible  |Grade Recieved
--------------------------------------|------------------------|--------------------
AWS Setup                             |Meets Specifications    |Meets Specifications
Running Jenkins                       |Meets Specifications    |Meets Specifications
Working Pipeline                      |Meets Specifications    |Meets Specifications
