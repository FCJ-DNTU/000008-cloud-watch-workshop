---
title : "Viewing Metrics"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---

#### Viewing Metrics

1. Access **AWS Management Console**

   - Find **CloudWatch**
   - Select **CloudWatch**

![CloudWatch](/images/2/2.1/0001.png?featherlight=false&width=90pc)

2. In the **CloudWatch** interface

   - Select **All metrics**
   - Select **EC2**

![CloudWatch](/images/2/2.1/0002.png?featherlight=false&width=90pc)

3. Select **Per-Instance Metrics**.

![CloudWatch](/images/2/2.1/0003.png?featherlight=false&width=90pc)

4. Then we will see the following interface.

![CloudWatch](/images/2/2.1/0004.png?featherlight=false&width=90pc)

5. In the **Dimension** section, the **InstanceId** column will appear. Then select **Add to search**

![CloudWatch](/images/2/2.1/0005.png?featherlight=false&width=90pc)

6. See **EBSWriteBytes**

![CloudWatch](/images/2/2.1/0007.png?featherlight=false&width=90pc)

7. See **CPUUtilization**

![CloudWatch](/images/2/2.1/0008.png?featherlight=false&width=90pc)

8. Select **Graphed metrics tab.**

- We can sort the positions of the metrics.

![CloudWatch](/images/2/2.1/0009.png?featherlight=false&width=90pc)

9. Select **Graph Options.** Perform configuration.

![CloudWatch](/images/2/2.1/00010.png?featherlight=false&width=90pc)

10. Finally we get the graph as shown.

![CloudWatch](/images/2/2.1/00011.png?featherlight=false&width=90pc)

In this part there is a small challenge: you will add labels with Horizontal annotation at 80% and vertical annotation.