## VPC PEERING PRACTICAL

1. TAke Two VPC with differnet CIDR BLOCK 

2. Go To Peering Connection
A. Click on create peering connection
a. name your connection
b. select your VPC [any resion]
c. -- select another VPC to peer with
d. -- select region 
e. enter your VPC ID
f. hit on create button

B. go to another region you have selected
a. go to peering connection
b. select the peer 
c. go to actions and "Accept Request"

C. by now status should be active

3. Go to respective region 
a. Launch an EC2 instance 
b. select the VPC you have peered 
c. select public subnet
d. "Enable" auto assing public IP
e. Do this in both region

4. ssh any instance [better if we choose acceptor]
A. Install nginx
a. start nginx
b. go to html directory
c. create a html page
d. paste  public IP on browser your page must be visible

5. Add Rout In both VPC 
A. check the subnet  
a. click on ec2
b. -- click on subnet id
c. -- again click on subnet id
d. scroll down to Route Tables
e. -- click on route table id
f. -- click on route table id again
g. go to edit rout
h. add route [add CIDR BLOCK of Another VPC] select peering connection
i. save rules
B. Do the same on both sides [on both VPC]

6. go to another instance and do ssh
A. curl http://PvtIp/page.name [pvt IP of VPC2][VPC1 is in which we created html page]
B. Your page content must be visible here
