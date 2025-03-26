# Thiết Kế Các Màn Hình Chi Tiết (Detail Screens)

## Cấu Trúc Chung Cho Các Màn Hình Chi Tiết
Tất cả các màn hình chi tiết (Destination, Location, Store, Product, Hotel, Stay Listing, Event) đều có cấu trúc chung như sau:

### Header Section
- **Breadcrumbs**
  - Vị trí: Đầu trang
  - Format: Khám Phá > [Tên Điểm đến] > [Tên Địa điểm] > ...
  - Link: Mỗi cấp (trừ mục cuối) là link để quay lại

- **Thư viện Ảnh (Image Gallery)**
  - Layout: Ảnh chính lớn + thumbnails (4-5 ảnh)
  - Kích thước: Chiếm toàn bộ chiều rộng, chiều cao ~50vh
  - Tương tác: Lightbox khi click, slideshow với controls
  - Responsive: Chuyển thành carousel trên mobile

- **Thông Tin Chính (Core Info Block)**
  - Tên: Font lớn (H1), đậm
  - Đánh giá: Star rating + số lượt đánh giá
  - Địa chỉ/Vị trí: Đầy đủ, kèm icon vị trí
  - Tags/Danh mục: Dạng pills/badges màu nhẹ
  - Thông tin phụ: Layout grid hoặc inline với icons
  - Nút hành động: Nổi bật ở góc phải

### Body Section
- Layout: Tabs hoặc Sections cuộn dọc
- Nội dung: Tùy thuộc vào loại màn hình chi tiết

### Review & Comments Section
- Header: Tổng quan về đánh giá (biểu đồ phân bố sao)
- Filter & Sort: Dropdown để lọc (theo số sao) và sắp xếp
- Danh sách bình luận: Card layout với avatar, tên, rating, nội dung
- Form đăng bình luận: Gồm rating stars, text area, upload ảnh (hiện cho người đã đăng nhập)

## Chi Tiết Các Màn Hình

### 1. Destination Detail (/destinations/{slug})

#### Bố Cục Riêng
- **Tabs/Sections**:
  - **Tổng quan**: Mô tả chi tiết về điểm đến, lịch sử, đặc trưng
  - **Địa điểm nổi bật**: Grid Location Cards (3-4 cột) + Nút "Xem tất cả"
  - **Khách sạn/Nơi ở**: Grid Hotel Cards (3-4 cột) + Bộ lọc mini
  - **Sự kiện sắp diễn ra**: List/Grid Event Cards + Calendar view toggle
  - **Đánh giá**: Phần review của người dùng về điểm đến
  - **Bản đồ khu vực**: Bản đồ lớn hiển thị vị trí điểm đến và các điểm đáng chú ý

#### Thiết Kế Đặc Biệt
- Có thể có slideshow ảnh panorama hoặc video ngắn ở đầu trang
- Biểu đồ thời tiết/mùa thích hợp để thăm (nếu là điểm du lịch)
- Gallery ảnh khu vực dạng masonry layout

### 2. Location Detail (/locations/{slug})

#### Bố Cục Riêng
- **Tabs/Sections**:
  - **Tổng quan**: Mô tả chi tiết về địa điểm, đặc điểm
  - **Cửa hàng trong Địa điểm**: Grid Store Cards + Bộ lọc/Search nhỏ
  - **Sự kiện tại đây**: List/Grid Event Cards + Calendar view
  - **Đánh giá**: Phần review của người dùng
  - **Bản đồ chi tiết**: Bản đồ hiển thị vị trí chính xác, lối vào, điểm đỗ xe

#### Thiết Kế Đặc Biệt
- Bảng thông tin giờ mở cửa (nếu là khu vực có giới hạn giờ)
- Hướng dẫn đi đến (phương tiện công cộng, ô tô, xe máy)
- Gallery ảnh 360° (nếu có)

### 3. Store Detail (/stores/{slug})

#### Bố Cục Riêng
- **Tabs/Sections**:
  - **Tổng quan/Giới thiệu**: Mô tả về cửa hàng, thương hiệu
  - **Sản phẩm / Menu**: Grid Product Cards + Bộ lọc/Search nhỏ + Categories
  - **Đánh giá**: Phần review của người dùng
  - **Bản đồ vị trí**: Bản đồ hiển thị vị trí chính xác + Hướng dẫn đi đến

