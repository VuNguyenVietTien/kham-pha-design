# Hệ Thống Thiết Kế và Các Thành Phần Chung

## Hệ Thống Thiết Kế (Design System)

### Bảng Màu (Color Palette)
- **Màu Chính (Primary)**
  - Primary-500: #2D72D9 (Xanh dương - Màu chủ đạo)
  - Primary-400: #4F8DEE (Xanh dương nhạt hơn)
  - Primary-600: #1A5DC0 (Xanh dương đậm hơn)
  
- **Màu Thứ Cấp (Secondary)**
  - Secondary-500: #FF8C38 (Cam)
  - Secondary-400: #FFA75F (Cam nhạt hơn)
  - Secondary-600: #E67020 (Cam đậm hơn)

- **Màu Trung Tính (Neutral)**
  - Neutral-100: #FFFFFF (Trắng)
  - Neutral-200: #F5F5F7 (Xám rất nhạt)
  - Neutral-300: #E5E5EA (Xám nhạt)
  - Neutral-400: #D1D1D6 (Xám)
  - Neutral-500: #A9A9B2 (Xám vừa)
  - Neutral-600: #636366 (Xám đậm)
  - Neutral-700: #3A3A3C (Xám rất đậm)
  - Neutral-800: #1A1A1A (Đen vừa)
  - Neutral-900: #000000 (Đen)

- **Màu Ngữ Nghĩa (Semantic)**
  - Success-500: #34C759 (Xanh lá - Thành công)
  - Warning-500: #FFCC00 (Vàng - Cảnh báo)
  - Error-500: #FF3B30 (Đỏ - Lỗi)
  - Info-500: #5AC8FA (Xanh nhạt - Thông tin)

- **Light Theme**
  - Background: Neutral-100/200
  - Text Primary: Neutral-800
  - Text Secondary: Neutral-600
  
- **Dark Theme**
  - Background: Neutral-800
  - Text Primary: Neutral-100
  - Text Secondary: Neutral-300

### Typography
- **Font Family**
  - Primary: 'Inter', sans-serif
  - Secondary (optional): 'Playfair Display', serif (cho headings đặc biệt)

- **Font Sizes**
  - Heading 1: 32px (2rem), Font Weight: 700
  - Heading 2: 24px (1.5rem), Font Weight: 700
  - Heading 3: 20px (1.25rem), Font Weight: 600
  - Heading 4: 18px (1.125rem), Font Weight: 600
  - Heading 5: 16px (1rem), Font Weight: 600
  - Body: 16px (1rem), Font Weight: 400
  - Small: 14px (0.875rem), Font Weight: 400
  - XSmall: 12px (0.75rem), Font Weight: 400

- **Line Heights**
  - Headings: 1.2 - 1.3
  - Body text: 1.5 - 1.6

### Spacing System
- **Base Unit**: 8px
- **Scale**:
  - Space-1: 4px (0.25rem) - Extra tight
  - Space-2: 8px (0.5rem) - Tight
  - Space-3: 16px (1rem) - Base
  - Space-4: 24px (1.5rem) - Loose
  - Space-5: 32px (2rem) - Extra loose
  - Space-6: 48px (3rem) - Ultra loose
  - Space-7: 64px (4rem) - Massive

### Borders & Rounded Corners
- **Border Widths**
  - Border-1: 1px
  - Border-2: 2px
  
- **Border Radius**
  - Radius-1: 4px - Nhỏ
  - Radius-2: 8px - Vừa
  - Radius-3: 16px - Lớn
  - Radius-4: 24px - Extra lớn
  - Radius-full: 9999px - Pill/Full rounded

### Shadows
- **Elevation-1**: 0px 1px 2px rgba(0, 0, 0, 0.05) - Subtle
- **Elevation-2**: 0px 2px 4px rgba(0, 0, 0, 0.1) - Light
- **Elevation-3**: 0px 4px 8px rgba(0, 0, 0, 0.12) - Medium
- **Elevation-4**: 0px 8px 16px rgba(0, 0, 0, 0.15) - Heavy
- **Elevation-5**: 0px 16px 24px rgba(0, 0, 0, 0.2) - Intense

## Các Thành Phần Chung (Common Components)

