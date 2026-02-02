# VPC PRACTICAL -- With existing VPC 

# In VPC
1. Go To VPC -- Click on Your VPC
   [Here You will see your default vpc and also the resurce map (It shows how your VPC resources (like subnets, route tables, internet gateways, etc.) are connected. It helps you quickly            
   understand the architecture and relationships within your VPC.)]

2. Go To Subnet -- CLick on Subnet 
   [You will see default subnets with cidr block, Id's of connected default route table and NACL]

3. Create Subnet
   a. select VPC Id
   b. name subnet [name subnet according to its use e.g. if you want to keep subnet private or public the mension it in the name so that you will select correct vpc at the time of    
      assinging route table] [Use camel case formate for naming e.g. defaultVpcCustomPublicSubnet]
   c. select availability zone [try to select diff zone for diff subnet]
   d. write cidr block [vpc cidr will be given there ] [you can website like cidr calc for cidr block writting]
   e. click on create subnet
   f. You can see this subnet in resource map of VPC 

4. Create Another Subnet [always try to lauch two subnet of same name, in which one will be publick and another one will be public] 
   [i.e. name of this subnet will be defaultVpcCustomPvtSubnet]

5. Create Route table
   a. go to route table [-- click on route table (here you see routes in which you will see two default routes one is connected to Internet Gateway and onother is local one)]
   b. click on create route table
   c. Name the Route table [name Route table according to its use e.g. if you want to keep Route table private or public the mension it in the name so that you will select correct vpc at  
      the time of assinging subnet] [Use camel case formate for naming e.g. customPvtRouteTable]
   d. select VPC 
   e. click on create route table

6. Attach Subnet To Created Route Table
 METHOD 1st :-
   a. go to route table you want to assign and then select "Subnet Associations"
   b. go to edit subnet association
   c. and then associate your subnet from there

 METHOD 2 :-
   a. go to subnet
   b. click on subnet you want to assign to the route table
   c. go to "Route Table"
   d. Edit route table association
   e. select route table you want to assign and click on save


# In EC2 

7. Go TO Lauch an Instance
   a. name instance [name it according to its work e.g. pvtsubnet]
   b. select OS [amezon linux most of the time]
   c. create key pair or you can use existing one
   d. --click on edit network setting
   e. select vpc
   f. select subnet [defaultVpcCustomPvtSubnet
   g. auto assign publick ip "Enable"
   h. hit on launch instances


8. Assign Internet Gateway to Route table
   a. click on route table
   b. go to "Edit routes"
   c. -- click on add route 
   d. Enter 0.0.0.0/0
   e. select target i.e. Internet Gateway
   f. select igw Id
   g. save changes

9. Now Do SSH in Terminal 
   [ Your Instance Should be Working Properlyy ]

