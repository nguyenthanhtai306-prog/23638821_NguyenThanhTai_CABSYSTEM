# CAB System - Operator API

## 1. Thông tin chung

- **Base URL:** `http://localhost:8080/api`
- **Version:** `1.0.0`
- **Actor / Use Case:** ACT03 – Nhân viên vận hành; UC02, UC13, UC15
- **Protocol:** HTTP
- **Content-Type:** `application/json` khi có request body
- **Authentication:** Các API có bảo mật sử dụng `Authorization: Bearer <JWT>` theo Swagger Specification.

## 2. API Endpoints

### POST `/drivers`

**Operation ID:** `createDriver`  
**Use Case / FR:** `UC02 - FR08`  
**Mô tả:** Tạo tài khoản tài xế

#### Request Body: `DriverRequest`

```json
{
  "example": "..."
}
```

> Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

#### Response

| HTTP Status | Meaning |
|---:|---|
| `201` | Tạo tài khoản tài xế thành công |
| `400` | Thông tin chưa đầy đủ |

### GET `/operations/trips`

**Operation ID:** `getActiveTrips`  
**Use Case / FR:** `UC13 - FR37-FR38`  
**Mô tả:** Theo dõi các chuyến đang diễn ra

#### Response

| HTTP Status | Meaning |
|---:|---|
| `200` | Danh sách chuyến |

### GET `/operations/transactions`

**Operation ID:** `getTransactions`  
**Use Case / FR:** `UC13 - FR39`  
**Mô tả:** Tra cứu lịch sử giao dịch

#### Response

| HTTP Status | Meaning |
|---:|---|
| `200` | Danh sách giao dịch |

### POST `/operations/trips/{tripId}/support`

**Operation ID:** `supportFailedTrip`  
**Use Case / FR:** `UC13 - FR40`  
**Mô tả:** Hỗ trợ xử lý chuyến bị lỗi

#### Path Parameter

| Parameter | Type | Required |
|---|---|---|
| `tripId` | integer (int64) | Yes |

#### Request Body: `SupportRequest`

```json
{
  "example": "..."
}
```

> Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

#### Response

| HTTP Status | Meaning |
|---:|---|
| `200` | Đã tiếp nhận xử lý |
| `403` | Không đủ quyền |

### GET `/reports/operations`

**Operation ID:** `getOperationsReport`  
**Use Case / FR:** `UC15 - FR43`  
**Mô tả:** Xem báo cáo hoạt động

#### Response

| HTTP Status | Meaning |
|---:|---|
| `200` | Báo cáo hoạt động |
| `403` | Không có quyền xem báo cáo |

## 3. Data Models

### DriverRequest
Dùng cùng cấu trúc `DriverRequest` của Driver API.

### Trip
Dùng cùng cấu trúc `Trip` của Customer API.

### PaymentResult
Dùng cùng cấu trúc `PaymentResult` của Customer API.

### SupportRequest
| Field | Type | Required |
|---|---|---|
| `action_detail` | string | Yes |

### OperationsReport
| Field | Type |
|---|---|
| `trip_count` | integer |
| `revenue` | number (double) |
| `completion_rate` | number (double) |
| `cancellation_rate` | number (double) |
| `driver_effectiveness` | number (double) |

## 4. Traceability

Các API trong tài liệu này giữ mã Use Case và Functional Requirement theo API Specification của repository.

## 5. Ghi chú

- Không bổ sung business rule hoặc giới hạn dữ liệu ngoài tài liệu nguồn.
- Khi SRS/API Specification chưa quy định giá trị cụ thể, tài liệu này không tự suy diễn.
