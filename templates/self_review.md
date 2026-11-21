# Tự đánh giá — Lê Quang Vinh · G09

## 1. Tự rà soát 4 cảnh

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| S02_ir.png | child_seat | wrong_class | Thuộc tính occupied cần khớp giá trị hợp lệ theo guideline | Rồi |
| S02_rgb.png | hand | guess | Kiểm tra thuộc tính on_wheel cho tay hành khách hàng ghế sau | Rồi |
| D02.png | person | ok | Đã gán đúng seat=driver và seatbelt=not_worn | Rồi |
| D05.png | phone | ok | Đã gán đúng box điện thoại với state=held | Rồi |

## 2. Lỗi mình lặp lại nhiều nhất hôm nay

Lỗi: Nhầm lẫn giá trị thuộc tính ở một số đối tượng trên cảnh SVIRO.
Vì sao mình mắc: Chuyển đổi nhanh giữa nhiều cảnh và đối chiếu thuộc tính chưa đồng nhất.
Lần sau tránh bằng cách: Rà soát lại toàn bộ thuộc tính của từng nhãn theo schema trước khi xuất file.

## 3. Ghi chú về disagreement_log

Một dòng bạn của mình đúng và mình sai. Mình học được gì từ dòng đó: Khi đối chiếu với Nguyễn Xuân Lam (04051) ở `S02_rgb.png` (`hand.on_wheel`), mình học được cách kiểm tra kỹ ngữ cảnh vị trí ghế ngồi để chọn giá trị thuộc tính chính xác hơn.
