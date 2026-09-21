# CAB System - Customer Test Cases

## TC-CUS-001 - Đăng ký tài khoản khách hàng thành công

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-CUS-001 |
| Description | Kiểm tra khách hàng có thể đăng ký tài khoản |
| Pre-conditions | Khách hàng chưa đăng ký tài khoản |
| Steps | 1. Chọn chức năng đăng ký. 2. Nhập thông tin khách hàng hợp lệ. 3. Gửi yêu cầu đăng ký. |
| Test Data | `full_name` hợp lệ; `phone` hợp lệ; `email` hợp lệ hoặc bỏ trống |
| Expected Result | Tài khoản khách hàng được tạo thành công. |
| Test Result | Not Executed |

## TC-CUS-002 - Đăng ký với thông tin không hợp lệ

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-CUS-002 |
| Description | Kiểm tra hệ thống xử lý thông tin đăng ký không hợp lệ |
| Pre-conditions | Người dùng đang ở chức năng đăng ký |
| Steps | 1. Nhập thiếu hoặc sai thông tin bắt buộc. 2. Gửi yêu cầu đăng ký. |
| Test Data | Thiếu `full_name` hoặc `phone` |
| Expected Result | Hệ thống thông báo thông tin không hợp lệ và không tạo tài khoản. |
| Test Result | Not Executed |

## TC-CUS-003 - Đăng nhập khách hàng thành công

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-CUS-003 |
| Description | Kiểm tra khách hàng đăng nhập thành công |
| Pre-conditions | Tài khoản khách hàng hợp lệ đã tồn tại |
| Steps | 1. Chọn đăng nhập. 2. Nhập thông tin xác thực hợp lệ. 3. Gửi yêu cầu. |
| Test Data | `phone` hợp lệ; thông tin xác thực hợp lệ theo hệ thống |
| Expected Result | Hệ thống xác thực thành công và cho phép sử dụng chức năng yêu cầu tài khoản. |
| Test Result | Not Executed |

## TC-CUS-004 - Đăng nhập thất bại

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-CUS-004 |
| Description | Kiểm tra đăng nhập khi xác thực không thành công |
| Pre-conditions | Có tài khoản khách hàng |
| Steps | 1. Nhập thông tin xác thực không hợp lệ. 2. Gửi yêu cầu đăng nhập. |
| Test Data | Thông tin xác thực không hợp lệ |
| Expected Result | Hệ thống thông báo xác thực không thành công và không cho truy cập chức năng yêu cầu tài khoản. |
| Test Result | Not Executed |

## TC-CUS-005 - Cập nhật thông tin khách hàng

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-CUS-005 |
| Description | Kiểm tra khách hàng có thể cập nhật thông tin cá nhân |
| Pre-conditions | Khách hàng đã đăng nhập |
| Steps | 1. Mở thông tin tài khoản. 2. Thay đổi thông tin cá nhân. 3. Gửi yêu cầu cập nhật. |
| Test Data | `full_name`, `phone`, `email` hợp lệ |
| Expected Result | Thông tin khách hàng được cập nhật thành công. |
| Test Result | Not Executed |

## TC-TRIP-001 - Tạo yêu cầu đặt chuyến thành công

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-TRIP-001 |
| Description | Kiểm tra khách hàng tạo yêu cầu đặt chuyến hợp lệ |
| Pre-conditions | Khách hàng đã đăng nhập |
| Steps | 1. Chọn đặt chuyến. 2. Nhập điểm đón. 3. Nhập điểm đến. 4. Chọn loại xe. 5. Gửi yêu cầu. |
| Test Data | Điểm đón, điểm đến và loại xe hợp lệ |
| Expected Result | Yêu cầu được tạo thành công và chuyển sang trạng thái đang tìm tài xế. |
| Test Result | Not Executed |

## TC-TRIP-002 - Đặt chuyến thiếu thông tin bắt buộc

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-TRIP-002 |
| Description | Kiểm tra hệ thống không tạo chuyến khi thiếu thông tin |
| Pre-conditions | Khách hàng đã đăng nhập |
| Steps | 1. Mở chức năng đặt chuyến. 2. Bỏ trống một thông tin bắt buộc. 3. Gửi yêu cầu. |
| Test Data | Thiếu điểm đón hoặc điểm đến hoặc loại xe |
| Expected Result | Hệ thống yêu cầu bổ sung/chỉnh sửa và không tạo chuyến. |
| Test Result | Not Executed |

## TC-STATUS-CUS-001 - Xem trạng thái chuyến

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-STATUS-CUS-001 |
| Description | Kiểm tra khách hàng xem được trạng thái chuyến |
| Pre-conditions | Khách hàng đã đăng nhập; chuyến tồn tại |
| Steps | 1. Mở thông tin chuyến. 2. Kiểm tra trạng thái hiện tại. |
| Test Data | `trip_id` hợp lệ |
| Expected Result | Hệ thống hiển thị thông tin chuyến và trạng thái hiện tại. |
| Test Result | Not Executed |

## TC-PAY-CUS-001 - Thanh toán tiền mặt

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-PAY-CUS-001 |
| Description | Kiểm tra ghi nhận thanh toán tiền mặt |
| Pre-conditions | Chuyến đã hoàn thành và có số tiền phải trả |
| Steps | 1. Chọn phương thức tiền mặt. 2. Gửi yêu cầu ghi nhận thanh toán. |
| Test Data | `payment_method = CASH` |
| Expected Result | Hệ thống ghi nhận giao dịch thanh toán tiền mặt. |
| Test Result | Not Executed |

