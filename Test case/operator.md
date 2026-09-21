# CAB System - Operator Test Cases

## TC-OPS-001 - Xem các chuyến đang diễn ra

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-OPS-001 |
| Description | Kiểm tra nhân viên vận hành xem được các chuyến đang diễn ra |
| Pre-conditions | Nhân viên vận hành đã đăng nhập và có quyền |
| Steps | Mở chức năng theo dõi chuyến |
| Test Data | Có các chuyến đang diễn ra |
| Expected Result | Hệ thống hiển thị danh sách các chuyến đang diễn ra. |
| Test Result | Not Executed |

## TC-OPS-002 - Tra cứu lịch sử giao dịch

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-OPS-002 |
| Description | Kiểm tra nhân viên vận hành tra cứu giao dịch |
| Pre-conditions | Nhân viên vận hành có quyền |
| Steps | Mở chức năng giao dịch |
| Test Data | Có các giao dịch đã lưu |
| Expected Result | Hệ thống hiển thị danh sách giao dịch. |
| Test Result | Not Executed |

## TC-OPS-003 - Hỗ trợ chuyến bị lỗi

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-OPS-003 |
| Description | Kiểm tra nhân viên vận hành hỗ trợ xử lý chuyến bị lỗi |
| Pre-conditions | Có chuyến gặp sự cố; nhân viên có quyền |
| Steps | 1. Mở thông tin chuyến lỗi. 2. Nhập nội dung hỗ trợ. 3. Gửi yêu cầu. |
| Test Data | `action_detail`: nội dung xử lý |
| Expected Result | Trường hợp lỗi được tiếp nhận để xử lý. |
| Test Result | Not Executed |

## TC-OPS-004 - Không đủ quyền hỗ trợ

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-OPS-004 |
| Description | Kiểm tra hệ thống từ chối thao tác vận hành không có quyền |
| Pre-conditions | Người dùng không có quyền phù hợp |
| Steps | Gửi yêu cầu hỗ trợ chuyến |
| Test Data | Token/tài khoản không có quyền |
| Expected Result | Hệ thống từ chối thao tác với trạng thái không đủ quyền. |
| Test Result | Not Executed |

## TC-DIS-001 - Tìm tài xế phù hợp

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-DIS-001 |
| Description | Kiểm tra hệ thống tìm và phân công tài xế |
| Pre-conditions | Có yêu cầu chuyến hợp lệ và có tài xế phù hợp |
| Steps | Gửi yêu cầu tìm tài xế |
| Test Data | Tài xế có trạng thái sẵn sàng và vị trí phù hợp |
| Expected Result | Hệ thống xác định tài xế phù hợp và gửi yêu cầu chuyến đến tài xế. |
| Test Result | Not Executed |

## TC-DIS-002 - Không tìm được tài xế

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-DIS-002 |
| Description | Kiểm tra xử lý khi không có tài xế phù hợp |
| Pre-conditions | Có yêu cầu chuyến nhưng không có tài xế phù hợp |
| Steps | Thực hiện tìm tài xế |
| Test Data | Không có tài xế đáp ứng tiêu chí |
| Expected Result | Hệ thống thông báo cho khách hàng và kết thúc yêu cầu theo trạng thái tương ứng. |
| Test Result | Not Executed |

## TC-FARE-001 - Tính cước sau khi chuyến hoàn thành

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-FARE-001 |
| Description | Kiểm tra hệ thống xác định và lưu số tiền phải trả |
| Pre-conditions | Chuyến đã hoàn thành và công thức cước đã được phê duyệt |
| Steps | Gửi yêu cầu tính cước |
| Test Data | Thông tin chuyến hoàn thành |
| Expected Result | Số tiền khách hàng phải trả được xác định và lưu cho chuyến. |
| Test Result | Not Executed |

## TC-FARE-002 - Tính cước khi chuyến chưa hoàn thành

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-FARE-002 |
| Description | Kiểm tra không tính cước khi chuyến chưa hoàn thành |
| Pre-conditions | Chuyến chưa ở trạng thái hoàn thành |
| Steps | Gửi yêu cầu tính cước |
| Test Data | Chuyến ở trạng thái chưa hoàn thành |
| Expected Result | Hệ thống không xác định số tiền cuối cùng và xử lý theo trạng thái lỗi được quy định. |
| Test Result | Not Executed |

## TC-FARE-003 - Công thức cước chưa được phê duyệt

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-FARE-003 |
| Description | Kiểm tra xử lý khi công thức cước chưa được xác nhận |
| Pre-conditions | Chuyến hoàn thành nhưng chính sách cước chưa được phê duyệt |
| Steps | Gửi yêu cầu tính cước |
| Test Data | Công thức cước chưa được phê duyệt |
| Expected Result | Hệ thống không tự suy diễn công thức và xử lý theo quy định tương ứng. |
| Test Result | Not Executed |

## TC-RPT-001 - Xem báo cáo hoạt động

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-RPT-001 |
| Description | Kiểm tra người dùng có quyền xem báo cáo |
| Pre-conditions | Người dùng đã xác thực và có quyền |
| Steps | Mở chức năng báo cáo hoạt động |
| Test Data | Dữ liệu hoạt động đã được ghi nhận |
| Expected Result | Hệ thống trả về báo cáo hoạt động. |
| Test Result | Not Executed |

## TC-RPT-002 - Kiểm tra các chỉ tiêu báo cáo

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-RPT-002 |
| Description | Kiểm tra báo cáo có các chỉ tiêu được yêu cầu |
| Pre-conditions | Báo cáo hoạt động có dữ liệu |
| Steps | Mở báo cáo và kiểm tra các trường dữ liệu |
| Test Data | Dữ liệu báo cáo |
| Expected Result | Báo cáo có số chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả tài xế. |
| Test Result | Not Executed |

## TC-RPT-003 - Không có quyền xem báo cáo

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-RPT-003 |
| Description | Kiểm tra người dùng không có quyền truy cập báo cáo |
| Pre-conditions | Người dùng không có quyền xem báo cáo |
| Steps | Gửi yêu cầu xem báo cáo |
| Test Data | Tài khoản không có quyền |
| Expected Result | Hệ thống từ chối truy cập. |
| Test Result | Not Executed |

## TC-EX-007 - Chuyến đang diễn ra gặp lỗi

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-EX-007 |
| Description | Kiểm tra nhân viên vận hành xử lý chuyến bị lỗi |
| Pre-conditions | Chuyến đang diễn ra |
| Steps | 1. Phát sinh lỗi. 2. Nhân viên vận hành kiểm tra chuyến. 3. Thực hiện hỗ trợ. |
| Test Data | Thông tin lỗi của chuyến |
| Expected Result | Nhân viên vận hành có thể tiếp nhận và hỗ trợ xử lý trường hợp lỗi. |
| Test Result | Not Executed |
