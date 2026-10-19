# PHẦN 1: PHÂN TÍCH LỖI
**1. Tại sao định dạng thủ công làm Auto TOC trắng trơn?**

Cơ chế của Auto TOC: Word **không nhìn vào chữ to, in đậm, tô vàng**. Nó chỉ quét trong hệ thống Style, những đoạn nào được gắn nhãn `Heading 1, Heading 2, Heading 3` thì mới được đưa vào mục lục.

File đang bị lỗi:

-   `1. Thông tin chung` - Chỉ bôi đen cho to 16 + tô vàng -> Về bản chất Word vẫn hiểu đây là `Normal`. 
-   `1.1, 1.2` - `Normal + in đậm cỡ 14` -> Cũng là Normal.
-   `3. Lịch trình` - `Normal` 100% -> Chắc chắn mất.

Kết quả: Khi bấm `References > Table of Contents`, Word đi quét cả file, không thấy thẻ Heading nào cả -> Trả về 1 dòng trống.

**2. Tại sao nhầm H2 sang H3 làm mục lục sai thụt lề?**

TOC có 3 cấp thụt lề tương ứng:

-   Heading 1 = Cấp 1 - Ra sát lề trái, không thụt
-   Heading 2 = Cấp 2 - Thụt vào 1 nấc
-   Heading 3 = Cấp 3 - Thụt vào 2 nấc

Dòng `2.1.1. Tiểu ban Kỹ thuật` đáng lẽ phải là con của `2.1. Ban Nội dung` (nghĩa là phải là Heading 3). Nếu gán nhầm nó thành Heading 2, trong TOC nó sẽ nhảy lên ngang hàng với `2.1`, nhìn vào sẽ hiểu sai là 2 ban song song, mất logic Chương > Mục > Chi tiết. Ngược lại, nếu gán Heading 2 thành Heading 3 thì nó sẽ bị thụt sâu vào trong, tưởng là mục con dù thực ra là mục lớn.


# PHẦN 2: SỬA LỖI & NGHIỆM THU

**3. Các bước sửa đúng cho 7 dòng:**

Bạn làm theo đúng thứ tự này, đừng sửa màu sắc:

-   **Bước 1:** Bôi đen dòng `1. Thông tin chung hội nghị` > Bấm `Ctrl + Alt + 1` để gán Heading 1. Sau đó mới tô màu, chỉnh cỡ nếu muốn.
-   **Bước 2:** Bôi đen `1.1. Tên hội nghị` > Bấm `Ctrl + Alt + 2` (Heading 2)
-   **Bước 3:** Bôi đen `1.2. Thời gian & địa điểm` > Bấm `Ctrl + Alt + 2` (Heading 2)
-   **Bước 4:** Bôi đen `2. Cơ cấu ban tổ chức` > Bấm `Ctrl + Alt + 1` (Heading 1)
-   **Bước 5:** Bôi đen `2.1. Ban Nội dung` > Bấm `Ctrl + Alt + 2` (Heading 2)
-   **Bước 6:** Bôi đen `2.1.1. Tiểu ban Kỹ thuật` > Bấm `Ctrl + Alt + 3` (Heading 3) - Đây chính là chỗ bị nhầm, phải là H3 mới đúng.
-   **Bước 7:** Bôi đen `3. Lịch trình sự kiện` > Bấm `Ctrl + Alt + 1` (Heading 1)

Sau khi sửa xong, vào `References > Table of Contents > Automatic Table 2`,  sẽ thấy đủ 3 cấp thụt lề đẹp: Và thu về kết quả 
1. Thông tin chung hội nghị....1
  1.1. Tên hội nghị.............1
  1.2. Thời gian & địa điểm.....2
2. Cơ cấu ban tổ chức...........2
  2.1. Ban Nội dung.............2
    2.1.1. Tiểu ban Kỹ thuật....3
3. Lịch trình sự kiện...........4


**4. Bẫy dữ liệu - Mục 3 bị đẩy sang trang 4:**

Nếu không làm gì thêm, mục lục sẽ **VẪN HIỆN SAI** là trang 2, vì TOC không tự động cập nhật số trang.

Bạn phải cập nhật lại:

-   Chuột phải vào giữa bảng Mục lục > Chọn `Update Field`
-   Chọn `Update entire table` (Cập nhật toàn bộ bảng) > OK
-   Phím tắt nhanh: Bôi đen toàn bộ mục lục rồi bấm `F9`.
