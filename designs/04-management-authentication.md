# Thiết Kế Khu Vực Quản Lý Nội Dung và Xác Thực

## 1. Màn Hình Quản Lý Nội Dung (User Management Portal)

### Tổng Quan
Khu vực quản lý dành cho người dùng có vai trò đặc biệt (Chủ cửa hàng, Chủ khách sạn/Host, Người tổ chức sự kiện) sau khi đăng nhập. Đây là giao diện dạng Dashboard giúp người dùng quản lý thông tin về cửa hàng, sản phẩm, khách sạn, kỳ nghỉ, và sự kiện của họ.

### Bố Cục Chung
![Management Portal Layout](../assets/management-layout.png)

#### Thành Phần Chính
1. **Header** (có thể là header riêng hoặc dùng Navbar chung)
   - Logo "Khám Phá" (phiên bản nhỏ hơn)
   - Breadcrumbs riêng cho khu vực quản lý
   - Thông tin người dùng đang đăng nhập
   - Notifications icon
   - Nút "Quay lại trang chủ"

2. **Sidebar Điều hướng Quản lý** (bên trái, cố định)
   - Thông tin người dùng/doanh nghiệp rút gọn (Avatar + Tên)
   - Menu điều hướng chính:
     - Tổng quan (Dashboard)
     - Quản lý Cửa hàng (Stores)
     - Quản lý Sản phẩm (Products)
     - Quản lý Khách sạn/Nơi ở (Accommodations)
     - Quản lý Kỳ nghỉ cho thuê (Stay Listings)
     - Quản lý Sự kiện (Events)
     - Công cụ QR Code
     - Đánh giá & Phản hồi
     - Thống kê
     - Hồ sơ / Cài đặt

3. **Main Content Area** (bên phải)
   - Header khu vực với tiêu đề section
   - Nội dung tương ứng với mục được chọn trên Sidebar

### Chi Tiết Thiết Kế

#### Dashboard (Tổng quan)
- **Stats Cards Row**: 4-6 card hiển thị số liệu nhanh
  - Lượt xem (tháng này vs. tháng trước)
  - Đánh giá mới
  - Yêu cầu mới
  - Lượt lưu/yêu thích
  
- **Charts Section**:
  - Biểu đồ cột/đường: Lượng truy cập theo thời gian
  - Biểu đồ tròn: Phân bố đánh giá

- **Recent Activities**:
  - Timeline hoặc list các hoạt động gần đây
  - Mỗi item gồm icon, timestamp, nội dung, link

- **Quick Actions**:
  - Các nút lối tắt đến hành động thường dùng
  - Layout dạng grid với icon + text

#### Trang Danh sách (Ví dụ: Quản lý Cửa hàng)
- **Toolbar**:
  - Thanh tìm kiếm (Search box)
  - Bộ lọc (Filters dropdown)
  - Nút "Thêm mới" (Primary button, nổi bật)
  - Dropdown sắp xếp (Sort by)

- **Data Table / Grid**:
  - Header row với tên cột
  - Mỗi row là một mục (Cửa hàng, Sản phẩm...)
  - Các cột chính: Tên, Trạng thái, Ngày tạo, Lượt xem, Rating...
  - Action icons trên mỗi dòng: Xem, Sửa, Xóa, Ẩn/Hiện
  - Checkbox cho multi-select actions

- **Pagination / Infinite Scroll**:
  - Pagination controls ở cuối bảng
  - Hoặc infinite scroll với loading indicator

#### Trang Tạo/Chỉnh sửa (Ví dụ: Thêm/Sửa Cửa hàng)
- **Form Layout**:
  - 1 cột hoặc 2 cột (responsive)
  - Section headers phân nhóm các trường liên quan
  - Trường bắt buộc có indicator (*)

- **Các loại Input Field**:
  - Text inputs, Textareas, Dropdowns, Radio buttons, Checkboxes
  - Date/Time pickers
  - Location picker (với map)
  - Tag input (chips)
  - Rich text editor (mô tả chi tiết)
  - File upload (hình ảnh, với preview)

- **Form Validation**:
  - Hiển thị lỗi dưới từng trường
  - Highlight trường lỗi
  - Summary lỗi ở đầu form (nếu nhiều lỗi)

- **Buttons**:
  - "Lưu" (Primary, fixed ở bottom)
  - "Lưu nháp" (Secondary)
  - "Hủy" (Tertiary/Text)
  - "Xóa" (Danger, nếu là edit mode)

