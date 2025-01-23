---
title : "Dynamic Labels"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 3.4 </b> "
---

#### Dynamic Labels

1. Select **Add math expression**, then select **Start with empty expression**

![CloudWatch](/images/2/2.4/0001.png?featherlight=false&width=90pc)

2. Do a search:

```
SEARCH('exe="cloudwatch" MetricName="procstat_memory_rss"', 'Average', 300)
```

![CloudWatch](/images/2/2.4/0002.png?featherlight=false&width=90pc)

3. Select **Add dynamic label**

- Then select **All Labels** and select **PROP('Dim.DimName')**

![CloudWatch](/images/2/2.4/0003.png?featherlight=false&width=90pc)

4. Result

![CloudWatch](/images/2/2.4/0004.png?featherlight=false&width=90pc)

5. Do the same for **PROP('MetricName')**

![CloudWatch](/images/2/2.4/0005.png?featherlight=false&width=90pc)

6. Then update Label

```
${PROP('Dim.exe')} - ${PROP('Dim.InstanceId')} - ${PROP('MetricName')}
```

![CloudWatch](/images/2/2.4/0006.png?featherlight=false&width=90pc)