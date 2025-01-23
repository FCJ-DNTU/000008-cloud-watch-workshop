---
title : "Dynamic Labels"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 3.4 </b> "
---

#### Dynamic Labels

1. Chọn **Add math expression**, sau đó chọn **Start with empty expression**

![CloudWatch](/images/2/2.4/0001.png?featherlight=false&width=90pc)

2. Thực hiện search:

```
SEARCH('exe="cloudwatch" MetricName="procstat_memory_rss"', 'Average', 300) 
```

![CloudWatch](/images/2/2.4/0002.png?featherlight=false&width=90pc)

3. Chọn **Add dynamic label**

- Sau đó, chọn **All Labels** và chọn **PROP('Dim.DimName')**

![CloudWatch](/images/2/2.4/0003.png?featherlight=false&width=90pc)

4. Kết quả

![CloudWatch](/images/2/2.4/0004.png?featherlight=false&width=90pc)

5. Thực hiện tương tự đối với **PROP('MetricName')**

![CloudWatch](/images/2/2.4/0005.png?featherlight=false&width=90pc)

6. Sau đó, cập nhật Label 

```
${PROP('Dim.exe')} - ${PROP('Dim.InstanceId')} - ${PROP('MetricName')}
```

![CloudWatch](/images/2/2.4/0006.png?featherlight=false&width=90pc)

