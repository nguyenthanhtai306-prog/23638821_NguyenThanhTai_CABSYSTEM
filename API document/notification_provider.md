# CAB System - Notification Provider API

## 1. Thông tin chung

- **Base URL:** `http://localhost:8080/api`
- **Version:** `1.0.0`
- **Actor / Use Case:** ACT06 – Nhà cung cấp thông báo; UC11
- **Protocol:** HTTP
- **Content-Type:** `application/json` khi có request body
- **Authentication:** Các API có bảo mật sử dụng `Authorization: Bearer <JWT>` theo Swagger Specification.

## 2. API Endpoints

### POST `/notifications`

**Operation ID:** `sendNotification`  
**Use Case / FR:** `UC11 - FR31-FR33`  
**Mô tả:** Gửi thông báo

#### Request Body: `NotificationRequest`

```json
{
  "example": "..."
}
```

> Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

#### Response

| HTTP Status | Meaning |
|---:|---|
| `201` | Thông báo được gửi hoặc lỗi được ghi nhận |

## 3. Data Models

### NotificationRequest
| Field | Type | Required |
|---|---|---|
| `trip_id` | integer (int64) | Yes |
| `customer_id` | integer (int64) | No |
| `driver_id` | integer (int64) | No |
| `notification_type` | string | Yes |
| `notification_status` | string | No |

## 4. Traceability

Các API trong tài liệu này giữ mã Use Case và Functional Requirement theo API Specification của repository.

## 5. Ghi chú

- Không bổ sung business rule hoặc giới hạn dữ liệu ngoài tài liệu nguồn.
- Khi SRS/API Specification chưa quy định giá trị cụ thể, tài liệu này không tự suy diễn.
