---
title : "CloudWatch Metric Filter"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 4.3 </b> "
---

#### CloudWatch Metric Filter

1. Return to **CloudWatch** interface

- Select **Log groups**
- Select **/ec2/linux/var/log/messages**
- Select **Actions**
- Select **Create metric filter**

![CloudWatch](/images/3/3.3/0001.png?featherlight=false&width=90pc)

2. For **Filter pattern**, enter **ERROR**

![CloudWatch](/images/3/3.3/0002.png?featherlight=false&width=90pc)

3. Select **Select log data to test** and select **Test pattern**

- You will see the following information:

```
[month, day, timestamp, host, appId="logger.runJob:", message="ERROR*"]
```

- Select **Next**

![CloudWatch](/images/3/3.3/0003.png?featherlight=false&width=90pc)

4. Name is **PythonAppErrors**

- Set **metric namespace** to **ec2-logs**
- For **Metric name** is **/var/log/messages - ERROR**
- For **Metric value** set to 1
- Default is set to 0
- For **Unit** choose **Count**
- Select **Next**

![CloudWatch](/images/3/3.3/0004.png?featherlight=false&width=90pc)

5. Review and select **Create metric filter**

![CloudWatch](/images/3/3.3/0005.png?featherlight=false&width=90pc)

![CloudWatch](/images/3/3.3/0006.png?featherlight=false&width=90pc)

![CloudWatch](/images/3/3.3/0007.png?featherlight=false&width=90pc)