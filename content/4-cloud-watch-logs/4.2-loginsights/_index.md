---
title : "CloudWatch Logs Insights"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---

#### CloudWatch Logs Insights

1. You access the **EC2** interface

- Select **Instances**
- Select **/Instance-A/test-instance**
- Then select **Connect**

![CloudWatch](/images/3/3.2/0001.png?featherlight=false&width=90pc)


2. In the **Connect to instance** interface

- Select **Session Manager**
- Select **Connect**

![CloudWatch](/images/3/3.2/0002.png?featherlight=false&width=90pc)

3. We will have a new interface on the browser

![CloudWatch](/images/3/3.2/0003.png?featherlight=false&width=90pc)

4. After accessing the **Session Manager** interface. You execute the following script:

```
cd /tmp
sudo aws s3 cp s3://workshop-template-bucket/logger.py .
```

![CloudWatch](/images/3/3.2/0004.png?featherlight=false&width=90pc)

4. Continue granting permission by running the next script

```
sudo chmod +x logger.py
python3 logger.py &
```

![CloudWatch](/images/3/3.2/0005.png?featherlight=false&width=90pc)

5 . We check again with the following command:

```
 ps -aux | grep logger
```

![CloudWatch](/images/3/3.2/0006.png?featherlight=false&width=90pc)

6. View the log with the following command:

```
sudo tail -f /var/log/messages
```

![CloudWatch](/images/3/3.2/0007.png?featherlight=false&width=90pc)

#### Find logs in CloudWatch Log Insights

1. Access to **CloudWatch** interface

- Select **Logs Insights**
- Select **Select log group(s)**

![CloudWatch](/images/3/3.2/0008.png?featherlight=false&width=90pc)

2. Select **/ec2/linux/var/log/messages.**

![CloudWatch](/images/3/3.2/0009.png?featherlight=false&width=90pc)

3. Execute **Run query**

```
fields @timestamp, @message
| sort @timestamp desc
| limit 20
```

![CloudWatch](/images/3/3.2/00010.png?featherlight=false&width=90pc)

4. **Notice that we are querying the logs from the past one hour**, select **Custom**

![CloudWatch](/images/3/3.2/00011.png?featherlight=false&width=90pc)

5. We will see the following log:

![CloudWatch](/images/3/3.2/00012.png?featherlight=false&width=90pc)

6. Filter error logs

```
fields @timestamp, @message
| filter @message like /ERROR/
| sort @timestamp desc
| limit 20
```

![CloudWatch](/images/3/3.2/00013.png?featherlight=false&width=90pc)

7. View logs containing **WARN**

```
fields @timestamp, @message
| filter @message like /WARN/
| sort @timestamp desc
| limit 20
```

![CloudWatch](/images/3/3.2/00014.png?featherlight=false&width=90pc)

8. Then retry running the query **ERROR**

```
fields @timestamp, @message
| filter @message like /ERROR/
| sort @timestamp desc
| stats count (*) by @logStream
```

![CloudWatch](/images/3/3.2/00015.png?featherlight=false&width=90pc)

9. Continue query

```
fields @timestamp, @message
| filter @message like /eth0/
| sort @timestamp desc
| stats count (*) by bin(5m)
```

![CloudWatch](/images/3/3.2/00016.png?featherlight=false&width=90pc)

10. Then you see **Visualization**

![CloudWatch](/images/3/3.2/00017.png?featherlight=false&width=90pc)

11. Execute **Save** query

```
fields @timestamp, @message
| filter @message like /ERROR/
| sort @timestamp desc
| limit 20
```

![CloudWatch](/images/3/3.2/00018.png?featherlight=false&width=90pc)

12. Save query successfully.

![CloudWatch](/images/3/3.2/00019.png?featherlight=false&width=90pc)

13. View query history.

![CloudWatch](/images/3/3.2/00020.png?featherlight=false&width=90pc)