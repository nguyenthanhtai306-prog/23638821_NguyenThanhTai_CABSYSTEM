# CAB System - Driver Test Cases

## TC-DRV-001 - Tạo tài khoản tài xế

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-DRV-001 |
| Description | Kiểm tra tài xế có thể được tạo tài khoản và lưu thông tin |
| Pre-conditions | Nhân viên vận hành có quyền tạo tài khoản |
| Steps | 1. Tạo tài khoản tài xế. 2. Nhập hồ sơ và thông tin phương tiện. 3. Gửi yêu cầu. |
| Test Data | `full_name`, `phone`, `vehicle_type`, `license_plate` hợp lệ |
| Expected Result | Tài khoản, hồ sơ và thông tin phương tiện được lưu thành công. |
| Test Result | Not Executed |

## TC-DRV-002 - Cập nhật hồ sơ và phương tiện

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-DRV-002 |
| Description | Kiểm tra tài xế cập nhật hồ sơ và phương tiện |
| Pre-conditions | Tài xế có tài khoản hợp lệ |
| Steps | 1. Mở thông tin tài xế. 2. Cập nhật thông tin. 3. Lưu thay đổi. |
| Test Data | Hồ sơ và phương tiện hợp lệ |
| Expected Result | Thông tin mới được lưu thành công. |
| Test Result | Not Executed |

## TC-DRV-003 - Tài khoản không hoạt động không được nhận chuyến

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-DRV-003 |
| Description | Kiểm tra hệ thống không xem xét tài khoản tài xế không hoạt động |
| Pre-conditions | Tài khoản tài xế ở trạng thái không hoạt động |
| Steps | 1. Tạo một yêu cầu đặt chuyến phù hợp. 2. Thực hiện tìm tài xế. |
| Test Data | `account_status` không hoạt động |
| Expected Result | Tài xế không được xem xét để nhận chuyến. |
| Test Result | Not Executed |

## TC-AVL-001 - Tài xế cập nhật trạng thái sẵn sàng

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-AVL-001 |
| Description | Kiểm tra tài xế cập nhật trạng thái sẵn sàng nhận chuyến |
| Pre-conditions | Tài xế đã đăng nhập |
| Steps | 1. Mở chức năng trạng thái. 2. Chọn sẵn sàng. 3. Lưu trạng thái. |
| Test Data | `availability_status = AVAILABLE` |
| Expected Result | Trạng thái sẵn sàng được cập nhật thành công. |
| Test Result | Not Executed |

## TC-AVL-002 - Tài xế chuyển sang không sẵn sàng

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-AVL-002 |
| Description | Kiểm tra tài xế chuyển sang không sẵn sàng |
| Pre-conditions | Tài xế có tài khoản hợp lệ |
| Steps | 1. Mở chức năng trạng thái. 2. Chọn không sẵn sàng. 3. Lưu. |
| Test Data | `availability_status = UNAVAILABLE` |
| Expected Result | Trạng thái được cập nhật thành công và tài xế không được xem xét khi tìm tài xế. |
| Test Result | Not Executed |

## TC-RES-001 - Tài xế chấp nhận chuyến

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-RES-001 |
| Description | Kiểm tra tài xế có thể chấp nhận yêu cầu chuyến |
| Pre-conditions | Tài xế nhận được yêu cầu chuyến |
| Steps | 1. Tài xế xem yêu cầu. 2. Chọn chấp nhận. 3. Gửi phản hồi. |
| Test Data | `response_status = ACCEPTED` |
| Expected Result | Hệ thống ghi nhận phản hồi và gán chuyến cho tài xế hợp lệ. |
| Test Result | Not Executed |

