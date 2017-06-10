# chiếc đồng hồ Bông Hồng nhỏ
* Chiếc đồng hồ thời tiết, người bạn cùng từng ngày năng động... 
* Chiếc đồng hồ giúp bạn biết vị trí của mình trên bản đồ. 
* Người bạn có khả năng dự báo thời tiết giúp bạn chủ động hơn trong các hoạt động và những chuyến đi chơi. 
* Giúp bạn biết nhiệt độ , độ ẩm tại nơi bạn làm việc, sinh sống,... 
* Sản phẩm phát triển từ phần cứng : Raspberry Pi 3; màn hình LCD 10 inch; cảm biến nhiệt độ, độ ẩm DHT11 . 
## Hướng dẫn cài đặt : 
### Bước 1 : Thiết lập cho Pi với hệ điều hành Raspbian 
- Trong Terminar 
  - Các bạn gõ lệnh : $ sudo raspi-config
  - Lựa chọn mở rộng vùng thẻ nhớ cho hệ điều hành :
   7.) Advanced Options > A1. Expand Filesystem > OK
  - Chọn chế độ boot cho hệ điều hành :
   3.) Boot Options > B1. Desktop / CLI  > B4. Desktop Autologin
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
   - Cài đặt thư viện cho cảm biến DHT11 
      - $ git clone https://github.com/adafruit/Adafruit_Python_DHT.git
      - $ cd Adafruit_Python_DHT
      - $ sudo apt-get update
      - $ sudo apt-get install build-essential python-dev
      - $ sudo python setup.py install
    - Cài đặt ẩn biểu tượng con chuột khi không có tác động tới màn hình 
      - $ sudo apt-get install unclutter 
    - Tắt chế độ ngủ của màn hình : 
      - $ sudo apt-get install xscreensaver
      - Vào Menu (biểu tượng của Pi, góc trái trên cùng của màn hình) > Preferences > Screensaver > trong Display Modes, tại Mode > chọn Disable Screen Saver. 
      - Close và khởi động lại Pi. 
### Bước 2 : Setup một số thông số cho phần mềm small Rose Clock
- Đăng ký tài khoản trên server  wunderground để nhận API key
    - Các bạn đăng ký tài khoản theo đường link : https://www.wunderground.com/weather/api . Lựa chọn *Sign Up for FREE*.
    
   ![signup for api key](https://user-images.githubusercontent.com/8324506/27001636-5167d780-4df9-11e7-9f3e-acd337d1b1e1.png)

   Các bạn điền thông tin và lựa chọn *Sign Up*
    
   ![step2](https://user-images.githubusercontent.com/8324506/27001644-8f73a5e0-4df9-11e7-9c2f-924bc6401226.png)

   Sau khi đăng ký tài khoản thành công, các bạn đăng nhập và truy cập theo đường link dưới đây để đăng ký lấy API key.
   https://www.wunderground.com/weather/api/d/pricing.html  
   Các bạn kéo xuống vị trí có đăng ký miễn phí : 500 lần truy cập server / ngày và 10 lần truy cập/phút. Nhấn vào Purchase Key và làm theo các yêu cầu của đăng ký, sau khi đăng ký thành công các bạn có thể nhận được API key.
   ![purchasekey](https://user-images.githubusercontent.com/8324506/27001719-fac00d38-4dfa-11e7-8970-68e59634a112.png)
   Các bạn mở thư mục small_RoseClock-python_qt4 đã tải về ở Bước 1, mở file ApiKeys.py và dán API  key của bạn vào dòng lệnh sau : 
    ```
    # Weather Underground API key
    wuapi = 'Your API key'
    ```
      
- Dò tìm vị trí của bạn và điền tọa độ vào chương trình
- Thay đổi hình nền cho giao diện.

Các bạn tham khảo tham khảo thêm tại : 
