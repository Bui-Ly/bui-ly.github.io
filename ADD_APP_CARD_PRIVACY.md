# Thêm app mới: card ở Home và Privacy Policy

Áp dụng khi tôi yêu cầu thêm một app/game vào website này theo mẫu gọn. Phạm vi mặc định chỉ gồm **một card ở trang Home** và **privacy policy riêng của app**. Giữ nguyên các app khác.

## Thông tin cần xác định

- Tên app chính xác, loại app, mô tả ngắn và icon. Dùng slug URL ổn định, chữ thường và dấu gạch ngang.
- Nền tảng và link cửa hàng **đã xác nhận**. Nếu chưa có link, card hiển thị `Google Play coming soon` hoặc `App Store coming soon` theo nền tảng; không tạo link giả.
- Đọc cấu hình và mã nguồn app để xác định tài khoản, dữ liệu lưu trên máy, quảng cáo/SDK, mua hàng, hỗ trợ và các bên thứ ba. Nội dung policy phải phản ánh app này, không sao chép nguyên khai báo của app khác.

## Các file cần làm

1. `assets/apps/<slug>.<ext>`: thêm icon có sẵn của app; không lấy icon của app khác.
2. `index.html`: thêm đúng **một** `app-card` giống card hiện có, cập nhật `app-count`. Trong `store-links` chỉ có một nút/link cửa hàng đã xác nhận; nếu chưa có link, dùng một `span.store-status` với chữ `Google Play coming soon` hoặc `App Store coming soon`. **Không thêm nút Game information hay Privacy policy lên card Home.** Dùng kiểu `store-status` đang có trong `home.css`.
3. `apps/<slug>/privacy/index.html`: tạo policy riêng theo bố cục của policy gần nhất phù hợp. Đổi toàn bộ tên, URL, metadata, email subject, icon và ngày hiệu lực. Kiểm tra từng tuyên bố về dữ liệu, quảng cáo, mua hàng, lưu trữ, quyền lựa chọn và liên hệ dựa trên app thực tế.
4. `privacy/index.html`: thêm một card dẫn đến `/apps/<slug>/privacy/`.
5. `sitemap.xml`: thêm URL `/apps/<slug>/privacy/`.

Chỉ thêm `apps/<slug>/privacy.html` nếu cần URL chuyển hướng tương thích. Không tạo trang support `/apps/<slug>/`, trang xóa tài khoản, hay sửa project app chỉ vì thêm card và privacy; chỉ làm các phần đó khi tôi yêu cầu riêng.

## Kiểm tra và đăng

- Soát `git status` trước khi sửa, giữ nguyên thay đổi không liên quan.
- Kiểm tra tên app, slug, icon, link nội bộ, mailto, URL canonical và sitemap; tìm lại tên/URL của app được dùng làm mẫu để tránh sót.
- Chạy `git diff --check`. Nếu được yêu cầu đẩy lên, chỉ commit file thuộc phạm vi này, push `main`, chờ GitHub Pages build xong rồi kiểm tra Home và policy public trả HTTP 200 với nội dung mới.
- Khi tôi gửi link cửa hàng sau này, chỉ thay nhãn `coming soon` bằng **một** link cửa hàng trên card Home và kiểm tra lại trang public.
