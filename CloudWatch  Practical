# CloudWatch Practical


** Create a SNS Topic **
1. go to sns
2. click on Create Topic
3. -- click on next step
a. select "standard"
b. name topic
c. hit on create Topic

* Create Subscription *
1. After creating topic scroll down and click on "Create Subscription"
a. select protocol
b. give your "Email"
c. hit on create Subscription
d. open your email and click on confirm [for confirming that email is yours]



** ALARMS CREATION **
1. Go to cloudwatch -- click on Alarm
 
2. -- Click on "Create Alarm"
a. -- click on select matric
   -select the service of which you have to create alarm [EC2]
   -copy instance id of your EC2
   -go inside "per instance Matric" and then peaste your instance id there
   -scroll down and select "CPUUtilization"
   -click on select matric
   -- In second step you just need to setup time according to your need
b. select an SNS Topic and dont change anything else [go to next page]
c. Name Your "Alarm"
d. hit on create alarm

3. Go to EC2 
a. scroll down and click on "Monitoring"
b. -- click on Manage Detailed Monitoring 
   -- Enable the detailed monitoring and confirm

** Increase Trafic For Alarm Working **
1. SSH the instance
2. Install Stres Software [to increase the trafic]
a. sudo yum install stress -y [command for installation]
b. stress --cpu 8 --timeout 60 [command for increasing traffic]

2. Monitor your EC2 

3. Continue to fire command untill your trafic reaches to limit you have seted while setting matric

4. You must receive an Email after your trafic increasing 


** DELETE EACH AND EVERY THING AFTER PERFORMING PRACTICAL **
