---
name: Xiaomi
subtitle: except Android One
manufacturer:
  - xiaomi
position: 4
award: 4
redirect_from: /vendors/xiaomi.html
explanation: "
Xiaomi và các tuỳ biến cho Android có tên là MIUI được coi là thứ rắc rối nhất khi không tuân theo quy chuẩn về ứng dụng chạy nền và quy chuẩn cấp quyền.
Hiện tại vẫn chưa có bất kì tài liệu về nó. Các cài đặt mặc định của ứng dụng chạy nền đều không hoạt động đúng và khiến ứng dụng sử dụng chúng đều gặp vấn đề.


> GHI CHÚ: Điện thoại Android One của Xiaomi hoạt động tốt hơn các điện thoại sử dụng MIUI. Vì vậy, nếu bạn thích Xiaomi, chúng tôi khuyên bạn nên tìm kiếm  sản phẩm Android One của họ
"

user_solution: '

### MIUI 10


Để ứng dụng của bạn có thể chạy nền thì cần đảm bảo rằng các cài đặt trong "Setting" của bạn cần phải giống như sau (dưới đây là ví dụ về một ứng dụng tên là Sleep) :

<div class="img-block">
  <img src="/assets/img/ss_xiaomi_1a.png">
  <img src="/assets/img/ss_xiaomi_1b.png">
  <img src="/assets/img/ss_xiaomi_1c.png">
</div>


### Power management


Please enable:

* *Cài đặt > Cài đặt bổ sung > Battery manager >Đặt Power plan* về chế độ Performance

* *Device Settings > Advanced Settings > Battery Manager > Protected apps* – Ứng dụng của bạn cần chuyển về Protected

* *Device Settings > Apps > Tên ứng dụng > Battery > Power-intensive prompt* and *Keep running after screen off*

* *Settings > Additional Settings > Battery & Performance > Manage apps’ battery usage* sau đó:

1. Chuyển Power Saving Modes về *Tắt*

2. Chọn  tuỳ chọn tiếp theo: *Saving Power in The Background > Choose apps > select your app > Background Settings > No restrictions*


### Chế độ tiết kiệm


*Security > Battery > App Battery Saver > Tên ứng dụng> No restriction*


### Chế độ tự khởi động

(Dựa trên tài liệu của [Xiaomi](https://in.c.mi.com/thread-253478-1-0.html):


Mở *Security app > Permissions > Auto-start*


Bật Autostart cho ứng dụng mong muốn.

<div class="img-block">
  <img src="/assets/img/ss_xiaomi_as_1.png">
  <img src="/assets/img/ss_xiaomi_as_2.png">
    <div class="img-block">
     <figure>
          <img src="/assets/img/ss_xiaomi_as_3.png">
       <figcaption>Tìm kiếm ứng dụng của bạn và bấm vào để bật</figcaption>
     </figure>
    </div>
</div>

### Ghim ứng

Khi mở để xem các ứng dụng đang chạy, giữ và kéo xuống tại ứng dụng của bạn – nó sẽ được khoá. Nó sẽ giúp ứng dụng của bạn không bị tắt khi bạn dọn các ứng dụng đang chạy nền.
 Kéo xuống tại ứng dụng 1 lần nữa để bỏ khoá và tắt ứng dụng.

'
---
