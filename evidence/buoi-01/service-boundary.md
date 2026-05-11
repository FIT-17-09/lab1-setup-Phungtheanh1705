# Service Boundary của nhóm

## 1. Thông tin nhóm

- Tên nhóm: 4
- Lớp: CNTT 17-09
- Thành viên: Phùng Thế Anh
- Service nhóm phụ trách: Core Business Service
- Sản phẩm tổng thể của lớp: Smart Campus System

## 2. Actor

- Sinh viên
- Giảng viên
- Quản trị viên
- Hệ thống IoT/thiết bị cảm biến
- Service Gateway
- Notification Service

## 3. System Boundary

Nhóm xây dựng phần xử lý nghiệp vụ trung tâm của hệ thống Smart Campus.

### Phần nhóm kiểm soát

- Xử lý luật nghiệp vụ
- Phân tích sự kiện bất thường
- Sinh cảnh báo
- Kiểm tra điều kiện hợp lệ
- Quản lý logic xử lý dữ liệu
- Cung cấp API cho service khác

### Phần nhóm chỉ tích hợp

- Database Service
- Notification Service
- Authentication Service
- API Gateway
- Frontend Dashboard

## 4. Service Boundary

### Service có trách nhiệm

- Tiếp nhận dữ liệu từ các service khác
- Xử lý nghiệp vụ trung tâm
- Kiểm tra điều kiện bất thường
- Sinh cảnh báo nếu có lỗi hoặc vi phạm
- Trả kết quả xử lý về hệ thống

### Service KHÔNG làm

- Không quản lý giao diện người dùng
- Không xác thực đăng nhập
- Không lưu trữ dữ liệu lâu dài
- Không gửi email/SMS trực tiếp
- Không xử lý giao tiếp phần cứng

## 5. Input / Output

### Input

- Dữ liệu cảm biến
- Thông tin sinh viên
- Sự kiện từ hệ thống
- Request API từ service khác

### Output

- Kết quả xử lý nghiệp vụ
- Trạng thái hợp lệ/bất thường
- Cảnh báo hệ thống
- API response JSON

## 6. API dự kiến

| Method | Endpoint | Mục đích |
|---|---|---|
| GET | /health | Kiểm tra service |
| POST | /events/process | Xử lý sự kiện |
| POST | /alerts/create | Tạo cảnh báo |
| GET | /alerts | Lấy danh sách cảnh báo |
| GET | /rules | Lấy danh sách luật nghiệp vụ |
| POST | /rules | Tạo luật nghiệp vụ mới |


## 7. Phụ thuộc service khác

### Service này gọi đến

- Authentication Service
- Notification Service
- Database Service

### Service gọi đến service này

- API Gateway
- Frontend Dashboard
- IoT Gateway
- Monitoring Service

## 8. Sơ đồ minh họa

<img width="823" height="526" alt="image" src="https://github.com/user-attachments/assets/b6d5d924-51e3-40fc-a823-305e2a03f728" />

