# Danh sách lớp v0 — Lê Quang Vinh · G09

## DMS (ít nhất 6 lớp)

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng DMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | face | bbox + eye_left, eye_right, glasses, gaze_zone | Theo dõi vùng mặt, hướng nhìn và trạng thái mắt tài xế | Có |
| 2 | face13 | 13 điểm landmark khuôn mặt | Ước lượng tư thế đầu, góc nhìn và trạng thái mở/nhắm mắt | Có |
| 3 | eye_left / eye_right | unknown / open / closed | Phát hiện buồn ngủ, nhắm mắt lâu hoặc mất tập trung | Có, trừ khi bị che hoặc kính phản xạ |
| 4 | hand (whose, side, on_wheel) | driver/passenger, left/right, unknown/yes/no | Kiểm tra tài xế có giữ vô lăng hay thao tác bất thường | Có |
| 5 | phone (state) | held / mounted / lap | Phát hiện tài xế cầm điện thoại khi lái xe | Có |
| 6 | person (seat, seatbelt) | seat + unknown/worn_correct/worn_incorrect/not_worn | Kiểm tra tình trạng thắt dây an toàn của tài xế | Có |

## OMS (ít nhất 6 lớp)

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng OMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | person (seat, seatbelt) | seat + trạng thái dây đai | Đếm số người và xác định vị trí ngồi trong cabin | Có |
| 2 | child_seat (seat, occupied) | seat + unknown/no/yes | Nhận diện ghế trẻ em và trạng thái sử dụng | Có |
| 3 | infant_seat (seat, facing) | seat + rear/front | Nhận diện ghế trẻ sơ sinh và hướng lắp đặt (quay sau/trước) | Có |
| 4 | object (seat, type) | seat + other/bag/box/cup | Nhận diện đồ vật bỏ quên hoặc vật thể trong cabin | Có |
| 5 | frame_meta (modality, light, camera_blocked) | ir/rgb, unknown/day/night, no/yes | Phân loại nguồn ảnh, điều kiện sáng và tình trạng che camera | Có |
| 6 | hand (whose, side, on_wheel) | thông tin tay hành khách | Theo dõi tương tác/chuyển động của người ngồi trong xe | Có |

## 2 câu hỏi leo thang

1. Câu hỏi: Với ảnh SVIRO hàng ghế sau, khi có người ngồi nhưng dây an toàn không hiển thị rõ ràng, nên chọn `not_worn` hay `unknown`?
   Khung ví dụ: `S02_ir.png`, `S04_ir.png`
   Bạn tạm gán thế nào và vì sao: Tạm gán `unknown` hoặc `not_worn` tùy độ rõ của khung hình để tránh suy đoán khi không thấy rõ dây đai.
2. Câu hỏi: Khi một số điểm mắt trên `face13` bị `outside=1` do góc quay nghiêng mạnh, `eye_<side>` nên giữ `unknown` hay gán theo bên còn thấy rõ?
   Khung ví dụ: `D04.png`
   Bạn tạm gán thế nào và vì sao: Tạm gán `unknown` cho phía bị khuất/ngoài khung hình để đồng bộ trạng thái hiển thị với bộ điểm landmark.
