# Ứng Dụng Quản Lý Bán Nước Ngọt - Laravel

## 👤 Thông Tin Cá Nhân  
- **Họ tên**: Nguyễn Minh Đức 
- **Mã sinh viên**: 23010171
- **Lớp**: CNTT_2
- **Môn học**: Xây dựng web nâng cao (TH3)

## Tổng Quan
Ứng dụng web này được xây dựng bằng framework **Laravel** để quản lý cửa hàng bán nước ngọt. Ứng dụng hỗ trợ xác thực người dùng, quản lý các đối tượng như *Nước Ngọt*, *Khách Hàng* và *Đơn Hàng*, cùng với các thao tác CRUD an toàn và API RESTful. Công nghệ chính bao gồm:
- **Laravel Breeze**: Xác thực người dùng.
- **Laravel Sanctum**: Xác thực API.
- **Eloquent ORM**: Quản lý cơ sở dữ liệu trên cloud (ví dụ: Aiven).

---

## Tính Năng
1. **Xác Thực Người Dùng**:
   - Đăng ký, đăng nhập, đăng xuất, đặt lại mật khẩu.
2. **Các Đối Tượng**:
   - **Nước Ngọt**: Quản lý tên, giá, mô tả.
   - **Khách Hàng**: Quản lý tên, email, số điện thoại.
   - **Đơn Hàng**: Liên kết giữa nước ngọt và khách hàng (số lượng).
3. **Thao Tác CRUD**:
   - Tạo, đọc, cập nhật, xóa đơn hàng.
4. **API**:
   - Cung cấp endpoint RESTful cho quản lý đơn hàng.
5. **Bảo Mật**:
   - Chống CSRF cho biểu mẫu.
   - Ngăn chặn XSS qua Blade và vệ sinh dữ liệu.
   - Xác thực dữ liệu đầu vào.
   - Phân quyền qua middleware.
   - Phiên và cookie an toàn.
   - Truy vấn SQL an toàn với Eloquent.
6. **Cơ Sở Dữ Liệu**:
   - Migrate dữ liệu lên cloud (Aiven MySQL/PostgreSQL).
---

## ⚙ Hệ thống sử dụng
- PHP (Laravel framework)
- Laravel Breeze
- MySQL (Aiven Cloud)
- Eloquent ORM (Hệ thống ORM giúp tương tác với CSDL)
- Frontend & UI (Blade engine, Tailwind CSS, Bootstrap 5)
- Laravel Security (Framework hỗ trợ)
- AJAX JQuery (Phục vụ tìm kiếm)
---

## Biện Pháp Bảo Mật
- **CSRF**: Biểu mẫu có token CSRF.
- **XSS**: Dữ liệu được vệ sinh qua Blade.
- **Xác thực dữ liệu**: Kiểm tra đầu vào phía server.
- **Phân quyền**: Middleware giới hạn truy cập.
- **SQL Injection**: Eloquent đảm bảo truy vấn an toàn.
- **Session/Cookies**: Phiên an toàn, cookie mã hóa.

---

## Cải Tiến Tương Lai
- Thêm tìm kiếm và lọc cho nước ngọt, khách hàng.
- Phân quyền vai trò (admin, user).
- Mở rộng API cho Nước Ngọt và Khách Hàng.
