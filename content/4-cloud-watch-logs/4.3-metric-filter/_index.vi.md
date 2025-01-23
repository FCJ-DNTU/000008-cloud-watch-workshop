---
title : "CloudWatch Metric Filter"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 4.3 </b> "
---

#### CloudWatch Metric Filter

1. Quay lại giao diện **CloudWatch**

- Chọn **Log groups**
- Chọn **/ec2/linux/var/log/messages**
- Chọn **Actions**
- Chọn **Create metric filter**

![CloudWatch](/images/3/3.3/0001.png?featherlight=false&width=90pc)

2. Đối với **Filter pattern**, nhập **ERROR**

![CloudWatch](/images/3/3.3/0002.png?featherlight=false&width=90pc)

3. Chọn **Select log data to test** và chọn **Test pattern**

- Bạn sẽ thấy theo thông tin sau:

```
[month, day, timestamp, host, appId="logger.runJob:", message="ERROR*"]
```

- Chọn **Next**

![CloudWatch](/images/3/3.3/0003.png?featherlight=false&width=90pc)

4. Name là **PythonAppErrors**

- Đặt **metric namespace** là **ec2-logs**
- Đối với **Metric name** là **/var/log/messages - ERROR**
- Đối với **Metric value** đặt là 1
- Mặc định đặt là 0
- Đối với **Unit** chọn **Count**
- Chọn **Next**

![CloudWatch](/images/3/3.3/0004.png?featherlight=false&width=90pc)

5. Xem lại và chọn **Create metric filter**

![CloudWatch](/images/3/3.3/0005.png?featherlight=false&width=90pc)

![CloudWatch](/images/3/3.3/0006.png?featherlight=false&width=90pc)

![CloudWatch](/images/3/3.3/0007.png?featherlight=false&width=90pc)