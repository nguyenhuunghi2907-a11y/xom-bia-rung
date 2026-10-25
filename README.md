# Xóm Bìa Rừng — Gói chuẩn bị cho admin đăng nhập (Decap)

Trạng thái ngày 2026-10-25: ĐANG CHỜ Nguyễn kết nối GitHub với Muse.
Chưa tạo repo, chưa liên kết Netlify với repo, chưa bật Netlify Identity.

## Khi GitHub đã kết nối, các bước tiếp theo là:
1. Tạo repo GitHub (ví dụ: xom-bia-rung), đẩy toàn bộ web hiện tại + thư mục `admin/` này vào repo.
2. Trong Netlify, liên kết site xom-bia-rung.netlify.app với repo đó (thay cho deploy Drop một lần).
3. Bật Netlify Identity + Git Gateway trong Site configuration.
4. Mời tài khoản quản trị bằng email của bác nông dân (cần email này từ Nguyễn).
5. Bác mở https://xom-bia-rung.netlify.app/admin, đăng nhập bằng email/mật khẩu được mời, đăng/sửa/xoá bài — bài sẽ lưu vào repo và Netlify tự deploy lại công khai.

## Lưu ý kỹ thuật quan trọng (không được bỏ qua khi tích hợp):
- Web hiện tại là 1 file HTML tĩnh duy nhất, nội dung bài viết đang nằm cứng trong HTML.
- Chỉ gắn thêm thư mục `admin/` vào file đó thì Decap vẫn chưa làm bài hiện lên web công khai.
- Khi tích hợp thật, cần tách nội dung bài viết và thông tin liên hệ ra file dữ liệu (ví dụ `content/posts/*.md` và `content/settings.json`) và sửa trang khách để đọc các file đó khi tải trang. Lúc đó bài bác đăng qua /admin mới hiện cho mọi khách xem.
- File `admin/config.yml` trong gói này đã chuẩn bị sẵn theo mô hình đó: collection Bài viết (tiêu đề, ngày, ảnh, nội dung dán sẵn) và Thông tin chung (tên, dòng phụ, SĐT, Zalo, địa chỉ).
- Chi phí: GitHub free + Netlify free, 0 đồng/tháng. Không dùng dịch vụ trả phí nào.
