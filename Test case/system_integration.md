# CAB System - System Integration Test Cases

## TC-NET-001 - Mất kết nối tạm thời

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-NET-001 |
| Description | Kiểm tra hệ thống giữ trạng thái cuối cùng khi mất kết nối |
| Pre-conditions | Chuyến đang diễn ra và đã có trạng thái được ghi nhận |
| Steps | 1. Ngắt kết nối tạm thời. 2. Thực hiện cập nhật trong thời gian mất kết nối. 3. Khôi phục kết nối. |
| Test Data | Mất kết nối tạm thời |
| Expected Result | Hệ thống giữ trạng thái cuối cùng đã ghi nhận và đồng bộ các cập nhật khi kết nối được khôi phục. |
| Test Result | Not Executed |

## TC-SEC-001 - Không lưu dữ liệu thanh toán nhạy cảm

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-SEC-001 |
| Description | Kiểm tra CAB không lưu trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán |
| Pre-conditions | Có giao dịch thanh toán điện tử |
| Steps | 1. Thực hiện thanh toán. 2. Kiểm tra dữ liệu lưu tại CAB. |
| Test Data | Giao dịch điện tử |
| Expected Result | CAB chỉ lưu dữ liệu giao dịch cần thiết và không lưu trực tiếp thông tin nhạy cảm. |
| Test Result | Not Executed |

## TC-SCOPE-001 - Kiểm tra phạm vi MBB

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-SCOPE-001 |
| Description | Kiểm tra các nội dung ngoài phạm vi MBB không được đưa vào tiêu chí nghiệm thu |
| Pre-conditions | Đã xác định phạm vi MBB |
| Steps | Rà soát chức năng, tài liệu và tiêu chí nghiệm thu |
| Test Data | Giá động, khuyến mại, tích điểm, ghép chuyến, nhiều điểm dừng, đặt chuyến theo lịch, thuật toán điều phối nâng cao |
| Expected Result | Các nội dung trên không thuộc phạm vi nghiệm thu MBB. |
| Test Result | Not Executed |