## TC-RES-002 - Tài xế từ chối chuyến

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-RES-002 |
| Description | Kiểm tra hệ thống tìm tài xế khác khi tài xế từ chối |
| Pre-conditions | Tài xế nhận được yêu cầu |
| Steps | 1. Tài xế chọn từ chối. 2. Gửi phản hồi. |
| Test Data | `response_status = REJECTED` |
| Expected Result | Hệ thống ghi nhận từ chối và tiếp tục tìm tài xế khác. |
| Test Result | Not Executed |

## TC-RES-003 - Tài xế không phản hồi

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-RES-003 |
| Description | Kiểm tra xử lý khi tài xế không phản hồi |
| Pre-conditions | Yêu cầu chuyến đã được gửi đến tài xế |
| Steps | Không gửi phản hồi từ tài xế và chờ thời gian xử lý theo thiết kế MBB. |
| Test Data | Không có phản hồi |
| Expected Result | Hệ thống ghi nhận không phản hồi và tiếp tục tìm tài xế khác. |
| Test Result | Not Executed |

## TC-RES-004 - Nhiều tài xế cùng chấp nhận

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-RES-004 |
| Description | Kiểm tra khi nhiều tài xế cùng phản hồi chấp nhận |
| Pre-conditions | Cùng một chuyến được gửi đến nhiều tài xế |
| Steps | 1. Tài xế A chấp nhận. 2. Tài xế B chấp nhận sau đó. |
| Test Data | Hai phản hồi `ACCEPTED` cho cùng một chuyến |
| Expected Result | Tài xế có phản hồi hợp lệ đầu tiên được gán; phản hồi sau không thay đổi tài xế đã chọn. |
| Test Result | Not Executed |

## TC-STATUS-001 - Cập nhật trạng thái chuyến đúng thứ tự

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-STATUS-001 |
| Description | Kiểm tra trạng thái chuyến được cập nhật đúng thứ tự |
| Pre-conditions | Chuyến đã được gán tài xế |
| Steps | 1. Cập nhật đã đến điểm đón. 2. Cập nhật đã đón khách. 3. Cập nhật đang di chuyển. 4. Cập nhật hoàn thành. |
| Test Data | Các trạng thái hợp lệ theo SRS |
| Expected Result | Hệ thống lưu và hiển thị đúng thứ tự trạng thái chuyến. |
| Test Result | Not Executed |

## TC-STATUS-002 - Cập nhật trạng thái sai trình tự

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-STATUS-002 |
| Description | Kiểm tra hệ thống từ chối trạng thái không hợp lệ |
| Pre-conditions | Chuyến đang ở một trạng thái xác định |
| Steps | Gửi trạng thái không đúng trình tự |
| Test Data | Trạng thái không hợp lệ so với trạng thái hiện tại |
| Expected Result | Hệ thống từ chối cập nhật trạng thái không hợp lệ và ghi nhận sự kiện theo quy định. |
| Test Result | Not Executed |

## TC-LOC-001 - Lưu vị trí tài xế

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-LOC-001 |
| Description | Kiểm tra hệ thống lưu vị trí và thời điểm cập nhật |
| Pre-conditions | Tài xế có tài khoản hợp lệ và đang hoạt động |
| Steps | 1. Gửi thông tin vị trí. 2. Hệ thống tiếp nhận và lưu. |
| Test Data | `latitude`, `longitude`, `recorded_at` hợp lệ |
| Expected Result | Vị trí và thời điểm ghi nhận được lưu thành công. |
| Test Result | Not Executed |

## TC-LOC-002 - Không có vị trí mới

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-LOC-002 |
| Description | Kiểm tra xử lý khi không nhận được vị trí mới |
| Pre-conditions | Tài xế đã có vị trí gần nhất được lưu |
| Steps | 1. Không gửi vị trí mới. 2. Theo dõi thông tin chuyến. |
| Test Data | Không có cập nhật vị trí mới |
| Expected Result | Hệ thống sử dụng vị trí cuối cùng và không tự xác nhận tài xế đã đến hoặc chuyến đã hoàn thành. |
| Test Result | Not Executed |
