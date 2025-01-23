---
title : "CloudWatch Logs Insights"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---

#### CloudWatch Logs Insights

1. Bạn truy cập vào giao diện **EC2**

- Chọn **Instances**
- Chọn **/Instance-A/test-instance**
- Sau đó, chọn **Connect**

![CloudWatch](/images/3/3.2/0001.png?featherlight=false&width=90pc)


2. Trong giao diện **Connect to instance**

- Chọn **Session Manager**
- Chọn **Connect**

![CloudWatch](/images/3/3.2/0002.png?featherlight=false&width=90pc)

3. Chúng ta sẽ có một giao diện mới trên trình duyệt

![CloudWatch](/images/3/3.2/0003.png?featherlight=false&width=90pc)

4. Sau khi truy cập vào giao diện **Session Manager**. Bạn thực hiện chạy đoạn script sau:

```
cd /tmp
sudo aws s3 cp s3://workshop-template-bucket/logger.py .
```

![CloudWatch](/images/3/3.2/0004.png?featherlight=false&width=90pc)

4. Tiếp tục cấp quyền bằng cách chạy đoạn script tiếp theo

```
sudo chmod +x logger.py
python3 logger.py &
```

![CloudWatch](/images/3/3.2/0005.png?featherlight=false&width=90pc)

5 . Chúng ta kiểm tra lại bằng lệnh sau:

```
 ps -aux | grep logger
```

![CloudWatch](/images/3/3.2/0006.png?featherlight=false&width=90pc)

6. Xem log bằng lệnh sau:

```
sudo tail -f /var/log/messages
```

![CloudWatch](/images/3/3.2/0007.png?featherlight=false&width=90pc)

#### Tìm log trong CloudWatch Log Insights

1. Truy cập vào giao diện **CloudWatch***

- Chọn **Logs Insights**
- Chọn **Select log group(s)**

![CloudWatch](/images/3/3.2/0008.png?featherlight=false&width=90pc)

2. Chọn **/ec2/linux/var/log/messages.**

![CloudWatch](/images/3/3.2/0009.png?featherlight=false&width=90pc)

3. Thực hiện **Run query**

```
fields @timestamp, @message
| sort @timestamp desc
| limit 20
```

![CloudWatch](/images/3/3.2/00010.png?featherlight=false&width=90pc)

4. **Notice that we are querying the logs from the past one hour**, chọn **Custom**

![CloudWatch](/images/3/3.2/00011.png?featherlight=false&width=90pc)

5. Chúng ta sẽ thấy log như sau:

![CloudWatch](/images/3/3.2/00012.png?featherlight=false&width=90pc)

6. Lọc những log lỗi

```
fields @timestamp, @message
| filter @message like /ERROR/
| sort @timestamp desc
| limit 20
```

![CloudWatch](/images/3/3.2/00013.png?featherlight=false&width=90pc)

7. Xem các log chứa **WARN**

```
fields @timestamp, @message
| filter @message like /WARN/
| sort @timestamp desc
| limit 20
```

![CloudWatch](/images/3/3.2/00014.png?featherlight=false&width=90pc)

8. Sau đó thử lại chạy query **ERROR**

```
fields @timestamp, @message
| filter @message like /ERROR/
| sort @timestamp desc
| stats count (*) by @logStream
```

![CloudWatch](/images/3/3.2/00015.png?featherlight=false&width=90pc)

9. Tiếp tục query

```
fields @timestamp, @message
| filter @message like /eth0/
| sort @timestamp desc
| stats count (*) by bin(5m)
```

![CloudWatch](/images/3/3.2/00016.png?featherlight=false&width=90pc)

10. Sau đó bạn xem **Visualization**

![CloudWatch](/images/3/3.2/00017.png?featherlight=false&width=90pc)

11. Thực hiện **Save** query

```
fields @timestamp, @message
| filter @message like /ERROR/
| sort @timestamp desc
| limit 20
```

![CloudWatch](/images/3/3.2/00018.png?featherlight=false&width=90pc)

12. Save query thành công.

![CloudWatch](/images/3/3.2/00019.png?featherlight=false&width=90pc)

13. Xem lịch sử các query.

![CloudWatch](/images/3/3.2/00020.png?featherlight=false&width=90pc)