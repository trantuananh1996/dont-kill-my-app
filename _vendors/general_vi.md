---
name: Other vendors
position: 9999
explanation: |
Dù bạn đang sử dụng điện thoại nào, khi có các lỗi xảy ra hoàn toàn có thể do thiết bị chứ không phải lỗi xảy ra vì phần mềm hay lỗi của lập trình viên. Trước hết, hãy kiểm tra cài đặt của điện thoại bạn để biết chắc rằng những tiến trình nền không bị chặn.

 Hãy kiểm tra bằng các cách thường được áp dụng sau
user_solution: |
 Hãy tìm các ứng dụng tiết kiệm pin trong thiết bị của bạn và gỡ bỏ hoặc vô hiệu hoá nếu có thể

Nếu không, bạn chỉ còn lựa chọn là root máy hoặc gỡ cài đặt các ứng dụng đó thông qua **adb** ( cần phải có kỹ năng cao về kỹ thuật ) :

 `adb shell`

 `pm uninstall --user 0 com.useless.piece.of.trash`

 Kiểm tra khác cài đặt của điện thoại và tìm kiếm các cài đặt liên quan tới tiết kiệm pin hoặc tiến trình nền.
Nếu bạn có thể tìm thấy nó, hãy tìm cách để vô hiệu hoá nó

 ## Android 6+

 Luôn kiểm tra các cài đặt sau
 **Mục Cài đặt của máy > Pin và tiết kiệm pin >  Sử dụng pin > tìm mục “Bỏ qua tiết kiệm pin" > Bật ** để tắt chế độ tiết kiệm pin của điện thoại
 ## Android 8+

 Kiểm tra **Mục Cài đặt của máy > Ứng dụng & Thông báo > Chọn ứng dụng của bạn > Đảm bảo rằng mục  Hạn chế tiến trình nền** không được bật.

Nếu tất cả các cách trên đều không thành công, hãy thử tắt chế độ “Doze” của thiết bị

 ## Tắt chế độ doze cho các thiết bị  Android 6.0 trở về trước

 Trong mục **Cài đặt >  Tuỳ chọn nhà phát triển**. (Sử dụng google search để bật được chế độ nhà phát triển)

 ## Tắt chế độ doze cho các thiết bị  Android 7+

 Yêu cầu trình độ cao về kỹ thuật

 `dumpsys deviceidle disable`
---
