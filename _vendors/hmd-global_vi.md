---
name: Nokia
subtitle: including Android One
manufacturer:
  - nokia
  - hmd global
redirect_from:
  - /vendors/nokia.html
award: 2
position: 10
explanation: "

<div class='caution-box'>
  Cập nhật 8/2019
  <br><br>
  <b>TIN TỐT</b>: HMD Global <a href=\"https://community.phones.nokia.com/discussion/51246/tapping-into-android-pies-adaptive-battery-for-optimum-battery-performance\">cho phép vô hiệu hoá các ứng dụng tiết kiệm pin Evenwell </a> cho tất cả các thiết bị sử dụng Android Pie hoặc mới hơn.
  <br>
  <b>TIN KHÔNG VU</b>: vẫn tồn tại DuraSpeed.
</div>

HMD Global/Nokia là hãng có nhiều ứng dụng ngắt tiến trình nền được cài đặt sẵn nhất trong tất cả.


Có 3 cơ chế ngắt tiến trình chạy nền của Nokia:


* *com.evenwell.powersaving.g3* trên Android Pie cho đa số các điện thoại Nokia - **cơ chế này đã bị vô hiệu hoá từ 8/2019 trên các thiết bị chạy Android Pie trở lên**

* *com.evenwell.emm* trên Android Oreo cho Nokia 1 - **có thể vẫn đang tồn tại bởi HMD chỉ vô hiệu hoá các ứng dụng Evenwell apps từ Pie trở lên**

* *DuraSpeed* trên Android Pie (build 00WW_3_180) cho điện thoại US Nokia 3.1 (TA-1049, TA-1063) và Nokia 5.1 - **cơ chế này vẫn đang tồn tại**


### Trên hầu hết các thiết bị Nokia (Chế độ tiết kiệm pin - com.evenwell.powersaving.g3)

<div class='caution-box'>
  Cơ chế tiết kiệm pin Evenwell *(com.evenwell.powersaving.g3)* đã bị vô hiệu hoá bởi HMD Global trên các thiết bị chạy Android Pie trở lên từ ngày 8/2019.
</div>


### Nokia 1 (com.evenwell.emm)

On Nokia 1 there is an alternative package that works very similar to what the com.evenwell.powersaving.g3 package is doing on the higher end models.


### Nokia 3.1 and 5.1 (DuraSpeed)

