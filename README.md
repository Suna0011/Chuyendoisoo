<h2 align="center">
    <a href="https://dainam.edu.vn/vi/khoa-cong-nghe-thong-tin">
    🎓 Faculty of Information Technology (DaiNam University)
    </a>
</h2>

<h2 align="center">
HỆ THỐNG QUẢN LÝ CỬA HÀNG THỜI TRANG THÔNG MINH TRONG THỜI KỲ 
    CHUYỂN ĐỔI SỐ
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


## 🎯1. Giới thiệu

Dự án phù hợp cho:
* Đồ án môn học / Bài tập lớn chuyên ngành CNTT.
* Người mới học **ASP.NET MVC** muốn tham khảo cấu trúc dự án thực tế.
* Demo cách tích hợp **GenAI (LLM)** vào website truyền thống.

### Tính năng chính
* ✅ **Người dùng:** Đăng ký, Đăng nhập, Quản lý hồ sơ.
* ✅ **Sản phẩm:** Danh mục, Tìm kiếm (Autocomplete), Chi tiết sản phẩm.
* ✅ **Mua sắm:** Giỏ hàng (Cart), Wishlist, Thanh toán (Checkout).
* ✅ **Quản trị:** Quản lý sản phẩm qua Database.
* ✅ **AI Chatbot (New):** Tư vấn mua hàng từng bước (Step-by-step).

---

## 🛠️2. Công nghệ sử dụng

| Lĩnh vực | Công nghệ | Chi tiết |
| :--- | :--- | :--- |
| **Backend** | ASP.NET MVC 5 | C# .NET Framework |
| | Entity Framework | ORM xử lý dữ liệu |
| | SQL Server | Microsoft SQL Server / LocalDB |
| **Frontend** | HTML5 / CSS3 | Giao diện người dùng |
| | Bootstrap | Responsive Design |
| | jQuery & AJAX | Xử lý sự kiện không tải lại trang |
| | jQuery UI | Autocomplete cho ô tìm kiếm |
| **AI / API** | OpenRouter API | Cổng kết nối AI (Free tier) |
| | LLaMA 3.1 Instruct | Mô hình ngôn ngữ xử lý tư vấn |

---

## 📸3. Hình ảnh & Demo


### a. Trang chủ & Sản phẩm
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/790ac14e-24b1-4b79-aa0e-418bdbca49b1" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/bb206c0f-f5ce-4d0b-acf9-4ae20bbeeec6" />

### b. Chatbot AI Tư vấn
Giao diện Chatbot bong bóng ở góc phải, hỏi từng bước để lấy thông tin khách hàng.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/90dc0a7a-fc06-4c8f-ada9-ce9084887fa4" />

### c. Giỏ hàng & Thanh toán

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0fc5e2f6-fc50-4493-9a80-81cb96654c92" />

### d. Trang Admin

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9d02ea58-060c-4500-948b-23f2e13c6f55" />

---

## 🚀 4. Hướng dẫn cài đặt (Chi tiết)
Để dự án chạy thành công mà không gặp lỗi kết nối Database hay thiếu thư viện, vui lòng làm đúng theo các bước sau:

### Bước 1: Clone Project

### Bước 2: Khởi tạo Database (Bắt buộc)
    - Lưu ý: Nếu không chạy bước này, web sẽ báo lỗi kết nối SQL.
    
    - Mở SQL Server Management Studio (SSMS).
    
    - Mở file script: E-commerce Website Project Script.sql (nằm trong thư mục gốc của dự án).
    
    - Nhấn Execute (F5) để chạy script.
    
    - Kiểm tra lại trong danh sách Database xem đã có database tên là Kahreedo_Ecommerce (hoặc tên trong script của bạn) chưa.

### Bước 3: Cấu hình Web.config (Quan trọng)
    - Mở file Web.config trong Visual Studio. Bạn cần sửa 2 vị trí sau đây để web kết nối được Database và Chatbot.

#### 1. Cấu hình chuỗi kết nối (Connection Strings) Tìm thẻ <connectionStrings>. Copy đoạn dưới đây và thay thế vào (lưu ý sửa Data Source):

<connectionStrings>
    <add name="DefaultConnection" 
         connectionString="Data Source=YOUR_SERVER_NAME;Initial Catalog=Kahreedo_Ecommerce;Integrated Security=True" 
         providerName="System.Data.SqlClient" />
    
    <add name="KahreedoEntities" 
         connectionString="metadata=res://*/Models.Model1.csdl|res://*/Models.Model1.ssdl|res://*/Models.Model1.msl;provider=System.Data.SqlClient;provider connection string=&quot;data source=YOUR_SERVER_NAME;initial catalog=Kahreedo_Ecommerce;integrated security=True;MultipleActiveResultSets=True;App=EntityFramework&quot;" 
         providerName="System.Data.EntityClient" />
</connectionStrings>

#### 2. Cấu hình API Key cho Chatbot Tìm thẻ <appSettings>. Thêm key OpenRouter vào để Chatbot hoạt động:

<appSettings>
    <add key="webpages:Version" value="3.0.0.0" />
    <add key="webpages:Enabled" value="false" />
    <add key="ClientValidationEnabled" value="true" />
    <add key="UnobtrusiveJavaScriptEnabled" value="true" />

    <add key="OpenRouterApiKey" value="sk-or-v1-your-api-key-here" />
</appSettings>

### Bước 4: Cài đặt thư viện (Restore Packages)

    - Để đảm bảo dự án có đầy đủ các thư viện cần thiết (Newtonsoft.Json, EntityFramework, jQuery…), bạn làm như sau:

    - Mở Visual Studio

    - Tại thanh Solution Explorer → chuột phải vào Solution 'ClientSide-Kahreedo...'

    - Chọn Restore NuGet Packages

### Bước 5: Khởi chạy dự án

    - Nhấn F5 hoặc nút Start Debugging (biểu tượng ▶️ màu xanh)

    - Visual Studio sẽ tự mở trình duyệt và chạy website

### 🔐 Tài khoản Quản trị (Admin)

- Dùng để đăng nhập trang CMS quản lý sản phẩm, người dùng, đơn hàng.

| Thông tin    | Giá trị    |
| ------------ | ---------- |
| **User**     | `admin`    |
| **Password** | `admin123` |

---

## 📞5. Liên hệ
Nếu bạn cần hỗ trợ cài đặt, tùy chỉnh giao diện hoặc nâng cấp tính năng AI, vui lòng liên hệ:

- Tác giả: Nhóm 7 

- Email: khaihoang051103@gmail.com
