# CAB System - Payment Provider Test Cases

## TC-PROV-001 - Xử lý thanh toán điện tử thành công

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-PROV-001 |
| Description | Kiểm tra nhà cung cấp thanh toán trả kết quả giao dịch thành công |
| Pre-conditions | Chuyến đã hoàn thành; có yêu cầu thanh toán điện tử |
| Steps | 1. CAB gửi yêu cầu đến provider. 2. Provider xử lý giao dịch. 3. Provider trả kết quả thành công. |
| Test Data | `tripId` hợp lệ; `payment_method = ELECTRONIC` |
| Expected Result | CAB nhận và ghi nhận kết quả giao dịch thành công. |
| Test Result | Not Executed |

## TC-PROV-002 - Provider trả kết quả thất bại

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-PROV-002 |
| Description | Kiểm tra CAB xử lý kết quả thanh toán điện tử thất bại |
| Pre-conditions | Có yêu cầu thanh toán điện tử |
| Steps | 1. Gửi yêu cầu thanh toán. 2. Provider trả kết quả thất bại. |
| Test Data | Payment failure |
| Expected Result | CAB ghi nhận trạng thái thất bại và thông báo cho khách hàng theo luồng thanh toán. |
| Test Result | Not Executed |

## TC-PROV-003 - Không lưu thông tin thanh toán nhạy cảm

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-PROV-003 |
| Description | Kiểm tra CAB không lưu trực tiếp thông tin nhạy cảm |
| Pre-conditions | Có giao dịch thanh toán điện tử |
| Steps | 1. Thực hiện giao dịch. 2. Kiểm tra dữ liệu được lưu tại CAB. |
| Test Data | Giao dịch có dữ liệu thanh toán nhạy cảm |
| Expected Result | CAB không lưu trực tiếp dữ liệu nhạy cảm của thẻ hoặc tài khoản; chỉ lưu dữ liệu giao dịch cần thiết. |
| Test Result | Not Executed |
