---
title : "Viewing Metrics"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---

#### Viewing Metrics

1. Truy cập **AWS Management Console**

   - Tìm **CloudWatch**
   - Chọn **CloudWatch**

![CloudWatch](/images/2/2.1/0001.png?featherlight=false&width=90pc)

2. Trong giao diện **CloudWatch**

   - Chọn **All metrics**
   - Chọn **EC2**

![CloudWatch](/images/2/2.1/0002.png?featherlight=false&width=90pc)

3. Chọn **Per-Instance Metrics**. 

![CloudWatch](/images/2/2.1/0003.png?featherlight=false&width=90pc)

4. Sau đó, chúng ta sẽ thấy giao diện như sau.

![CloudWatch](/images/2/2.1/0004.png?featherlight=false&width=90pc)

5. Trong phần **Dimension**, sẽ xuất hiện cột **InstanceId**. Sau đó chọn **Add to search**

![CloudWatch](/images/2/2.1/0005.png?featherlight=false&width=90pc)

6. Xem **EBSWriteBytes**

![CloudWatch](/images/2/2.1/0007.png?featherlight=false&width=90pc)

7. Xem **CPUUtilization**

![CloudWatch](/images/2/2.1/0008.png?featherlight=false&width=90pc)

8. Chọn **Graphed metrics tab.**

- Chúng ta có thể sắp xếp vị trí của các metric.

![CloudWatch](/images/2/2.1/0009.png?featherlight=false&width=90pc)

9. Chọn **Graph Options.** Thực hiện cấu hình.

![CloudWatch](/images/2/2.1/00010.png?featherlight=false&width=90pc)

10. Cuối cùng chúng ta được graph như hình.

![CloudWatch](/images/2/2.1/00011.png?featherlight=false&width=90pc)

Trong phần này có một thử thách nhỏ: các bạn sẽ thêm label với Horizontal annotation tại 80% và vertical annotation.

