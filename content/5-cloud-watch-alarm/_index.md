---
title : "CloudWatch Alarms"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

1. Select **All Alarms**

- Select **"Create Alarm"**

![CloudWatch](/images/4/0001.png?featherlight=false&width=90pc)

2. Select **Select Metric**

![CloudWatch](/images/4/0002.png?featherlight=false&width=90pc)

3. We will see **"ec2-logs"**

![CloudWatch](/images/4/0003.png?featherlight=false&width=90pc)

4. **Metrics with no dimensions**

![CloudWatch](/images/4/0004.png?featherlight=false&width=90pc)

5. Select **/var/log/messages - ERROR**

- Select **Select Metric**

![CloudWatch](/images/4/0005.png?featherlight=false&width=90pc)

6. Select **1 minute** for **Period**

![CloudWatch](/images/4/0006.png?featherlight=false&width=90pc)

7. Select **Greater > threshold** and set it to 10. Then select **Next**

![CloudWatch](/images/4/0007.png?featherlight=false&width=90pc)

8. Select **Create Topic** and enter your email to receive notifications.

![CloudWatch](/images/4/0008.png?featherlight=false&width=90pc)

9. Select **Next**

![CloudWatch](/images/4/0009.png?featherlight=false&width=90pc)

10. Select **Create alarm**

![CloudWatch](/images/4/00010.png?featherlight=false&width=90pc)

11. Confirm mail

![CloudWatch](/images/4/00011.png?featherlight=false&width=90pc)

12. Results

![CloudWatch](/images/4/00012.png?featherlight=false&width=90pc)

13. You have successfully created **Alarm**.

![CloudWatch](/images/4/00013.png?featherlight=false&width=90pc)