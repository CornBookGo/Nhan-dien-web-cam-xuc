
Công nghệ Nhận diện Khuôn mặt API Python là 1 app nhận diện cảm xúc sử dụng Flask. Nó được tích hợp thư viện Face-API.js, được phát triển bởi [justadudewhohacks](https://github.com/justadudewhohacks), để nhận diện cảm xúc.  

## Chuẩn bị
- Python 3.6 hoặc cao hơn được tải lên máy tính sử dụng.
- 1 webcam hoặc camera được kết nối với máy tính.

## Tải thư viện liên quan
Sử dụng câu lệnh trên cmd để tải thư mục thư viện được sử dụng trong ứng dụng
   - pip install -r requirements.txt

## Sử dụng
Để dùng ứng dụng Nhận diện API, làm theo các bước sau:
1. Khởi chạy server API của ứng dụng bằng câu lệnh:
    python application.py

2. Khi server được chạy, mở trình duyệt web và chạy tên miền `http://localhost:5000`.

3. Cấp quyền truy cập vào camera khi thông báo trên trình duyệt web đưa ra.

4. Ứng dụng sẽ tự động nhận diện khuôn mặt trong đầu vào của camera và hiển thị cảm xúc tương ứng theo thời gian thực.

## Cách thức hoạt động
Công nghệ Nhận diện Khuôn mặt API Python sử dụng Flask, một khung web dành cho Python, để lưu trữ một máy chủ web. Nó cũng sử dụng MediaDevices API và Canvas API được cung cấp bởi các trình duyệt web hiện đại để ghi lại dữ liệu đầu vào của camera và hiển thị kết quả theo thời gian thực.

Khi trang web được tải, nó sẽ thiết lập kết nối websocket với máy chủ Flask. Máy chủ liên tục chụp các khung hình từ đầu vào của camera và thực hiện phát hiện cảm xúc khuôn mặt bằng thư viện Face-API.js và TensorFlow.js. Kết quả sau đó được gửi lại cho máy khách thông qua kết nối websocket và hiển thị trên trang web.

Thư viện Face-API.js cung cấp các mô hình được đào tạo trước để phát hiện khuôn mặt và phân loại cảm xúc, được tải xuống và sử dụng cục bộ trong bài khoa học này
