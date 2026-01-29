# ☁️ CloudWatch Practical


## **Create an SNS Topic**

1. Go to **SNS**
2. Click on **Create topic**
3. Click on **Next step**

   * a. Select **Standard**
   * b. Enter a **Topic name**
   * c. Click on **Create topic**



## **Create Subscription**

1. After creating the topic, scroll down and click on **Create subscription**

   * a. Select **Protocol**
   * b. Enter your **Email**
   * c. Click on **Create subscription**
   * d. Open your email and click on **Confirm subscription**
     *(to confirm that the email is yours)*



## **ALARMS CREATION**

1. Go to **CloudWatch** → Click on **Alarms**
2. Click on **Create alarm**

   * a. Click on **Select metric**

     * Select the service for which you want to create the alarm (**EC2**)
     * Copy the **Instance ID** of your EC2 instance
     * Go to **Per-Instance Metrics** and paste the **Instance ID**
     * Scroll down and select **CPUUtilization**
     * Click on **Select metric**
     * In the next step, set the **time period** as per your requirement
   * b. Select an **SNS Topic** and do not change anything else → Click **Next**
   * c. Enter a **Name** for the alarm
   * d. Click on **Create alarm**



## **Enable Detailed Monitoring**

1. Go to **EC2**

   * a. Scroll down and click on **Monitoring**
   * b. Click on **Manage detailed monitoring**

     * Enable **Detailed monitoring**
     * Click on **Confirm**



## **Increase Traffic for Alarm Working**

1. SSH into the EC2 instance

2. Install **Stress** software (to increase traffic)

   * a. Install stress:

     ```
     sudo yum install stress -y
     ```
   * b. Increase CPU load:

     ```
     stress --cpu 8 --timeout 60
     ```

3. Monitor your EC2 instance

4. Keep running the command until the traffic reaches the threshold set in the alarm

5. You will receive an **Email notification** once the alarm is triggered



## ⚠️ **IMPORTANT**

**DELETE EACH AND EVERY RESOURCE AFTER PERFORMING THE PRACTICAL**
(SNS Topic, Subscription, Alarm, EC2 Instance, etc.)


* Make it **exam / interview notes**
* Add a **diagram flow (SNS → CloudWatch → EC2)**
