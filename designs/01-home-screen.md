# Thiết Kế Màn Hình Trang Chủ (Home Screen)

## Tổng Quan
Màn hình Trang chủ là điểm khởi đầu của người dùng khi truy cập vào trang web "Khám Phá". Nó nên mang đến trải nghiệm hấp dẫn và giúp người dùng dễ dàng khám phá các nội dung.

## Bố Cục Chung
![Home Screen Layout](../assets/home-layout.png)

### Thành Phần Chính
1. **Navbar**
   - Logo "Khám Phá" (bên trái)
   - Thanh tìm kiếm chính (giữa)
   - Nút chuyển đổi sáng/tối (bên phải)
   - Khu vực người dùng (bên phải ngoài cùng)

2. **Main Content**
   - Tiêu đề chính "Khám Phá - Đi đâu? Mua gì? Ở đâu?"
   - Tabs điều hướng nội dung
   - Lưới Card (Card Grid)
   - Các khu vực nổi bật

3. **Footer**
   - Copyright © Khám Phá [Năm]
   - Các liên kết: Về chúng tôi, Liên hệ, Điều khoản sử dụng, Chính sách bảo mật
   - Liên kết mạng xã hội

## Chi Tiết Thiết Kế

### Navbar
- Chiều cao: 64px
- Nền: Trắng (#FFFFFF) / Tối (#1A1A1A)
- Shadow: nhẹ (0px 2px 4px rgba(0, 0, 0, 0.1))
- Logo: Góc trái, kích thước vừa phải (120px-150px)
- Thanh tìm kiếm: Chiều rộng 40-50% của màn hình, bo tròn viền
- Biểu tượng sáng/tối: Icon mặt trời/mặt trăng, có animation chuyển đổi
- Khu vực user: 
  - Chưa đăng nhập: Hai nút "Đăng nhập" và "Đăng ký"
  - Đã đăng nhập: Avatar người dùng (có dropdown menu)

### Tabs Điều Hướng Nội Dung
- Vị trí: Ngay dưới tiêu đề chính
- Các tab: "Điểm đến", "Địa điểm", "Cửa hàng", "Khách sạn", "Sự kiện", "Cho thuê kỳ nghỉ"
- Tab đang chọn: Màu nổi bật, có gạch chân/highlight
- Animation: Hiệu ứng mềm mại khi chuyển tab

### Lưới Card (Card Grid)
- Layout: Grid layout linh hoạt (CSS Grid/Flexbox)
- Desktop: 4 cột, Tablet: 2-3 cột, Mobile: 1 cột
- Khoảng cách giữa các card: 16px-24px
- Hiệu ứng hover: Scale nhẹ (1.02-1.05) và shadow tăng lên

### Khu Vực Nổi Bật
- Header mỗi khu vực: Font size lớn, font weight đậm
- Nút "Xem tất cả": Góc phải của header
- Các section:
  - "Gợi ý Gần bạn" (nếu có quyền truy cập vị trí)
  - "Điểm đến Hấp dẫn"
  - "Sự kiện Sắp diễn ra"
  - "Khách sạn/Resort Đáng chú ý"

### Lazy Loading / Infinite Scroll
- Tải thêm nội dung khi người dùng cuộn xuống cuối trang
- Hiển thị animation loading nhẹ nhàng

## Responsive Design
- **Desktop (>1200px)**: Hiển thị đầy đủ, 4 cột card
- **Tablet (768px-1200px)**: 2-3 cột card, có thể rút gọn một số thành phần
- **Mobile (<768px)**:
  - 1 cột card
  - Navbar có thể chuyển thành hamburger menu
  - Tabs có thể scroll ngang

## Theme Colors
- Chủ đạo: 2-3 màu thương hiệu (VD: Xanh dương #2D72D9, Cam #FF8C38)
- Light theme: Nền trắng (#FFFFFF), Text chính (#1A1A1A)
- Dark theme: Nền tối (#1A1A1A), Text chính (#F5F5F5)
- Màu nhấn: Dùng cho CTA, highlight tab đang chọn

## Components
### Destination Card
- Ảnh: Tỷ lệ 16:9, cover hoặc contain
- Tên điểm đến: Font size lớn, đậm
- Tags: Hiển thị dưới tên, nền màu nhẹ, bo tròn
- Rating: Hiển thị sao (★) kèm số lượng đánh giá

### Other Cards
Tương tự nhưng với nội dung phù hợp với từng loại thông tin (Location, Store, Hotel, Event, Stay Listing)