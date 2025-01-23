---
title: "Thực hiện các phép tìm kiếm"
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

#### Biểu thức tìm kiếm

Ở phần trước thì chúng ta thực hiện xem metric theo cách thủ công, tuy nhiên nó vẫn còn nhiều hạn chế cũng như là phải thao tác nhiều lần với nhiều metrics khác nhau. Trong phần này chúng ta có thể thực hiện việc này nhanh hơn với Search Expression.

1. Xoá hết các thông tin trong biểu đồ cũ đi, ấn **X** hoặc ấn **Clear graph**.

![3.2.1](/images/3-cloud-watch-metric/3.2-search-expression/3.2.1.png)

2. Trở lại tab **Browse**

   - Xoá bộ lọc **EBSWriteBytes** đi.
   - Thêm lại **CPUUtilization**.
   - Ấn Graph search.

![3.2.2](/images/3-cloud-watch-metric/3.2-search-expression/3.2.2.png)

![3.2.3](/images/3-cloud-watch-metric/3.2-search-expression/3.2.3.png)

3. Quay trở lại tab **Graphed metrics**, chúng ta có thể thấy cột **Details** có một biểu thức tìm kiếm vừa mới hiện lên ở đây.

![3.2.4](/images/3-cloud-watch-metric/3.2-search-expression/3.2.4.png)

4. Nhập một biểu thức mới với nội dung như bên dưới. Biểu thức này chúng ta đang thực hiện tìm kiếm ở một Namespace khác ngoài EC2.

```

```

Sau đó là ấn **Apply** để áp dụng.

![3.2.5](/images/3-cloud-watch-metric/3.2-search-expression/3.2.5.png)

Ở góc bên trên bên phải cùng

- Xổ ô **Line**.
- Chọn **Stacked area**.

![3.2.6](/images/3-cloud-watch-metric/3.2-search-expression/3.2.6.png)

Và biểu đồ của chúng ta đã dễ nhìn hơn.

![3.2.7](/images/3-cloud-watch-metric/3.2-search-expression/3.2.7.png)

5. Tìm lượng bộ nhớ trung bình sử dụng theo phần trăm (Disk Used Percent)

```
SEARCH("disk_used_percent", 'Average', 300)
```

![3.2.8](/images/3-cloud-watch-metric/3.2-search-expression/3.2.8.png)

![3.2.9](/images/3-cloud-watch-metric/3.2-search-expression/3.2.9.png)

6. Tìm theo từ khoá "used"

```
SEARCH("used", 'Average', 300)
```

![3.2.10](/images/3-cloud-watch-metric/3.2-search-expression/3.2.10.png)

Có thể thấy là kết quả ít nhiều đã khác đi.

![3.2.11](/images/3-cloud-watch-metric/3.2-search-expression/3.2.11.png)

Ok vậy thì chúng ta vừa mới thực hiện xong cơ bản các phép tìm kiểu ở trong CloudWatch Console. Sang phần tiếp theo thì chúng ta sẽ thực hiện các phép toán đơn giản.