### 1. Navbar (Thanh điều hướng trên cùng)
![Navbar Component](../assets/components/navbar.png)

- **Kích thước**:
  - Chiều cao: 64px
  - Chiều rộng: 100% width
  - Padding: horizontal 24px

- **Thành phần**:
  - Logo (left-aligned): SVG, chiều cao 32px
  - Thanh tìm kiếm (center-aligned): Chiều rộng 40-50%
  - Nút chuyển đổi sáng/tối (right-aligned): Icon 20px
  - User area (right-most): Avatar 32px hoặc hai nút "Đăng nhập", "Đăng ký"

- **Variants**:
  - Default: Nền trắng, shadow nhẹ
  - Transparent: Không nền, dùng trên hero sections
  - Dark: Nền đen/tối, cho dark mode

### 2. Card Components
![Card Components](../assets/components/cards.png)

#### a. Destination Card
- **Kích thước**: Width 100%, aspect ratio 1:1.3
- **Layout**:
  - Ảnh: Tỷ lệ 16:9, top position
  - Nội dung: Padding 16px
  - Tên: Heading 3, weight bold
  - Tags: Pills, font size small, margin-top 8px
  - Đánh giá: Bottom position, star icon + số

#### b. Location Card
- **Kích thước**: Width 100%, aspect ratio 1:1.3
- **Layout**:
  - Ảnh: Tỷ lệ 16:9, top position
  - Nội dung: Padding 16px
  - Tên: Heading 4, weight bold
  - Địa chỉ: Font size small, color neutral-600
  - Tags: Pills dạng nhỏ, inline

#### c. Store Card
- **Kích thước**: Width 100%, aspect ratio 1:1.3
- **Layout**:
  - Ảnh: Tỷ lệ 16:9 hoặc 1:1, top position
  - Logo (optional): Tròn, position absolute, bottom của ảnh
  - Nội dung: Padding 16px
  - Tên: Heading 4, weight bold
  - Loại hình: Font size small, color primary
  - Địa chỉ & Rating: Bottom row, space-between

#### d. Product Card
- **Kích thước**: Width 100%, aspect ratio 1:1.5
- **Layout**:
  - Ảnh: Tỷ lệ 1:1, top position
  - Nội dung: Padding 16px
  - Tên: Heading 5, weight medium
  - Tên Cửa hàng: Font size small, color neutral-600
  - Giá: Semi-bold, color primary-600
  - Đánh giá: Bottom position, star icon + số

#### e. Hotel Card
- **Kích thước**: Width 100%, aspect ratio 1:1.3
- **Layout**:
  - Ảnh: Tỷ lệ 16:9, top position
  - Badge (nếu có): Position absolute, top-right
  - Nội dung: Padding 16px
  - Tên: Heading 4, weight bold
  - Địa chỉ: Font size small, color neutral-600
  - Hạng sao: Icon sao vàng (1-5)
  - Giá: Bottom-right, semi-bold

#### f. Stay Listing Card
- **Kích thước**: Width 100%, aspect ratio 1:1.3
- **Layout**:
  - Ảnh: Tỷ lệ 16:9, top position
  - Badge (thời gian): Position absolute, top-left
  - Nội dung: Padding 16px
  - Tên Resort: Heading 5, weight medium
  - Thông tin unit: Font size small, color neutral-600
  - Giá thuê: Semi-bold, color primary-600
  - Tên Host: Bottom row, with small avatar

#### g. Event Card
- **Kích thước**: Width 100%, aspect ratio 1:1.4
- **Layout**:
  - Ảnh/Poster: Tỷ lệ 16:9, top position
  - Badge (ngày): Position absolute, top-left
  - Nội dung: Padding 16px
  - Tên Sự kiện: Heading 4, weight bold
  - Ngày/Giờ: Font size small, with icon
  - Địa điểm: Font size small, with icon
  - Giá vé (nếu có): Bottom-right, semi-bold

### 3. Thanh Tìm kiếm & Modal
![Search Components](../assets/components/search.png)

- **Thanh Tìm kiếm (Navbar)**:
  - Height: 40px
  - Border-radius: Radius-full (pill)
  - Border: 1px solid neutral-300
  - Icon search: Left, 16px
  - Placeholder: "Tìm kiếm Điểm đến, Địa điểm, Cửa hàng, Sản phẩm..."
  - Focus state: Shadow glow light primary