## TC-PAY-CUS-002 - Thanh toán điện tử thành công

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-PAY-CUS-002 |
| Description | Kiểm tra thanh toán điện tử thành công |
| Pre-conditions | Chuyến đã hoàn thành và nhà cung cấp thanh toán hoạt động |
| Steps | 1. Chọn thanh toán điện tử. 2. Hệ thống gửi yêu cầu đến nhà cung cấp thanh toán. 3. Nhận kết quả thành công. |
| Test Data | `payment_method = ELECTRONIC` |
| Expected Result | Kết quả giao dịch thành công được lưu và thông báo cho khách hàng. |
| Test Result | Not Executed |

## TC-PAY-CUS-003 - Thanh toán điện tử thất bại

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-PAY-CUS-003 |
| Description | Kiểm tra xử lý thanh toán điện tử thất bại |
| Pre-conditions | Chuyến đã hoàn thành |
| Steps | 1. Chọn thanh toán điện tử. 2. Giả lập giao dịch thất bại. |
| Test Data | Kết quả giao dịch thất bại |
| Expected Result | Hệ thống thông báo thất bại, lưu trạng thái giao dịch thất bại và xử lý lại theo chính sách được xác nhận. |
| Test Result | Not Executed |

## TC-PAY-CUS-004 - Thử thanh toán lại

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-PAY-CUS-004 |
| Description | Kiểm tra khả năng xử lý lại giao dịch thanh toán điện tử |
| Pre-conditions | Giao dịch điện tử trước đó thất bại |
| Steps | 1. Thực hiện lại thanh toán điện tử. 2. Nhận kết quả giao dịch. |
| Test Data | Giao dịch retry |
| Expected Result | Hệ thống ghi nhận kết quả giao dịch mới theo luồng thanh toán. |
| Test Result | Not Executed |

## TC-HIS-001 - Xem lịch sử chuyến

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-HIS-001 |
| Description | Kiểm tra khách hàng xem lịch sử chuyến |
| Pre-conditions | Khách hàng đã đăng nhập và có lịch sử chuyến |
| Steps | 1. Mở chức năng lịch sử chuyến. |
| Test Data | Tài khoản có chuyến đã lưu |
| Expected Result | Hệ thống hiển thị lịch sử chuyến và số tiền phải trả. |
| Test Result | Not Executed |

## TC-RAT-001 - Đánh giá sau khi chuyến hoàn thành

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-RAT-001 |
| Description | Kiểm tra khách hàng đánh giá tài xế sau chuyến |
| Pre-conditions | Chuyến đã hoàn thành |
| Steps | 1. Mở chức năng đánh giá. 2. Nhập điểm đánh giá. 3. Gửi đánh giá. |
| Test Data | `score`: từ 1 đến 5; `comment` tùy chọn |
| Expected Result | Đánh giá hợp lệ được lưu vào lịch sử chuyến. |
| Test Result | Not Executed |

## TC-RAT-002 - Đánh giá trước khi chuyến hoàn thành

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-RAT-002 |
| Description | Kiểm tra hệ thống không cho đánh giá chuyến chưa hoàn thành |
| Pre-conditions | Chuyến chưa hoàn thành |
| Steps | Gửi yêu cầu đánh giá |
| Test Data | `score`: giá trị từ 1 đến 5 |
| Expected Result | Hệ thống từ chối ghi nhận đánh giá. |
| Test Result | Not Executed |

## TC-RAT-003 - Đánh giá lần thứ hai cho cùng chuyến

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-RAT-003 |
| Description | Kiểm tra không cho ghi nhận nhiều đánh giá cho một chuyến |
| Pre-conditions | Chuyến đã có một đánh giá hợp lệ |
| Steps | Gửi thêm một đánh giá cho cùng chuyến |
| Test Data | Đánh giá thứ hai |
| Expected Result | Hệ thống không ghi nhận đánh giá thứ hai. |
| Test Result | Not Executed |

## TC-EX-011 - Khách hàng hủy khi đang tìm tài xế

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-EX-011 |
| Description | Kiểm tra khách hàng hủy khi hệ thống đang tìm tài xế |
| Pre-conditions | Chuyến đang ở trạng thái tìm tài xế |
| Steps | Khách hàng gửi yêu cầu hủy |
| Test Data | Yêu cầu hủy chuyến |
| Expected Result | Hệ thống dừng tìm tài xế, cập nhật chuyến thành đã hủy và thông báo kết quả cho khách hàng. |
| Test Result | Not Executed |

## TC-EX-012 - Hủy sau khi tài xế nhận chuyến

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-EX-012 |
| Description | Kiểm tra xử lý hủy sau khi tài xế đã nhận |
| Pre-conditions | Chuyến đã được gán tài xế |
| Steps | Khách hàng yêu cầu hủy |
| Test Data | Yêu cầu hủy chuyến |
| Expected Result | Hệ thống ghi nhận yêu cầu và chuyển trường hợp cho nhân viên vận hành xử lý; không tự quyết định phí hủy. |
| Test Result | Not Executed |
