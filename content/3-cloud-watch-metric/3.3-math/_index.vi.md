---
title : "Math expressions"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3.3 </b> "
---

#### Math expressions

1. Tiếp tục bước trước, chúng ta vẫn truy cập vào giao diện **CloudWatch**

![CloudWatch](/images/2/2.3/0001.png?featherlight=false&width=90pc)

2. Chọn **Graphed metrics**

   - Chọn **Add math expression**

![CloudWatch](/images/2/2.3/0002.png?featherlight=false&width=90pc)

3. Chọn  **Filter**


![CloudWatch](/images/2/2.3/0003.png?featherlight=false&width=90pc)

4. Sau đó chọn **Top 10 by Sum**. Xem chi tiết: 
```
SORT(e1, SUM, DESC, 3)
```

![CloudWatch](/images/2/2.3/0004.png?featherlight=false&width=90pc)

5. Quay lại giao diện **All metrics**

   - Chọn **CWAgent namespace**

![CloudWatch](/images/2/2.3/0005.png?featherlight=false&width=90pc)

6. Chọn **ImageId, InstanceId, InstanceType, exe, process_name**

![CloudWatch](/images/2/2.3/0006.png?featherlight=false&width=90pc)

7.  exe="cloudwatch" và MetricName="procstat_memory_rss"

![CloudWatch](/images/2/2.3/0007.png?featherlight=false&width=90pc)

8. Kết quả

![CloudWatch](/images/2/2.3/0008.png?featherlight=false&width=90pc)

9. Thực hiện tương tự

![CloudWatch](/images/2/2.3/0009.png?featherlight=false&width=90pc)

![CloudWatch](/images/2/2.3/00010.png?featherlight=false&width=90pc)

