
# Autoscalling Practical :

1. Launch an EC2 Instance
a. install and enable nginx
b. create a html page there [try to add text as Version1] 
c. run html page on browser

2. Generate AMI  of the same instance
a. give name yo the instance like V1

3. Create Autoscalling Group
A. -- click on create Autoscalling Group
a. name your Autoscalling Group [e.g myasg]
b. click on launch template

** Autoscalling Template Creation **
1. Name your template [try to keep it same as that of Autoscalling Group name and add template word e.g myasgtemplate]
2. Give version to your template [according to your version]
3. select your AMI 
4. select instance type [t2.micro]
5. select key pair
6. security group [you can either create or use default]
7. add security rule [port number 80]
8. hit on create button

** TEMPLATE IS CREATED **



c. select the template you launched
d. go to next page

B. Choose Instance Launch Options
a. select availablity zones  [ select a and b public zones as we have selected t2.micro ]
b. keep everything as it is and move to next page

C. Integrate with other services
a. -- select attach to new load balancer
b. keep it internet facong
c. select create a target group
d. enable all (3) health check

D. Group Size 
a. set size of Desire, Min and Max
b. select target tracking scalling policies
c. no policy in Instance maintaining policy and dont change anything go to next page

E. Add Notificatio if you want to go to next page and hit on create button


4. Now go to load balencer 
a. coopy your DNS of your loadbalencer and paste it into your browser
b. your page must be visible here [the html page you created with V1 text]

5. If Page is not visible
a. check if port number 80 is in security group or not
b. make sure your nginx was enable at the time of creating AMI
c. check the target group of load balencer if target are present or not

6. Fire the stress command in your terminal to check if your autoscalling is working or not

7. After Everything delete Everything