On Mediatek-based devices, HMD has baked in [DuraSpeed](https://www.appbrain.com/app/duraspeed/com.mediatek.duraspeed) as a system service. There is no user-facing control, or whitelist; this Mediatek-developed task killer terminates all background apps without prejudice.


DuraSpeed can be disabled through the global settings store, but this is a protected area of Android that can only be manipulated through adb, or an app that has been granted the `WRITE_SECURE_SETTINGS` permission (which must also be done with adb). Additionally, the setting does not survive a reboot. Users can fix their devices themselves using an automation app (see \"Solution for users\"), or apps can request the `WRITE_SECURE_SETTINGS` permission and then cycle the flag on startup to kill DuraSpeed. Syncthing-Fork is one app that has [taken this approach](https://github.com/Catfriend1/syncthing-android/wiki/Nokia-HMD-phone-preparations).


Unfortunately, there are [some](https://forum.xda-developers.com/showpost.php?s=1f4fbd7602c2739781c1c5346bb06e36&p=80157506&postcount=7) [reports](https://github.com/urbandroid-team/dont-kill-my-app/issues/57#issuecomment-534246709) that even this fix does not work.


"
user_solution: "

### Trên hầu hết các điện thoại Nokia (Chế độ tiết kiệm pin - com.evenwell.powersaving.g3)

Để sửa lỗi này, hãy làm theo các bước sau:

* Đi tới **Cài đặt điện thoại > Ứng dụng  > Tất cả ứng dụng**.

* Bấm vào **menu trên góc trên bên phải > Chọn Hiển thị hệ thống**.

* Tìm các ứng dụng **Tiết kiệm pin** trong danh sách, chọn ứng dụng và chọn **Buộc dừng**. Ứng dụng sẽ được tắt ngay lập tức, nhưng sau đó sẽ tự khởi động lại


Từ giờ trở đi, các ứng dụng sử dụng tiến trình nền sẽ hoạt động bình thường và điện thoại sẽ sử dụng chức năng tiết kiệm pin mặc định của Android.


Các ứng dụng báo thức ( không phải mặc định ) hay các ứng dụng chạy ngầm theo lịch trình vẫn sẽ không hoạt động được ~~Hiện tại,chúng tôi vẫn chưa có cách khắc phục vấn đề này~~ Cập nhật: trong các thứ nghiệm, có vẻ việc tắt các ứng dụng tiết kiệm pin giúp cho các ứng dụng báo thức ( không phải mặc định ) hay các ứng dụng chạy ngầm theo lịch trình vẫn hoạt động tốt cho đến khi các ứng dụng tiết kiệm pin được khởi động lại


Giải pháp thay thế cho các người dùng hiểu biết về kỹ thuật:

### Hầu hết các thiết bị Nokia

<div class='caution-box'>
  Chế độ tiết kiệm pin Evenwell *(com.evenwell.powersaving.g3)* đã được vô hiệu hoá bởi HMD Global trên các thiết bị chạy Android Pie trở lên từ ngày 8/2019.
</div>


Vô hiệu hoá *com.evenwell.powersaving.g3* bằng cách sử udngj các câu lệnh adb sau :


`adb shell`<br>
`pm disable-user com.evenwell.powersaving.g3`


### Nokia 1 (Android Go)

Vô hiệu hoá *com.evenwell.emm* bằng cách sử udngj các câu lệnh adb sau :


`adb shell`<br>
`pm disable-user com.evenwell.emm`


### Nokia 3.1 and 5.1
Đáng tiếc là HMD không cung cấp bất kì một cài đặt nào để có thể thay đổi hoạt động của tính năng DuraSpeed. Và từ khi các tiến trình ngắt tiến trình nền trở thành tiến trình của hệ thống, nó không thể được gỡ một cách dễ dành. May thay, DuraSpeed có một cách để tắt: Nó lắng nghe sự thay đổi của cài đặt `setting.duraspeed.enabled` và sẽ tự động tắt nếu giá trị được đặt cho nó không bằng 1. Một khi DuraSpeed dừng hoạt động,các ứng dụng chạy tiến trình nền đều sẽ hoạt động tốt.Tuy nhiên, khi khởi động lại máy thì DuraSpeed sẽ được tự động chạy lại bằng phương pháp [MacroDroid](https://play.google.com/store/apps/details?id=com.arlosoft.macrodroid).


Trước tiên, sử dụng adb để MacroDroid (hoặc ứng dụng tuỳ chọn) có khả năng ghi đè các cài đặt hệ thống bằng câu lệnh:


```
adb shell pm grant com.arlosoft.macrodroid android.permission.WRITE_SECURE_SETTINGS
```


Sau đó khởi tạo một chương trình, được kích hoạt tại **Device Boot**, bằng các bước sau:


1. System Setting: type **Global**, name **setting.duraspeed.enabled**, value **2**


2. System Setting: type **Global**, name **setting.duraspeed.enabled**, value **0**


<div class='img-block'>
  <figure>
     <img src='/assets/img/nokia/duraspeed_macrodroid_kyrasantae.png'>
     <figcaption>MacroDroid example task</figcaption>
  </figure>
  <figure>
     <img src='/assets/img/nokia/duraspeed_tasker_yoryan.jpg'>
     <figcaption>Ví dụ về chương trình</figcaption>
  </figure>
</div>


Chạy chương trình và đảm bảo không có lỗi. Nếu mọi thứ đều tốt đẹp, DuraSpeed sẽ bị vô hiệu hoá và cũng sẽ không bị khởi động lại khi khởi động lại máy.

"

developer_solution: "The only workaround we found so far is to keep the screen on all time your process runs. Yes, this is very battery consuming. As usually, vendors trying to safe your battery cause much bigger battery drain on this kind of workarounds. An alternative to this is to turn the screen on only less than every 20 minutes.


Another serious issue which we did not find a workaround for is that Nokia does not allow to start service using `startForegroundService()` when the process is not on background. We cannot reproduce it in few minutes after the process gets to background, but after ~hours there is the following message in the log:


`ActivityManager: Background start not allowed: service Intent { act=com.myapp.ALARM_ALERT flg=0x4 pkg=com.myapp (has extras) } to com.myapp/.MyService from pid=-1 uid=666 pkg=com.myapp startFg?=true`


This renders any alarm clocks, calendars, schedulers, automation tasks or any other processing at specified time useless.

"

---
