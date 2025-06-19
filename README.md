# Ứng Dụng Quản Lý Bán Nước Ngọt - Laravel

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
7. **Liên Kết Công Khai**:
   - [Chèn URL sau khi triển khai]

---

## Yêu Cầu
- PHP >= 8.1
- Composer
- Laravel >= 10.x
- MySQL/PostgreSQL (Aiven hoặc dịch vụ cloud)
- Laravel Breeze
- Laravel Sanctum
- Node.js và NPM

---

## Hướng Dẫn Cài Đặt
1. **Sao chép mã nguồn**:
   ```bash
   git clone [repository-url]
   cd myWebApp
   ```
2. **Cài đặt thư viện**:
   ```bash
   composer install
   npm install
   ```
3. **Cấu hình môi trường**:
   - Sao chép file `.env.example` thành `.env`:
   ```bash
   cp .env.example .env
   ```
   - Cập nhật thông tin cơ sở dữ liệu Aiven:
   ```env
   DB_CONNECTION=mysql
   DB_HOST=<aiven_host>
   DB_PORT=<aiven_port>
   DB_DATABASE=<aiven_database>
   DB_USERNAME=<aiven_username>
   DB_PASSWORD=<aiven_password>
   ```
4. **Tạo khóa ứng dụng**:
   ```bash
   php artisan key:generate
   ```
5. **Chạy migration**:
   ```bash
   php artisan migrate
   ```
6. **Biên dịch tài nguyên frontend**:
   ```bash
   npm run dev
   ```
7. **Khởi động server**:
   ```bash
   php artisan serve
   ```

---

## Sử Dụng API
- **Endpoint**: `/api/orders` (GET, POST, PUT, DELETE).
- **Xác thực**: Sử dụng token Sanctum.
- Ví dụ yêu cầu:
   ```bash
   curl -H "Authorization: Bearer <token>" http://localhost:8000/api/orders
   ```

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