- **Modal Tìm kiếm**:
  - Width: 600px (desktop) / 100% (mobile)
  - Border-radius: Radius-3
  - Input field: Tự động focus, giống thanh tìm kiếm nhưng lớn hơn
  - Gợi ý (dropdown): Max-height với scroll
  - Mỗi item gợi ý: Icon phân loại + Text + Action hover
  - Tìm kiếm gần đây: Pills có thể click/remove
  - Xu hướng tìm kiếm: Pills highlight màu nhẹ

### 4. Breadcrumbs
- **Layout**:
  - Height: 24px
  - Margin: Vertical 16px
  - Separator: Icon chevron-right, color neutral-400
  
- **Typography**:
  - Font size: Small
  - Current item: Regular, color neutral-600
  - Links: Regular, color primary-500
  - Hover: Underline

### 5. Buttons
![Button Components](../assets/components/buttons.png)

- **Size Variants**:
  - Small: Height 32px, Padding horizontal 12px
  - Medium: Height 40px, Padding horizontal 16px
  - Large: Height 48px, Padding horizontal 24px

- **Style Variants**:
  - Primary: Background primary-500, Text white
  - Secondary: Background white, Border primary-500, Text primary-500
  - Tertiary: No background/border, Text primary-500
  - Danger: Background error-500, Text white
  - Success: Background success-500, Text white
  - Ghost: Background transparent, hover slight background

- **Icon Buttons**:
  - Circle: Diameter 40px
  - Square: 40x40px
  - Rounded: Border-radius Radius-1
  - Icon size: 20px

### 6. Form Elements
![Form Components](../assets/components/forms.png)

- **Text Input**:
  - Height: 40px (standard), 48px (large)
  - Border-radius: Radius-2
  - Border: 1px solid neutral-300
  - Padding: Horizontal 16px
  - States: Default, Focus, Error, Disabled
  - With icon: Left or right positioned

- **Dropdown/Select**:
  - Same base style as text input
  - Chevron-down icon right
  - Options dropdown: Border-radius Radius-2, shadow Elevation-3

- **Checkbox & Radio**:
  - Size: 20x20px
  - Border-radius: 4px (checkbox), 50% (radio)
  - Checked state: Background primary-500, icon check white

- **Range Slider**:
  - Track height: 4px
  - Thumb: Circle, diameter 20px, primary-500
  - Range highlight: Background primary-400

### 7. Tabs & Pagination
- **Tabs**:
  - Height: 48px
  - Border-bottom: 1px solid neutral-300
  - Active tab: Border-bottom 2px primary-500
  - Hover: Text darker/border visible
  - Padding: Horizontal 16px
  - Spacing between: 8px

- **Pagination**:
  - Height: 40px
  - Number buttons: 40x40px, border-radius Radius-1
  - Current page: Background primary-500, text white
  - Prev/Next: With chevron icons
  - Hover: Background neutral-200

### 8. Alerts & Notices
- **Alert Types**:
  - Success: Green background, check icon
  - Warning: Yellow background, alert icon
  - Error: Red background, x-circle icon
  - Info: Blue background, info icon

- **Layout**:
  - Padding: 16px
  - Border-radius: Radius-2
  - Icon: Left, 20px
  - Close button: Right, x icon
  - Actions: Bottom if needed
  
- **Toast notifications**:
  - Position: Top-right floating
  - Animation: Slide in + fade
  - Auto-dismiss: With progress bar

### 9. Loading States
- **Spinner**:
  - Circular, primary color
  - Sizes: Small (16px), Medium (24px), Large (40px)

- **Skeleton Loading**:
  - For cards: Placeholder shapes
  - Animation: Pulse effect
  - Color: neutral-200 to neutral-300 gradient

- **Progress Bar**:
  - Height: 4px
  - Background: neutral-200
  - Fill: primary-500, animation left to right

### 10. Responsive Breakpoints
- **Extra small (mobile)**: < 576px
- **Small (mobile large)**: 576px - 767px
- **Medium (tablet)**: 768px - 991px
- **Large (desktop)**: 992px - 1199px
- **Extra large (large desktop)**: ≥ 1200px