------------------------------------------------------------------------------------------------------------
-------------------------------- Project Developed by // TUSHAR SRIVASTAVA ---------------------------------
--------------------- Hire Me // Mobile No.: 8299357488 && Email: tusharrbl@gmail.com ----------------------
---------------------------- Portfolio // https://www.tusharsrivastava.tech --------------------------------
-------------------------- LinkedIn // https://www.linkedin.com/in/tusharrblgh -----------------------------
----------------------------- GitHub // https://www.github.com/tusharrblgh ---------------------------------
------------------------------------------------------------------------------------------------------------
------------------------------ ⚠️ Legal Notice – Copyright Warning (India) --------------------------------
-------- This project is protected under the Copyright Act, 1957 (as amended) and other applicable ---------
--------------------------------- intellectual property laws of India. -------------------------------------
------------------ Any unauthorized copying, reproduction, modification, distribution, or ------------------
-------------------------- commercial use of this work, in whole or in part, -------------------------------
------------ without the explicit written permission of the author is strictly prohibited. -----------------
------------------------------------------------------------------------------------------------------------


------------------------------------------------------------------------------------------------------------
--------------------------------------------- Review Phase - 1 ---------------------------------------------
Network Environment:
1. Private - Resources (We are going to work with) and Application (We are going to deploy).
2. Isolated - No outside Entity should be able to access it.
3. Secure - Make sure deployment and everything is secure.

Kubernetes cluster and other deployment cluster where we are going to deploy our application.

Create Virtual Machines (instances) on Amazon Web Services (AWS) using Terraform.
------------------------------------------------------------------------------------------------------------


------------------------------------------------------------------------------------------------------------
Total No. of Virtual Machines (instances) you have to create: 07

Links of user-data code written using bash script:
1st Virtual Machine (Instance Name: Kubernetes-Master): 
2nd & 3rd Virtual Machines (Instance Name: Kubernetes-Slave-1 & 2):
4th Virtual Machine (Instance Name: SonarQube):
5th Virtual Machine (Instance Name: Nexus):
6th Virtual Machine (Instance Name: Jenkins):
7th Virtual Machine (Instance Name: Monitoring):
------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------------------------------------------
Allowed Ports in Security Group:
1. SSH
   ingress // [This is an inbound rule. It allows traffic into the resource (like an EC2 instance in AWS)]
    from_port = 22 // [ The starting port number in the rule (used when protocol is TCP/UDP)]
    to_port = 22 // [The ending port number in the rule (used when protocol is TCP/UDP)]
    protocol = "tcp" // [The rule applies to the TCP protocol]
    cidr_blocks = ["0.0.0.0/0"] // [This means the rule allows traffic from any IP address in the world.
                                    This is wide open to the public internet]

2. Also for Mail (Company Uses Most)
   ingress
    from_port = 25
    to_port = 25
    protocol = "tcp"
    cidr_blocks = ["0.0.0.0/0"]

3. HTTP
   ingress
    from_port = 80
    to_port = 80
    protocol = "tcp"
    cidr_blocks = ["0.0.0.0/0"]

4. HTTPS
   ingress
    from_port = 443
    to_port = 443
    protocol = "tcp"
    cidr_blocks = ["0.0.0.0/0"]

5. Send Mail Notification from Jenkins Pipeline to our Mail
   ingress
    from_port = 465
    to_port = 465
    protocol = "tcp"
    cidr_blocks = ["0.0.0.0/0"]  

6. Use in Setup K8S Cluster
   ingress
    from_port = 6443
    to_port = 6443
    protocol = "tcp"
    cidr_blocks = ["0.0.0.0/0"]

7. Most Deployment happen between these Port Range like 8080 for Jenkins, 9000 for Sonarqube 
   ingress
    from_port = 3000
    to_port = 10000
    protocol = "tcp"
    cidr_blocks = ["0.0.0.0/0"]

8. Use for Deployment for Application
   ingress 
    from_port = 30000      
    to_port = 32767
    protocol = "tcp"
    cidr_blocks = ["0.0.0.0/0"]

9. egress // [This is for outbound traffic (leaving your instance)]
    from_port = 0
    to_port = 0
    protocol = "-1" // [-1 means all protocols (TCP, UDP, ICMP, etc)]
    cidr_blocks = ["0.0.0.0/0"]
------------------------------------------------------------------------------------------------------------