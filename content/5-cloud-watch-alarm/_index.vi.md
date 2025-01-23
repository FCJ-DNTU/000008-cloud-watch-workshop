---
title : "CloudWatch Alarms"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

1. Chọn **All Alarms**

- Chọn **"Create Alarm"**

![CloudWatch](/images/4/0001.png?featherlight=false&width=90pc)

2. Chọn **Select Metric**

![CloudWatch](/images/4/0002.png?featherlight=false&width=90pc)

3. Ta sẽ thấy **"ec2-logs"**

![CloudWatch](/images/4/0003.png?featherlight=false&width=90pc)

4. **Metrics with no dimensions**

![CloudWatch](/images/4/0004.png?featherlight=false&width=90pc)

5. Chọn **/var/log/messages - ERROR**

- Chọn **Select Metric**

![CloudWatch](/images/4/0005.png?featherlight=false&width=90pc)

6. Chọn **1 minute** cho **Period**

![CloudWatch](/images/4/0006.png?featherlight=false&width=90pc)

7. Chọn **Greater > threshold** và đặt là 10. Sau đó chọn **Next**

![CloudWatch](/images/4/0007.png?featherlight=false&width=90pc)

8. Chọn **Create Topic** và điền mail của bạn nhận thông báo.

![CloudWatch](/images/4/0008.png?featherlight=false&width=90pc)

9. Chọn **Next**

![CloudWatch](/images/4/0009.png?featherlight=false&width=90pc)

10. Chọn **Create alarm**

![CloudWatch](/images/4/00010.png?featherlight=false&width=90pc)

11. Xác nhận mail

![CloudWatch](/images/4/00011.png?featherlight=false&width=90pc)

12. Kết quả

![CloudWatch](/images/4/00012.png?featherlight=false&width=90pc)

13. Thế là bạn đã tạo **Alarm** thành công.

![CloudWatch](/images/4/00013.png?featherlight=false&width=90pc)