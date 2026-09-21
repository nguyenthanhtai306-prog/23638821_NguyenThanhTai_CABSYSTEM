# CAB System - Notification Provider Test Cases

## TC-NOTI-001 - Gửi thông báo thành công

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-NOTI-001 |
| Description | Kiểm tra CAB gửi được thông báo qua nhà cung cấp |
| Pre-conditions | Có sự kiện cần thông báo |
| Steps | 1. Xác định người nhận. 2. Gửi yêu cầu thông báo. 3. Kiểm tra kết quả. |
| Test Data | `trip_id` hợp lệ; `notification_type` hợp lệ |
| Expected Result | Thông báo được gửi hoặc trạng thái gửi được ghi nhận. |
| Test Result | Not Executed |

## TC-NOTI-002 - Thông báo trạng thái chuyến

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-NOTI-002 |
| Description | Kiểm tra các sự kiện trạng thái chuyến tạo ra thông báo |
| Pre-conditions | Có thay đổi trạng thái chuyến cần thông báo |
| Steps | Kiểm tra thông báo khi yêu cầu được tiếp nhận, tài xế nhận chuyến, tài xế đến điểm đón và chuyến hoàn thành. |
| Test Data | Các sự kiện trạng thái chuyến |
| Expected Result | Thông báo được gửi đến đúng đối tượng theo sự kiện. |
| Test Result | Not Executed |

## TC-NOTI-003 - Lỗi chức năng thông báo

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-NOTI-003 |
| Description | Kiểm tra lỗi thông báo không làm dừng luồng đặt chuyến |
| Pre-conditions | Có sự kiện cần gửi thông báo |
| Steps | 1. Giả lập lỗi nhà cung cấp thông báo. 2. Tiếp tục luồng đặt chuyến. |
| Test Data | Notification provider error |
| Expected Result | Lỗi được ghi nhận nhưng luồng đặt chuyến vẫn tiếp tục. |
| Test Result | Not Executed |
