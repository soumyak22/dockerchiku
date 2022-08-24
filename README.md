
---
version: '3.3'
services:
myjenkins:
 image: jenkins:jenkins
 ports:
  - 8080:8080
qaserver:
 image: tomcat
 ports:
  - 7070:8080
 links:
  - myjenkins:jenkins
prodserver:
image: tomee
ports:
 - 6060:8080
links:
 - myjenkins:jenkins 
