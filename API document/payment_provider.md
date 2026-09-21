# CAB System - Payment Provider API

## 1. Thông tin chung

- **Base URL:** `http://localhost:8080/api`
- **Version:** `1.0.0`
- **Actor / Use Case:** ACT05 – Nhà cung cấp thanh toán; UC10
- **Protocol:** HTTP
- **Content-Type:** `application/json` khi có request body
- **Authentication:** Các API có bảo mật sử dụng `Authorization: Bearer <JWT>` theo Swagger Specification.

## 2. API Endpoints

### POST `/payments/trips/{tripId}`

**Operation ID:** `processElectronicPayment`  
**Use Case / FR:** `UC10 - FR27-FR30`  
**Mô tả:** Xử lý thanh toán điện tử và trả kết quả

#### Path Parameter

| Parameter | Type | Required |
|---|---|---|
| `tripId` | integer (int64) | Yes |

#### Request Body: `PaymentRequest`

```json
{
  "example": "..."
}
```

> Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

#### Response

| HTTP Status | Meaning |
|---:|---|
| `200` | Kết quả giao dịch |
| `400` | Giao dịch không hợp lệ |

## 3. Data Models

### PaymentRequest
| Field | Type | Required |
|---|---|---|
| `payment_method` | string | Yes |

Allowed values: `CASH`, `ELECTRONIC`.

### PaymentResult
| Field | Type |
|---|---|
| `payment_id` | integer (int64) |
| `trip_id` | integer (int64) |
| `payment_method` | string |
| `amount` | number (double) |
| `payment_status` | string |
| `provider_reference` | string |
| `retry_count` | integer |
| `paid_at` | string (date-time) |

## 4. Traceability

Các API trong tài liệu này giữ mã Use Case và Functional Requirement theo API Specification của repository.

## 5. Ghi chú

- Không bổ sung business rule hoặc giới hạn dữ liệu ngoài tài liệu nguồn.
- Khi SRS/API Specification chưa quy định giá trị cụ thể, tài liệu này không tự suy diễn.
