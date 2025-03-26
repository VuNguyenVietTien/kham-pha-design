# Thiết Kế Giao Diện - Khám Phá

Đây là repository chứa các thiết kế giao diện cho dự án "Khám Phá" - một nền tảng giúp người dùng trả lời câu hỏi "Đi đâu? Mua gì? Ở đâu?", cung cấp thông tin phong phú về các điểm đến, địa điểm cụ thể, cửa hàng, sản phẩm, sự kiện, và nơi ở.

## Cấu Trúc Thông Tin

Trang web được tổ chức theo cấu trúc thông tin phân cấp sau:

1. **Điểm đến (Destination)**: Các khu vực địa lý lớn (Vũng Tàu, Đà Lạt, Sa Pa...)
2. **Địa điểm (Location)**: Các khu vực cụ thể trong Điểm đến (Bãi Trước, Chợ Đà Lạt...)
3. **Cửa hàng (Store)**: Cơ sở kinh doanh trong Địa điểm (Quán Cafe, Shop Thời trang...)
4. **Sản phẩm/Dịch vụ (Product)**: Mặt hàng/dịch vụ của Cửa hàng
5. **Khách sạn/Nơi ở (Accommodation)**: Thông tin chỗ ở
6. **Kỳ nghỉ cho thuê (Stay Listing)**: Tin đăng cho thuê lại timeshare/kỳ nghỉ
7. **Sự kiện (Event)**: Hoạt động diễn ra tại Địa điểm/Điểm đến

## Liên Kết Figma

Bạn có thể xem các thiết kế Figma đầy đủ tại:
[Link Figma Design - Khám Phá](https://www.figma.com/file/...)

## Các Màn Hình Chính

1. Trang chủ (Home)
2. Trang kết quả tìm kiếm (Search Results)
3. Chi tiết Điểm đến (Destination Detail)
4. Chi tiết Địa điểm (Location Detail)
5. Chi tiết Cửa hàng (Store Detail)
6. Chi tiết Sản phẩm (Product Detail)
7. Chi tiết Khách sạn (Hotel Detail)
8. Chi tiết Kỳ nghỉ (Stay Listing Detail)
9. Chi tiết Sự kiện (Event Detail)
10. Màn hình Quản lý (Dashboard)
11. Màn hình Đăng nhập/Đăng ký (Authentication)

## Thành Phần Chính

- Navbar và Footer
- Card Components (các loại card khác nhau)
- Tìm kiếm và Bộ lọc
- Breadcrumbs
- Hệ thống đánh giá và bình luận

## Nguyên Tắc Thiết Kế

- Hiện đại, trực quan, sạch sẽ
- Tập trung vào nội dung & hình ảnh
- Phân cấp rõ ràng
- Responsive (hoạt động tốt trên mọi thiết bị)
- Lấy khám phá làm trung tâm