#### Trang Công cụ QR Code
- **Current QR Display**:
  - QR Code lớn, rõ ràng
  - Hiển thị URL đang được mã hóa
  - Timestamp tạo/cập nhật

- **Generator Form**:
  - Input URL Menu/Đặt hàng
  - Dropdown chọn Cửa hàng (nếu có nhiều)
  - Tùy chọn màu sắc, logo trong QR

- **Buttons**:
  - "Tạo/Cập nhật QR Code"
  - "Tải về PNG"
  - "Tải về SVG"
  - "In"

### Responsive Design
- **Desktop (>1200px)**:
  - Sidebar luôn hiển thị
  - Layout 2 cột cho một số form
  - Data tables hiển thị đầy đủ cột

- **Tablet (768px-1200px)**:
  - Sidebar có thể thu gọn (toggle)
  - Data tables ẩn một số cột ít quan trọng

- **Mobile (<768px)**:
  - Sidebar ẩn hoàn toàn (slide in khi click hamburger)
  - Forms chuyển sang 1 cột
  - Data tables chuyển sang card layout (mỗi row là 1 card)

## 2. Màn Hình Xác Thực (Authentication)

### Đăng nhập (/login)
- **Bố cục**:
  - Logo "Khám Phá" (centered, top)
  - Form container (card với shadow nhẹ)
  - Footer links

- **Form Elements**:
  - Tiêu đề "Đăng nhập"
  - Input: Email/Tên đăng nhập
  - Input: Mật khẩu (có toggle show/hide)
  - Checkbox: "Ghi nhớ đăng nhập"
  - Link: "Quên mật khẩu?" (góc phải)
  - Button: "Đăng nhập" (full width, primary)
  - Divider "hoặc"
  - Social login buttons (Google, Facebook)
  - Text + Link: "Chưa có tài khoản? Đăng ký"

- **Validation**:
  - Error messages inline
  - Form-level errors (ví dụ: sai thông tin đăng nhập)

### Đăng ký (/register)
- **Bố cục**: Tương tự màn hình Đăng nhập

- **Form Elements**:
  - Tiêu đề "Đăng ký"
  - Input: Họ tên
  - Input: Email
  - Input: Mật khẩu (có strength indicator)
  - Input: Xác nhận mật khẩu
  - Checkbox: "Tôi đồng ý với Điều khoản & Chính sách"
  - Button: "Đăng ký" (full width, primary)
  - Divider "hoặc"
  - Social signup buttons (Google, Facebook)
  - Text + Link: "Đã có tài khoản? Đăng nhập"

- **Multi-step Registration** (tùy chọn):
  - Step 1: Thông tin cơ bản (như trên)
  - Step 2: Thông tin bổ sung (địa chỉ, SĐT...)
  - Step 3: Tùy chọn vai trò (Người dùng thông thường/Chủ cửa hàng/Host...)
  - Progress indicator hiển thị bước hiện tại

### Quên Mật khẩu (/forgot-password)
- **Bố cục**: Đơn giản hóa từ màn hình Đăng nhập

- **Form Elements**:
  - Tiêu đề "Quên mật khẩu"
  - Text giải thích
  - Input: Email
  - Button: "Gửi link đặt lại mật khẩu"
  - Link: "Quay lại đăng nhập"

- **Success State**:
  - Thông báo đã gửi email
  - Hướng dẫn kiểm tra hộp thư
  - Button: "Gửi lại email" (disabled với countdown timer)

### Đặt lại Mật khẩu (/reset-password)
- **Bố cục**: Tương tự Quên Mật khẩu

- **Form Elements**:
  - Tiêu đề "Đặt lại mật khẩu"
  - Input: Mật khẩu mới (có strength indicator)
  - Input: Xác nhận mật khẩu mới
  - Button: "Đặt lại mật khẩu"

- **Success State**:
  - Thông báo thành công
  - Button: "Đăng nhập ngay"

### Theme & Style
- **Authentication Screens**:
  - Màu sắc: Tối giản, tập trung vào nội dung
  - Nền: Màu nhẹ hoặc pattern/gradient tinh tế
  - Minh họa: Có thể thêm illustrations liên quan đến chủ đề (travel, discovery)
  - Typography rõ ràng, dễ đọc

- **Management Portal**:
  - Màu chủ đạo: Khác biệt với frontend để phân biệt rõ khu vực
  - Sidebar: Màu nền đậm hơn, text và icons sáng
  - Content area: Màu nền nhạt, tối ưu cho việc đọc và tương tác với dữ liệu
  - Các nút hành động: Màu sắc theo semantic (Primary, Danger, Success...)