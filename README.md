# Bài 7 - Automated PR Review

`mvn verify` chạy unit test và Google Checkstyle. Khi PR vào `main`, job `review` dùng `dbelyaev/action-checkstyle@v3` để nhận xét trực tiếp dòng lỗi. `fail_level: error` làm job thất bại khi phát hiện vi phạm trên dòng mới.

**Thao tác bắt buộc trên GitHub:** trong repository, vào Settings → Branches / Rulesets, tạo rule áp dụng `main`, yêu cầu PR trước merge và require status checks `build`, `review` (tên check có thể khác theo GitHub hiển thị). Tạo nhánh, cố ý đặt tên biến sai chuẩn trên dòng mới, mở PR từ **cùng repository** vào `main`; lấy ảnh review comment và nút Merge bị khóa. Sửa lỗi, push lại, chụp trạng thái xanh. Cấu hình branch protection là thiết lập phía GitHub, không thể thay bằng file YAML.
