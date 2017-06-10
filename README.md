# chiếc đồng hồ Bông Hồng nhỏ
* Chiếc đồng hồ thời tiết, người bạn cùng từng ngày năng động... 
* Chiếc đồng hồ giúp bạn biết vị trí của mình trên bản đồ. 
* Người bạn có khả năng dự báo thời tiết giúp bạn chủ động hơn trong các hoạt động và những chuyến đi chơi. 
* Giúp bạn biết nhiệt độ , độ ẩm tại nơi bạn làm việc, sinh sống,... 
* Sản phẩm phát triển từ phần cứng : Raspberry Pi; màn hình LCD 10 inch; cảm biến nhiệt độ, độ ẩm DHT11 . 
## Hướng dẫn cài đặt : 
### Bước 1 : Thiết lập cho Pi với hệ điều hành Raspbian 
- Trong Terminar 
  - Các bạn gõ lệnh : $ sudo raspi-config
  - Lựa chọn mở rộng vùng thẻ nhớ cho hệ điều hành :
   - 7.) Advanced Options > A1. Expand Filesystem > OK
  - Chọn chế độ boot cho hệ điều hành :
   - 3.) Boot Options > B1. Desktop / CLI  > B4. Desktop Autologin
- Chọn lại Timezone : Trên biểu tượng Pi ở góc trên cùng bên trái màn hình, các bạn click chọn và tìm tới Preference > Raspberry  Pi Configuration  > Localisation > Timezone  : 
  - Area : Asia
  - Location : Ho_Chi_Minh
- Enable : SSH, VNC, 1-Wire 
- Kết nối wifi hoặc mạng Lan cho Pi.
- Kết nối cảm biến DHT11 với Pi : 
  - VCC  --- pin số 2 : 5V
  - GND  ---  pin số 6 : GND
  - DOUT ---  pin số 22 : GPIO25
- Khởi động lại Pi
- Cài đặt phần mềm cần thiết cho Pi 
  - Download phần mềm small Rose Clock : $ git clone https://github.com/ThuyPham/small_RoseClock-python_qt4.git 
  - Cài đặt python-qt4 : 
   - $ sudo apt-get update 
   - $ sudo apt-get install python-qt4
    
Các bạn tham khảo tham khảo thêm tại : 
