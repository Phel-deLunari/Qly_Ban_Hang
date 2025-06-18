Ứng Dụng Quản Lý Bán Nước Ngọt - Laravel
Tổng quan
Đây là một ứng dụng web được xây dựng bằng framework Laravel để quản lý cửa hàng bán nước ngọt. Ứng dụng bao gồm các chức năng xác thực người dùng, quản lý các đối tượng như Nước Ngọt (Drink), Khách Hàng (Customer), và Đơn Hàng (Order), cùng với các thao tác CRUD an toàn và API RESTful. Ứng dụng sử dụng Laravel Breeze cho xác thực, Laravel Sanctum cho xác thực API, và Eloquent ORM để quản lý cơ sở dữ liệu trên cloud (ví dụ: Aiven MySQL/PostgreSQL).
Tính năng

Xác thực người dùng: Hỗ trợ đăng ký, đăng nhập, đăng xuất và đặt lại mật khẩu thông qua Laravel Breeze.
Các đối tượng:
Nước Ngọt (Drink): Quản lý thông tin nước ngọt (tên, giá, mô tả).
Khách Hàng (Customer): Quản lý thông tin khách hàng (tên, email, số điện thoại).
Đơn Hàng (Order): Quản lý đơn hàng (nước ngọt, khách hàng, số lượng).


Thao tác CRUD: Hỗ trợ đầy đủ các thao tác tạo, đọc, cập nhật, xóa cho Đơn Hàng.
API: Cung cấp các endpoint API RESTful cho quản lý Đơn Hàng, sử dụng Laravel Sanctum.
Bảo mật:
Bảo vệ CSRF cho các biểu mẫu.
Ngăn chặn XSS bằng cách sử dụng Blade và vệ sinh dữ liệu đầu vào.
Xác thực dữ liệu đầu vào (validation).
Xác thực và phân quyền thông qua middleware.
Quản lý phiên (session) và cookie an toàn.
Truy vấn SQL an toàn với Eloquent ORM.


Cơ sở dữ liệu: Sử dụng Eloquent ORM để migrate các đối tượng vào cơ sở dữ liệu trên cloud (ví dụ: Aiven).
Liên kết công khai: [Chèn URL công khai của ứng dụng sau khi triển khai]

Yêu cầu

PHP >= 8.1
Composer
Laravel >= 10.x
MySQL/PostgreSQL (được cấu hình trên Aiven hoặc dịch vụ cloud tương tự)
Laravel Breeze
Laravel Sanctum
Node.js và NPM (cho tài nguyên frontend)

Hướng dẫn cài đặt

Sao chép kho mã nguồn:git clone [repository-url]
cd myWebApp


Cài đặt thư viện:composer install
npm install


Cấu hình môi trường:
Sao chép file .env.example thành .env và cập nhật thông tin cơ sở dữ liệu Aiven.

cp .env.example .env


Ví dụ cấu hình cơ sở dữ liệu:

DB_CONNECTION=mysql
DB_HOST=<aiven_host>
DB_PORT=<aiven_port>
DB_DATABASE=<aiven_database>
DB_USERNAME=<aiven_username>
DB_PASSWORD=<aiven_password>


Tạo khóa ứng dụng:php artisan key:generate


Chạy migration:php artisan migrate


**Biên

