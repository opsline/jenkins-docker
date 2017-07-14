# jenkins-docker

This project provides custom Jenkins docker images.

# Jenkins
This image is based on `jenkinsci/jenkins:lts`.

It overrides the starup script injecting code that sets `hudson.TcpSlaveAgentListener.hostName` property to EC2 instance IP address (reading the metadata). When running Jenkins in AWS, Jenkins is often behind an ELB, is addressed by the public IP address, or running inside ECS cluster. Setting this property to the private address allows slaves (either instances or ECS tasks) to easily access the master.

# Jenkins slave
THis image is based on `jenkinsci/jnlp-slave:latest`.

It installs `docker` and `awscli`.
