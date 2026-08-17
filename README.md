# 2weet Map 🍰

Web app tra cứu & khám phá các tiệm bánh tại TP. Hồ Chí Minh — lọc theo khu vực, hình thức (cửa hàng/online/hybrid), dòng bánh, chế độ ăn, và lưu tiệm yêu thích.

Gồm 2 trang:
- `index.html` — trang khách, dùng để tìm/khám phá tiệm bánh
- `index_html.html` (trang quản lý) — trang admin, có đăng nhập, để duyệt đề xuất và quản lý danh sách tiệm

## Tính năng — Trang khách
- Tìm kiếm & lọc tiệm bánh theo quận, hình thức, dòng bánh, chế độ ăn (vegan, gluten-free, ...)
- Sắp xếp theo khoảng cách từ vị trí hiện tại hoặc khu vực đã chọn
- Lưu tiệm yêu thích, đồng bộ real-time qua Firebase (dùng chung mọi thiết bị/trình duyệt)
- Đề xuất tiệm mới kèm ảnh, chờ duyệt
- Chỉ đường nhanh qua Google Maps / Apple Maps / Grab

## Tính năng — Trang quản lý (Admin)
- Đăng nhập bằng email/mật khẩu (Firebase Authentication)
- Xem & duyệt danh sách tiệm do khách đề xuất (tab "⏳ Chờ duyệt")
- Quản lý toàn bộ tiệm: thêm mới, sửa, đổi trạng thái (Đã duyệt / Chờ duyệt / Từ chối)
- Tự động lấy toạ độ (lat/lng) từ địa chỉ qua OpenStreetMap Nominatim
- `<meta name="robots" content="noindex, nofollow, noarchive">` — không cho công cụ tìm kiếm lập chỉ mục trang admin

## Công nghệ
- HTML/CSS/JS thuần (không dùng framework)
- [Firebase Realtime Database](https://firebase.google.com/products/realtime-database) — đồng bộ dữ liệu tiệm bánh và danh sách yêu thích
- [Firebase Authentication](https://firebase.google.com/products/auth) — bảo vệ
