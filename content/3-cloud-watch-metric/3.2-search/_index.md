---
title : "Search expressions"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---

#### Search expressions

1. Like the previous part we access **CloudWatch**

   - Select **All metrics**
   - Select **Browse**
   - Select **EC2.**
   - Select **Per-Instance Metrics**
   - Select **CPUUtilization**
   - Select **Add to search**

![CloudWatch](/images/2/2.2/0001.png?featherlight=false&width=90pc)

2. Select **Graph search**

![CloudWatch](/images/2/2.2/0002.png?featherlight=false&width=90pc)

3. Observe and select **Graphed metrics**

The details of the syntax are as follows:

```
SEARCH('{AWS/EC2,InstanceId} MetricName="CPUUtilization"', 'Average', 300)
```

![CloudWatch](/images/2/2.2/0003.png?featherlight=false&width=90pc)

4. Continue practicing with the following syntaxes

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