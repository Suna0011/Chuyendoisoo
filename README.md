<h2 align="center">
    <a href="https://dainam.edu.vn/vi/khoa-cong-nghe-thong-tin">
    🎓 Faculty of Information Technology (DaiNam University)
    </a>
</h2>

<h2 align="center">
    HỆ THỐNG QUẢN LÝ CỬA HÀNG THỜI TRANG THÔNG MINH TRONG THỜI KỲ CHUYỂN ĐỔI SỐ
</h2>

<div align="center">
    <p align="center">
        <img alt="AIoTLab Logo" width="170" src="docs/aiotlab_logo.png" />
        <img alt="DaiNam University Logo" width="200" src="docs/fitdnu_logo.png" />
        <img alt="CNTT Logo" width="180" src="docs/dnu_logo.png" />
    </p>

[![AIoTLab](https://img.shields.io/badge/AIoTLab-green?style=for-the-badge)](https://www.facebook.com/DNUAIoTLab)
[![Faculty of Information Technology](https://img.shields.io/badge/Faculty%20of%20Information%20Technology-blue?style=for-the-badge)](https://dainam.edu.vn/vi/khoa-cong-nghe-thong-tin)
[![DaiNam University](https://img.shields.io/badge/DaiNam%20University-orange?style=for-the-badge)](https://dainam.edu.vn)
</div>

# HỆ THỐNG QUẢN LÝ CỬA HÀNG THỜI TRANG THÔNG MINH TRONG THỜI KỲ CHUYỂN ĐỔI SỐ

> Dự án chuyển đổi số cho cửa hàng thời trang, kết hợp website bán hàng (E-commerce) và hệ thống quản lý nội bộ (IMS – Inventory Management System) trên nền tảng .NET và SQL Server.

---

## 📌 Giới thiệu

Trong bối cảnh **chuyển đổi số**, cửa hàng thời trang không chỉ cần bán hàng trực tiếp tại cửa hàng mà còn phải:

- Bán hàng đa kênh (online + offline)
- Quản lý tồn kho, đơn hàng, khách hàng theo thời gian thực
- Cá nhân hóa trải nghiệm mua sắm
- Ra quyết định dựa trên dữ liệu

Dự án này xây dựng một **hệ thống quản lý thông minh** cho cửa hàng thời trang với các thành phần chính:

- **CSDL E-commerce**: `E-commerce Website Project Script.sql`
- **Website bán hàng (Client)**: `ClientSide-Kahreedo.pk.sln`
- **Hệ thống quản lý kho (IMS)**: `IMS-Project.sln`

---

## 🎯 Mục tiêu dự án

- Số hóa toàn bộ dữ liệu: sản phẩm, khách hàng, đơn hàng, thanh toán, vận chuyển
- Quản lý tập trung trong một hệ thống duy nhất
- Hỗ trợ quản lý kho thông minh & đồng bộ với đơn hàng
- Nâng cao trải nghiệm khách hàng (wishlist, sản phẩm xem gần đây, đánh giá,…)
- Tạo nền tảng mở rộng cho các tính năng phân tích & AI sau này

---

## 🧩 Các module chính

### 1. Quản lý sản phẩm & danh mục

- Danh mục & tiểu danh mục (nam, nữ, trẻ em, phụ kiện, thể thao,…)
- Thông tin sản phẩm:
  - Tên, giá hiện tại, giá cũ
  - Size, tồn kho
  - Hình ảnh, mô tả ngắn/dài
  - Gắn nhãn: `SALE`, `HOT`, `SOLD OUT`,...

### 2. Quản lý khách hàng & hành vi

- Hồ sơ khách hàng (thông tin cá nhân, liên hệ, địa chỉ)
- Lịch sử mua hàng
- Wishlist (danh sách yêu thích)
- Recently viewed (sản phẩm đã xem)
- Đánh giá & nhận xét sản phẩm

### 3. Đơn hàng & thanh toán

- Tạo đơn hàng, chi tiết đơn hàng
- Tính tổng tiền, thuế, chiết khấu
- Trạng thái đơn: tạo, đang xử lý, đã giao, đã hủy,…
- Nhiều phương thức thanh toán (COD, thẻ, ví điện tử, v.v.)
- Quản lý thông tin giao hàng

### 4. Quản lý kho (IMS)

- Theo dõi tồn kho theo từng sản phẩm
- Nhập – xuất kho
- Tự động trừ kho khi có đơn hàng
- Hỗ trợ kiểm kê, cập nhật số lượng

### 5. Phân quyền & quản trị

- Tài khoản quản trị & nhân viên
- Phân quyền theo vai trò: `Admin`, `Employee`, `User`
- Giao diện quản trị để:
  - Quản lý sản phẩm, đơn hàng, khách hàng
  - Xem báo cáo cơ bản

### 6. Marketing & giao diện người dùng

- Slider/banner khuyến mãi trên trang chủ
- Khu vực hiển thị:
  - Hàng mới về
  - Sản phẩm bán chạy
  - Sản phẩm giảm giá
- Hỗ trợ trải nghiệm mua sắm trực tuyến cho khách hàng cuối

---

## 🏗️ Kiến trúc tổng quan

- **Frontend**:
  - Website bán hàng cho khách hàng (ASP.NET Web)
  - Giao diện quản trị cho Admin/nhân viên

- **Backend**:
  - Xử lý logic đơn hàng, thanh toán, cập nhật kho
  - Áp dụng khuyến mãi, badge sản phẩm
  - Phân quyền & xác thực người dùng

- **Database (SQL Server)**:
  - Bảng sản phẩm, danh mục, nhà cung cấp
  - Bảng khách hàng, đơn hàng, chi tiết đơn
  - Bảng thanh toán, giao hàng
  - Bảng wishlist, recently views, review
  - Bảng tài khoản, nhân viên, roles

---

## 🛠️ Công nghệ sử dụng

- **Ngôn ngữ**: C#
- **Framework**: ASP.NET (Web Forms / MVC tùy cấu trúc solution)
- **CSDL**: Microsoft SQL Server
- **IDE**: Visual Studio 2013 trở lên

---

## 🚀 Cài đặt & chạy dự án

### 1. Chuẩn bị môi trường

- Cài **SQL Server** / **SQL Server Express**
- Cài **Visual Studio 2013+** (.NET, ASP.NET, C#, SQL Server tools)

### 2. Tạo cơ sở dữ liệu

1. Mở file:

   ```text
   E-commerce Website Project Script.sql
Thực thi script trong SQL Server Management Studio (SSMS):

Tạo database (ví dụ: Kahreedo)

Tạo bảng, khóa ngoại

Insert dữ liệu mẫu (sản phẩm, khách, đơn hàng,…)

3. Chạy website bán hàng

Mở solution:

ClientSide-Kahreedo.pk.sln


Cập nhật chuỗi kết nối (connection string) trong file cấu hình (ví dụ: Web.config) trỏ tới database vừa tạo.

Build & Run trực tiếp từ Visual Studio (IIS Express).

4. Chạy hệ thống IMS (quản lý kho)

Mở solution:

IMS-Project.sln


Cập nhật connection string (nếu cần) để trỏ về cùng database (hoặc DB kho riêng nếu bạn tách).

Build & Run từ Visual Studio.

## 🔮 Hướng phát triển trong tương lai

Dashboard BI (doanh thu, lợi nhuận, top sản phẩm, phân khúc khách hàng,…)

Kết nối POS tại cửa hàng → mô hình omni-channel

Tích hợp AI gợi ý sản phẩm dựa trên:

Lịch sử mua

Wishlist

Sản phẩm đã xem

Nâng cấp responsive / PWA cho trải nghiệm mobile

Tăng cường bảo mật & logging

📂 Cấu trúc repo (gợi ý)
.
├── README.md
├── database/
│   └── E-commerce Website Project Script.sql
├── src/
│   ├── ClientSide-Kahreedo.pk.sln
│   └── IMS-Project.sln
└── docs/
    └── (tài liệu thêm nếu có)

## 👤 Tác giả / Thông tin

Mô tả: Đồ án/chuyên đề về chuyển đổi số cửa hàng thời trang với hệ thống quản lý thông minh.

Người phát triển:Hoàng Thé Khải
