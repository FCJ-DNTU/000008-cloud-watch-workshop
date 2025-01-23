---
title : "Math expressions"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.3 </b> "
---

#### Math expressions

1. Continuing the previous step, we still access the **CloudWatch** interface

![CloudWatch](/images/2/2.3/0001.png?featherlight=false&width=90pc)

2. Select **Graphed metrics**

   - Select **Add math expression**

![CloudWatch](/images/2/2.3/0002.png?featherlight=false&width=90pc)

3. Select **Filter**


![CloudWatch](/images/2/2.3/0003.png?featherlight=false&width=90pc)

4. Then select **Top 10 by Sum**. See details:
```
SORT(e1, SUM, DESC, 3)
```

![CloudWatch](/images/2/2.3/0004.png?featherlight=false&width=90pc)

5. Return to **All metrics** interface

   - Select **CWAgent namespace**

![CloudWatch](/images/2/2.3/0005.png?featherlight=false&width=90pc)

6. Select **ImageId, InstanceId, InstanceType, exe, process_name**

![CloudWatch](/images/2/2.3/0006.png?featherlight=false&width=90pc)

7. exe="cloudwatch" and MetricName="procstat_memory_rss"

![CloudWatch](/images/2/2.3/0007.png?featherlight=false&width=90pc)

8. Results

![CloudWatch](/images/2/2.3/0008.png?featherlight=false&width=90pc)

9. Do the same

![CloudWatch](/images/2/2.3/0009.png?featherlight=false&width=90pc)

![CloudWatch](/images/2/2.3/00010.png?featherlight=false&width=90pc)