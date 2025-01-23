---
title : "Search expressions"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---

####  Search expressions

1. Giống như phần trước chúng ta truy cập vào **CloudWatch**

   - Chọn **All metrics**
   - Chọn **Browse**
   - Chọn **EC2.**
   - Chọn **Per-Instance Metrics**
   - Chọn **CPUUtilization**
   - Chọn **Add to search**

![CloudWatch](/images/2/2.2/0001.png?featherlight=false&width=90pc)

2. Chọn **Graph search**

![CloudWatch](/images/2/2.2/0002.png?featherlight=false&width=90pc)

3. Quan sát và chọn **Graphed metrics**

Chi tiết về cú pháp như sau:

```
SEARCH('{AWS/EC2,InstanceId} MetricName="CPUUtilization"', 'Average', 300)
```

![CloudWatch](/images/2/2.2/0003.png?featherlight=false&width=90pc)

4. Tiếp tục thực hành với các cú pháp sau

```
SEARCH('{CWAgent,ImageId,InstanceId,InstanceType,device,fstype,path} path="/" MetricName="disk_used_percent"', 'Average', 300)
```

```
SEARCH('"disk_used_percent"', 'Average', 300)
```

```
SEARCH('used', 'Average', 300)
```

![CloudWatch](/images/2/2.2/0004.png?featherlight=false&width=90pc)