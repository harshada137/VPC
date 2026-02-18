# Load Balencing Practical :-
1. You can either create new VPC or use default one

2. Create Security Group [All instance should have same security group]

3. Luanch an EC2 instance
a. select security group you had created

4. Install Nginx in first instance
a. enable nginx [sudo systemctl enable nginx]
b. remove index.html in html directory 
c. make your own html page [with any normal text]
d. copy paste your public IP in Browser [Youe index.html page must be visible there]
e. if page is not visible then check security rules [http and https must be include]

5. Create AMI of your EC2
a. select EC2 and go to actions
b. -- select Image and Template
c. name your AMI 
d. hit on create Image

6. Launch Instance From AMI
a. select AMI 
b. --click on Launch Instance From AMI
c. change number of instance from one to '2'
d. name instance [give it second]
e. select key pair [use as same as that of your previous EC2]
f. select security group [use as same as that of your previous EC2]
g. change name of one instance from 'second' to 'third'


7. Lauch Load Balencer
a. click on create load Balencer
b. -- you will see four types of load balencer 
c. select "Application Load Balencer" [you can select acording to your need]
d. name your Load Balencer 
e. -- select internet facing 
f. -- select IPV4 
g. Network Mapping
   -- select VPC
   -- select Two zones [a and b]
h. Select sequrity group [this one is differnt from that of EC2 ]
i. Listenrs and Routing 
   -- click on create "target group"
   -- Instance is selected by Defaul
   give name to target group
   Port [let it be as it is]
   -- HEALTH CHECK [if your page is index.html then let the '/' as it is otherwise change it to your page name]
   -- click on next
   -- select instances
   -- hit on create target group
j. refresh the target group [dont refresh whole page]
   -- select target group you just created
k. dont change anything else
l. click on create load balencer.

8. Add Security Group to Load Balencer
a. click on Load Balencer
b. go to security group
c. -- click on edit Inbond Rule [add http and https]

9. Change html page
a. go to second and third server And then change the html page [you can write first secnd and third in that page according to instance]

10. Now refresh the browser [in which we have paste our public IP]
  
** YOU CAN SEE THE ROUND ROBBIN EFFECT THERE ** 

