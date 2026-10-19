


# Bài 8: Chữa lỗi bảng đăng ký báo cáo viên không lọc được

## Phần 1: Phân tích lỗi

1. Các lỗi trong bảng

-   Dòng tiêu đề: Tên bảng nằm chung vùng dữ liệu → vi phạm quy tắc 1. AutoFilter có thể nhận sai hàng tiêu đề.
    
-   Ô B3: “Trần Thị Bình” có khoảng trắng thừa → dữ liệu không thống nhất, gây khó khăn khi tìm kiếm chính xác.
    
-   Các dòng trống: Có dòng trống giữa dữ liệu → vi phạm quy tắc 4, khiến bộ lọc có thể chỉ nhận một phần bảng.
    
-   Dòng “TỔNG SỐ CNTT: 45”: Nằm giữa dữ liệu → vi phạm quy tắc 5, làm sai phạm vi lọc.
    
-   Các cột: Cần bảo đảm mỗi cột chỉ chứa một loại thông tin, mỗi hàng tương ứng một báo cáo viên.
    

2. Vì sao khoảng trắng làm sai kết quả lọc?

Filter so sánh chuỗi ký tự. “Trần Thị Bình” và “Trần Thị Bình ” có khoảng trắng cuối khác nhau nên có thể không khớp khi lọc chính xác.

## Phần 2: Sửa lỗi và nghiệm thu

3. Cấu trúc bảng đúng chuẩn

-   Hàng đầu tiên là tiêu đề cột: STT, Họ và Tên, Khoa / Viện, Điểm Xét Duyệt, Trạng Thái.
    
-   Mỗi hàng chứa thông tin của một báo cáo viên.
    
-   Xóa các hàng trống nằm giữa dữ liệu.
    
-   Chuyển dòng “TỔNG SỐ CNTT: 45” ra ngoài vùng dữ liệu.
    

4. Làm sạch dữ liệu và lọc

-   Nhập công thức `=TRIM(B2)` vào cột phụ để loại bỏ khoảng trắng thừa trong họ tên, sau đó kéo công thức xuống các dòng còn lại.
    
-   Bật bộ lọc bằng Ctrl + Shift + L.
    
-   Lọc cột Khoa / Viện chọn `CNTT`.
    
-   Lọc cột Điểm Xét Duyệt chọn điều kiện lớn hơn hoặc bằng 8.0.
