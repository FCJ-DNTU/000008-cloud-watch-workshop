---
title: "Thực hiện các phép toán học"
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

#### Biểu thức toán học

Tiếp tục, trong phần này chúng ta sẽ thực hiện các thao tác biểu thức toán cơ bản.

1. Đầu tiên là dọn dẹp biểu thức tìm kiếm trước đó.

![3.3.1](/images/3-cloud-watch-metric/3.3-math-expression/3.3.1.png)

2. Về lại tab Browse.

   - Ấn Graph search để lấy lại biểu đồ như ban đầu ở bước trước.

![3.3.2](/images/3-cloud-watch-metric/3.3-math-expression/3.3.2.png)

3. Sau đó xổ phần **Add math** ở bên góc trên bên phải, dưới biểu đồ.

   - Xổ tiếp **Filter**.
   - Chọn **Top 10 by sum**.

![3.3.3](/images/3-cloud-watch-metric/3.3-math-expression/3.3.3.png)

![3.3.4](/images/3-cloud-watch-metric/3.3-math-expression/3.3.4.png)

4. Giờ thì chúng ta sẽ tiến hành sắp xếp lại biểu đồ dựa trên biểu thức tìm kiếm đầu tiên, với biểu thức như bên dưới.

```
SORT(e1, SUM, DEC, 3)
```

![3.3.5](/images/3-cloud-watch-metric/3.3-math-expression/3.3.5.png)

![3.3.6](/images/3-cloud-watch-metric/3.3-math-expression/3.3.6.png)

OK xong, trong phần này thì chúng ta thực hiện đơn giản như vậy thôi, tiếp tục thực hành ở phần sau.
