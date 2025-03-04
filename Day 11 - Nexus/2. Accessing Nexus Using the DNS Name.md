### Accessing Nexus Artifactory Using the DNS Name  

Follow these steps to access Nexus Artifactory using the DNS name.  

#### Step 1: Create the Target Group  
Create a target group and add the instance with port `8081`. Set the health check path to `/`.  

- **Target Group Name:** `nexus-tg`  

#### Step 2: Create the Load Balancer  
Create an load balancer and add listeners for both HTTP (`80`) and HTTPS (`443`).  

- **Load Balancer Name:** `nexus-alb`  

#### Step 3: Create the A Record in Route 53  
Create an A record in Route 53 to point to the Nexus Artifactory load balancer.  

- **Record Name:** `nexus.techworldwithmurali.in`  

#### Step 4: Access Artifactory  
You can access Artifactory using the following URL:  

- **URL:** https://nexus.techworldwithmurali.in


🎉 **Congratulations! You have successfully accessed Nexus using the DNS name.** 🚀
