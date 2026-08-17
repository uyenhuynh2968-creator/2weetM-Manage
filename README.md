# 2weet Map — Quản lý 🛠️

Trang quản trị (admin) dành cho **2weet Map** — dùng để duyệt đề xuất tiệm bánh từ khách và quản lý toàn bộ danh sách tiệm hiển thị trên [trang khách](#). Trang này có đăng nhập, không public rộng rãi.

## Tính năng
- Đăng nhập bằng email/mật khẩu (Firebase Authentication)
- Tab **"⏳ Chờ duyệt"** — xem & xử lý các tiệm do khách đề xuất
- Tab **"📋 Tất cả tiệm"** — quản lý toàn bộ tiệm đang có
- Thêm / sửa thông tin tiệm: tên, địa chỉ, giờ mở cửa, liên hệ, website, dòng bánh, chế độ ăn, ảnh (upload hoặc dán link, tối đa 10 ảnh/tiệm)
- Đổi trạng thái tiệm: **Đã duyệt / Chờ duyệt / Từ chối**
- Tự động lấy toạ độ (lat/lng) từ địa chỉ qua OpenStreetMap Nominatim
- `<meta name="robots" content="noindex, nofollow, noarchive">` — chặn công cụ tìm kiếm lập chỉ mục trang này

## Công nghệ
- HTML/CSS/JS thuần (không dùng framework)
- [Firebase Realtime Database](https://firebase.google.com/products/realtime-database) — đọc/ghi chung dữ liệu `stores_data` với trang khách
- [Firebase Authentication](https://firebase.google.com/products/auth) — bảo vệ đăng nhập
- [OpenStreetMap Nominatim](https://nominatim.org/) — geocoding địa chỉ sang toạ độ

## Quan hệ với trang khách
Repo này **chỉ chứa trang quản lý**. Trang khách (nơi người dùng xem/tìm/lưu tiệm bánh) nằm ở repo riêng: **2weet Map** (`2weetworld`).

Cả hai trang dùng **chung 1 `firebaseConfig`** để đọc/ghi cùng một database:
- `stores_data` — danh sách tiệm bánh (trang quản lý ghi, trang khách đọc)
- `favorites_data` — danh sách yêu thích của khách

⚠️ Nếu sửa cấu trúc dữ liệu (`stores_data`) ở đây, nhớ kiểm tra lại trang khách để tránh vỡ tính năng bên đó.

## Chạy thử
Mở trực tiếp file `.html` bằng trình duyệt, hoặc deploy qua static hosting (khuyến khích đặt sau xác thực/giới hạn truy cập, không nên public link công khai).

## Cấu hình Firebase & bảo mật
- Nhớ bật **Email/Password Authentication** trong Firebase Console và tạo sẵn tài khoản admin — trang này không có chức năng tự đăng ký.
- Nếu fork repo, thay `firebaseConfig` bằng project Firebase riêng để tránh ghi đè dữ liệu của người khác.
- Dù có `noindex`, ai có link vẫn vào được màn hình đăng nhập — cân nhắc thêm giới hạn truy cập ở tầng hosting nếu cần bảo mật cao hơn.

## Ghi chú
Dự án cá nhân, đang trong giai đoạn hoàn thiện — có thể còn thay đổi cấu trúc/tính năng.
