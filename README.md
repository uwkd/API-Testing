# DỰ ÁN: KIỂM THỬ API & XÁC THỰC LUỒNG DỮ LIỆU (Mock E-commerce Backend)

## 1. Mục tiêu Dự án
Thực hiện kiểm thử toàn diện các điểm cuối của hệ thống API nhằm đảm bảo tính ổn định, xử lý ngoại lệ tốt và toàn vẹn dữ liệu của Backend. Dự án tập trung vào việc xác thực các phương thức CRUD (Create, Read, Update, Delete) và đối chiếu chéo với cơ sở dữ liệu gốc (Database Cross-checking).

## 2. Công cụ & Công nghệ áp dụng
* **API Testing Tool:** Postman.
* **Database Management:** SQL Server.
* **Data Format:** JSON.

## 3. Kỹ thuật Nâng cao (Key Features)
Dự án không chỉ dừng lại ở Manual API Testing mà đã áp dụng các tư duy tự động hóa và quản lý dự án:
* **Quản lý Môi trường (Environment Variables):** Sử dụng biến toàn cục `{{base_url}}` để linh hoạt chuyển đổi giữa các môi trường Dev/Staging/Production mà không cần hard-code (sửa tay) hàng loạt link.
* **Tự động hóa Nghiệm thu (Test Scripts/Assertions):** Viết script bằng JavaScript trên Postman để hệ thống tự động đánh giá kết quả:
  * Xác thực mã trạng thái HTTP (Status code: 200, 201).
  * Đo lường hiệu năng phản hồi (Response time < 1000ms).
  * Xác thực cấu trúc dữ liệu trả về (Data validation).
* **Kiểm thử Ngoại lệ (Negative Testing):** Phân tích phản hồi của Server khi gọi API sai ID (ép lỗi 404 Not Found) hoặc gửi payload rỗng (ép lỗi 400 Bad Request) để bẻ gãy hệ thống.

## 4. Bằng chứng Thực thi (Test Execution Evidence)
<img width="1602" height="998" alt="image" src="https://github.com/user-attachments/assets/3f503304-62aa-4620-98e8-d6e59125d540" />
<img width="1601" height="979" alt="image" src="https://github.com/user-attachments/assets/d05c8086-fd08-480c-9d54-a510178b6fe5" />
<img width="1597" height="967" alt="image" src="https://github.com/user-attachments/assets/caca1632-c6a6-4371-88db-70f05ee3ff9c" />
<img width="1595" height="969" alt="image" src="https://github.com/user-attachments/assets/3971cf7d-f82d-445f-9920-b447f5e92c12" />
<img width="1598" height="985" alt="image" src="https://github.com/user-attachments/assets/5f8470b1-1737-489a-89ea-fc58e3eae3e4" />


## 5. Ghi chú Kỹ thuật: Xác thực Toàn vẹn Dữ liệu (Database Validation)
Trong môi trường thực tế, để đảm bảo bản ghi đã được khởi tạo thành công vào Database chứ không chỉ báo ảo trên Client (API), kịch bản yêu cầu thực thi truy vấn SQL Server để đối chiếu chéo sau khi gọi lệnh `POST /users`:
