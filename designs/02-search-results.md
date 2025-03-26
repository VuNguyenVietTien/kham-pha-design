# Thiết Kế Màn Hình Kết Quả Tìm Kiếm (Search Results)

## Tổng Quan
Màn hình Kết quả tìm kiếm hiển thị các kết quả dựa trên từ khóa người dùng nhập vào thanh tìm kiếm. Màn hình này phải cung cấp khả năng lọc, sắp xếp và duyệt các kết quả một cách hiệu quả.

## Bố Cục Chung
![Search Results Layout](../assets/search-layout.png)

### Thành Phần Chính
1. **Navbar** (giống màn hình Trang chủ)

2. **Main Content Container**
   - Sidebar (Bên trái)
   - Kết quả tìm kiếm (Bên phải)

3. **Footer** (giống màn hình Trang chủ)

## Chi Tiết Thiết Kế

### Sidebar (Bộ lọc)
- Chiều rộng: 280-320px (Desktop), có thể ẩn/hiện trên Tablet/Mobile
- Nền: Màu nhạt hơn so với nền trang (Light: #F5F5F7, Dark: #252525)
- Các bộ lọc (từ trên xuống dưới):

  1. **Loại nội dung**
     - Radio buttons hoặc Checkbox
     - Options: Tất cả, Điểm đến, Địa điểm, Cửa hàng, Sản phẩm, Khách sạn, Sự kiện, Kỳ nghỉ cho thuê
     - Icon nhỏ đi kèm mỗi option
  
  2. **Vị trí**
     - Dropdown/Select cascade
     - Các cấp: Tỉnh/Thành phố → Quận/Huyện → Phường/Xã

  3. **Danh mục/Tags**
     - Checkbox list hoặc Multi-select
     - UI dạng chip/tags (có thể bỏ chọn bằng cách click vào "x")

  4. **Đánh giá**
     - UI dạng star rating (1-5 sao)
     - Có thể chọn "Từ X sao trở lên"

  5. **Giá**
     - Dạng slider với 2 đầu kéo (min-max)
     - Hoặc các khoảng giá định sẵn (radio buttons)
     - Đơn vị tiền tệ VND

  6. **Bộ lọc riêng**
     - Xuất hiện dựa trên loại nội dung đang chọn
     - Ví dụ: Tiện nghi khách sạn, Loại hình sự kiện

  7. **Buttons**
     - "Áp dụng bộ lọc" (Primary button)
     - "Xóa bộ lọc" (Secondary/Text button)

### Khu Vực Kết Quả (Bên phải)
- Header:
  - Tiêu đề: "Kết quả tìm kiếm cho '[Từ khóa]'" (font size lớn)
  - Số lượng kết quả: "XX kết quả"

- Toolbar:
  - Tabs Lọc Nhanh (Optional): Lặp lại các tab loại nội dung để chuyển đổi nhanh
  - Dropdown Sắp xếp: "Liên quan nhất", "Mới nhất", "Đánh giá cao → thấp", "Giá thấp → cao"

- Lưới Kết quả:
  - Layout tương tự Card Grid ở trang chủ
  - Card thiết kế giống với các loại card ở trang chủ
  - Phân biệt loại kết quả bằng nhãn nhỏ hoặc icon đặc trưng

- Phân trang:
  - Vị trí: Cuối danh sách kết quả
  - Thiết kế: Buttons với số trang, nút Previous/Next
  - Hoặc: Infinite scroll/Load more button

### Responsive Design
- **Desktop (>1200px)**: Hiển thị đầy đủ, sidebar mở
- **Tablet (768px-1200px)**:
  - Sidebar có thể ẩn/hiện qua nút "Bộ lọc"
  - Grid layout chuyển sang 2-3 cột
- **Mobile (<768px)**:
  - Sidebar chuyển thành modal full-screen khi click vào "Bộ lọc"
  - Grid layout chuyển sang 1 cột
  - Dropdown Sắp xếp có thể ẩn trong menu dots (...)

### Empty State
- Khi không có kết quả nào phù hợp:
  - Minh họa thân thiện (illustration)
  - Thông báo "Không tìm thấy kết quả cho '[Từ khóa]'"
  - Gợi ý tìm kiếm khác: "Hãy thử từ khóa khác hoặc điều chỉnh bộ lọc"
  - Hoặc hiển thị "Có thể bạn quan tâm" với các đề xuất liên quan

## Tương Tác
- **Filter Feedback**: Khi áp dụng bộ lọc, hiển thị các filter đã chọn dưới dạng chip ở đầu khu vực kết quả (có thể remove từng cái)
- **Lazy Loading**: Tải thêm nội dung khi cuộn xuống (nếu dùng infinite scroll)
- **Sort Animation**: Hiệu ứng nhẹ khi thay đổi sắp xếp (các card xáo trộn vị trí)
- **Mobile Filter**: Nút "Áp dụng" đặt ở bottom sticky khi mở filter trên mobile