#### Thiết Kế Đặc Biệt
- **Tính năng QR Code** (cho Nhà hàng/Quán ăn):
  - Nút "Xem Menu / Đặt món QR" nổi bật
  - Modal hiển thị QR code lớn, rõ ràng
  - Hướng dẫn quét mã ngắn gọn
- Bảng thông tin chi tiết về giờ mở cửa (có calendar view)
- Thông tin liên hệ và đặt chỗ/đặt hàng (nếu có)

### 4. Product Detail (/products/{slug})

#### Bố Cục Riêng
- **Tabs/Sections**:
  - **Gallery ảnh sản phẩm**: Nhiều góc, các biến thể màu
  - **Tùy chọn (Variants)**: Màu sắc, kích cỡ, các tùy chọn khác
  - **Mô tả chi tiết**: Thông tin đầy đủ về sản phẩm
  - **Thông số kỹ thuật**: Bảng thông số chi tiết (nếu có)
  - **Đánh giá Sản phẩm**: Phần review chi tiết

#### Thiết Kế Đặc Biệt
- Hiển thị trạng thái còn hàng/hết hàng rõ ràng
- Bảng size chart (với sản phẩm thời trang)
- Phần "Sản phẩm liên quan" ở cuối trang

### 5. Hotel/Accommodation Detail (/hotels/{slug})

#### Bố Cục Riêng
- **Tabs/Sections**:
  - **Tổng quan**: Mô tả về khách sạn, lịch sử, đặc điểm
  - **Các loại phòng**: Card layout cho từng loại phòng + Thông tin chi tiết
  - **Kỳ nghỉ đang cho thuê**: Grid Stay Listing Cards + Bộ lọc ngày/giá
  - **Tiện nghi**: Icons list phân nhóm (Chung, Phòng, Dịch vụ...)
  - **Đánh giá**: Phần review của khách hàng
  - **Bản đồ**: Vị trí + Điểm đáng chú ý xung quanh

#### Thiết Kế Đặc Biệt
- Bảng giá theo mùa/thời điểm (nếu có)
- Virtual tour 360° (nếu có)
- Thông tin về check-in/check-out, chính sách

### 6. Stay Listing Detail (/stays/{listing_id})

#### Bố Cục Riêng
- **Tabs/Sections**:
  - **Mô tả chi tiết**: Thông tin từ Host
  - **Thông tin Host**: Card với avatar, tên, ngày tham gia
  - **Nội quy/Điều khoản**: List các quy định
  - **Lịch phòng**: Calendar view hiển thị ngày có sẵn/đã đặt
  - **Thông tin về Khách sạn/Resort gốc**: Summary card + Link

#### Thiết Kế Đặc Biệt
- Highlight thời gian cho thuê cụ thể
- Sticky booking panel (bên phải trên desktop, dưới cùng trên mobile)
- Badges đặc biệt (Ưu đãi, Đặt nhanh, v.v.)

### 7. Event Detail (/events/{slug})

#### Bố Cục Riêng
- **Tabs/Sections**:
  - **Mô tả chi tiết sự kiện**: Nội dung, mục đích, đối tượng tham gia
  - **Lịch trình**: Timeline hiển thị các hoạt động (nếu có)
  - **Thông tin vé/đăng ký**: Các loại vé, giá, form đăng ký
  - **Bản đồ địa điểm**: Vị trí + Chỉ dẫn

#### Thiết Kế Đặc Biệt
- Countdown timer nếu sự kiện sắp diễn ra
- Phần gallery từ các sự kiện tương tự trước đây (nếu có)
- Danh sách các nhà tài trợ/diễn giả/nghệ sĩ (nếu có)

## Responsive Design cho Detail Screens
- **Desktop**:
  - Layout 2 cột cho một số section (Info + Map, Gallery + Core Info)
  - Tabs ngang
  - Sticky elements (Menu tabs, Booking panel)

- **Tablet**:
  - Layout chủ yếu 1 cột
  - Tabs ngang hoặc accordion
  - Gallery chuyển sang carousel

- **Mobile**:
  - Layout 1 cột hoàn toàn
  - Tabs chuyển thành accordion hoặc select dropdown
  - Sticky CTA buttons ở bottom
  - Thumbnail gallery chuyển thành dots indicator