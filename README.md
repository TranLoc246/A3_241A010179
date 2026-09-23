# LAB A3: DỰNG GIAO DIỆN LOGIN VÀ THẺ HỒ SƠ

Họ và tên: Trần Nguyễn Thanh Lộc
Mã số sinh viên: 241A010179
Lớp: Lập trình di động - INT4211

 1. GIỚI THIỆU DỰ ÁN
Ứng dụng Android thực hành dựng giao diện Màn hình đăng nhập kết hợp Thẻ hồ sơ sinh viên cho bài Lab A3.
Dự án minh họa cách sử dụng các bộ bố cục LinearLayout, ConstraintLayout, quản lý tài nguyên trong res/ values, cũng như hỗ trợ thay đổi giao diện khi xoay ngang màn hình (layout-land).

---

 2. LỊCH SỬ COMMIT (GIT LOG)
Dự án thực hiện đầy đủ 5 mốc commit theo yêu cầu:
- Commit 1: Khởi tạo dự án
- Commit 2: Khai báo tài nguyên colors, dimens, strings, drawables
- Commit 3: Dựng giao diện LinearLayout activity_main và view_profile_card
- Commit 4: Tạo ConstraintDemoActivity dựng giao diện phẳng với ConstraintLayout
- Commit 5: Thêm giao diện xoay ngang layout-land cho activity_main

 3. BẢNG SO SÁNH PHẦN 5.3 (LINEARLAYOUT VS CONSTRAINTLAYOUT)

1. Số tầng lồng nhau (đếm trong Component Tree):
- Bản LinearLayout: 4 đến 5 tầng (ScrollView -> LinearLayout dọc -> FrameLayout / LinearLayout con -> View/Button).
- Bản ConstraintLayout: 1 đến 2 tầng (ConstraintLayout phẳng, các View con nằm trực tiếp trong ConstraintLayout).

2. Số dòng XML:
- Bản LinearLayout: Dài hơn (khoảng 200 đến 220 dòng do dùng nhiều thẻ mở và đóng LinearLayout con để chia hàng, cột).
- Bản ConstraintLayout: Ngắn gọn hơn (khoảng 120 đến 140 dòng do dùng các thuộc tính ràng buộc layout_constraint).

3. Dễ đọc / dễ sửa hơn?:
- Bản LinearLayout: Dễ đọc với giao diện đơn giản xếp theo hàng dọc/ngang. Tuy nhiên khi giao diện phức tạp thì khó sửa do lồng nhau quá nhiều layer.
- Bản ConstraintLayout: Dễ quản lý và chỉnh sửa vị trí tương quan giữa các View, giao diện phẳng giúp tối ưu hiệu năng render của ứng dụng.

4. Khi màn hình rộng ra thì bố cục thế nào?:
- Bản LinearLayout: Các View bị kéo giãn theo chiều dọc hoặc ngang cố định, dễ thừa khoảng trống dư thừa nếu không tạo layout-land.
- Bản ConstraintLayout: Linh hoạt tự điều chỉnh theo tỷ lệ màn hình nhờ các đường gióng (Guideline) và ràng buộc chuỗi (Chains).

 4. CÂU HỎI ÔN TẬP

1. Khác nhau giữa padding và layout_margin, giữa gravity và layout_gravity:
- Padding là khoảng cách từ viền của View đến nội dung bên trong của chính View đó.
- layout_margin là khoảng cách từ viền của View đến các View khác xung quanh hoặc viền của View cha.
- Gravity quyết định vị trí căn chỉnh của nội dung bên trong View đó.
- layout_gravity quyết định vị trí căn chỉnh của chính View đó so với View cha chứa nó.

2. Khi nào dùng dp, khi nào dùng sp? Vì sao không dùng px?:
- Dùng dp cho các kích thước giao diện như chiều rộng, chiều cao, padding, margin.
- Dùng sp duy nhất cho kích thước văn bản (textSize) để tự động co giãn theo cài đặt hệ thống.
- Không dùng px vì px cố định theo số điểm ảnh thực tế, khiến giao diện bị vỡ hoặc thu nhỏ trên các màn hình có mật độ điểm ảnh (DPI) khác nhau.

3. Muốn hai nút chia đôi chiều ngang trong LinearLayout:
- Đặt layout_width = 0dp cho cả hai nút.
- Đặt layout_weight = 1 cho cả hai nút.

4. Lý do nên thay LinearLayout lồng nhiều tầng bằng ConstraintLayout:
- Giảm độ sâu của cây giao diện giúp tăng tốc độ đo đạc và vẽ màn hình (tối ưu hiệu năng).
- Dễ dàng di chuyển, neo các thành phần giao diện theo vị trí tương quan mà không cần nhóm vào nhiều ViewGroup con.

5. Hệ thống chọn giữa res/layout và res/layout-land:
- Dựa vào hướng màn hình (Orientation) hiện tại của thiết bị (dọc hoặc ngang).
- Khi xoay màn hình, sự kiện Configuration Change xảy ra làm Activity bị hủy và tạo lại để tải bộ giao diện tương ứng với hướng mới.

 5. HƯỚNG DẪN XEM DEMO
- Video demo đính kèm trình diễn các thao tác: Cuộn màn hình, nhập MSSV/Mật khẩu và bấm Đăng nhập, xoay ngang màn hình để tải layout-land, và bấm nút chuyển sang màn hình ConstraintDemoActivity.
