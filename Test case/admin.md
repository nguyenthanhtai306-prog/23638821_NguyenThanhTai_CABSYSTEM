# CAB System - Admin Test Cases

## TC-ADM-001 - Thực hiện thao tác quản trị có quyền

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-ADM-001 |
| Description | Kiểm tra quản trị viên thực hiện thao tác quản trị |
| Pre-conditions | Quản trị viên đã đăng nhập và có quyền |
| Steps | 1. Chọn thao tác quản trị. 2. Cung cấp thông tin cần thiết. 3. Thực hiện thao tác. |
| Test Data | `action_type`, `target_type` hợp lệ |
| Expected Result | Thao tác được thực hiện và được lưu vết. |
| Test Result | Not Executed |

## TC-ADM-002 - Người dùng không đủ quyền

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-ADM-002 |
| Description | Kiểm tra hệ thống từ chối thao tác quản trị không có quyền |
| Pre-conditions | Người dùng không có quyền quản trị |
| Steps | Gửi yêu cầu thao tác quản trị |
| Test Data | Token/tài khoản không có quyền phù hợp |
| Expected Result | Hệ thống từ chối thao tác với trạng thái không đủ quyền. |
| Test Result | Not Executed |

## TC-ADM-003 - Kiểm tra audit log

| Thuộc tính | Nội dung |
|---|---|
| TC_ID | TC-ADM-003 |
| Description | Kiểm tra thao tác quản trị được lưu trong nhật ký |
| Pre-conditions | Đã thực hiện một thao tác quản trị quan trọng |
| Steps | 1. Mở audit log. 2. Kiểm tra bản ghi tương ứng. |
| Test Data | Thao tác quản trị vừa thực hiện |
| Expected Result | Nhật ký chứa thông tin thao tác tương ứng. |
| Test Result | Not Executed |
