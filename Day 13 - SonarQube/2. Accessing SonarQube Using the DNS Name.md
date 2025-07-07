### Accessing SonarQube   Using the DNS Name  

Follow these steps to access SonarQube  using the DNS name.  

#### Step 1: Create the Target Group  
Create a target group and add the instance with port `9000`. Set the health check path to `/`.  

- **Target Group Name:** `sonarqube-tg`  

#### Step 2: Create the Load Balancer  
Create an  load balancer and add listeners for both HTTP (`80`) and HTTPS (`443`).  

- **Load Balancer Name:** `sonarqube-alb`  

#### Step 3: Create the A Record in Route 53  
Create an A record in Route 53 to point to the sonarqube  load balancer.  

- **Record Name:** `sonarqube.techworldwithmurali.in`  

#### Step 4: Access sonarqube  
You can access sonarqube using the following URL:  

- **URL:** https://sonarqube.techworldwithmurali.in


🎉 **Congratulations! You have successfully accessed sonarqube using the DNS name.** 🚀
