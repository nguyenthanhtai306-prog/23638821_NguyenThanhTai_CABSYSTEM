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

| Field | Type | Required |
|---|---|---|
| `full_name` | string | Yes |
| `phone` | string | Yes |
| `vehicle_type` | string | Yes |
| `license_plate` | string | Yes |
| `account_status` | string | No |
| `availability_status` | string | No |

#### Response

| HTTP Status | Meaning |
|---:|---|
| `201` | Tạo tài khoản tài xế thành công |
| `400` | Thông tin chưa đầy đủ |

---

### GET `/operations/trips`

**Operation ID:** `getActiveTrips`  
**Use Case / FR:** `UC13 - FR37-FR38`  
**Mô tả:** Theo dõi các chuyến đang diễn ra

#### Response

| HTTP Status | Meaning |
|---:|---|
| `200` | Danh sách chuyến |

**Response Model:** `Trip[]`

---

### GET `/operations/transactions`

**Operation ID:** `getTransactions`  
**Use Case / FR:** `UC13 - FR39`  
**Mô tả:** Tra cứu lịch sử giao dịch

#### Response

| HTTP Status | Meaning |
|---:|---|
| `200` | Danh sách giao dịch |

**Response Model:** `PaymentResult[]`

---

### POST `/operations/trips/{tripId}/support`

**Operation ID:** `supportFailedTrip`  
**Use Case / FR:** `UC13 - FR40`  
**Mô tả:** Hỗ trợ xử lý chuyến bị lỗi

#### Path Parameter

| Parameter | Type | Required |
|---|---|---|
| `tripId` | integer (int64) | Yes |

#### Request Body: `SupportRequest`

| Field | Type | Required |
|---|---|---|
| `action_detail` | string | Yes |

#### Response

| HTTP Status | Meaning |
|---:|---|
| `200` | Đã tiếp nhận xử lý |
| `403` | Không đủ quyền |

---

### GET `/reports/operations`

**Operation ID:** `getOperationsReport`  
**Use Case / FR:** `UC15 - FR43`  
**Mô tả:** Xem báo cáo hoạt động

#### Response

| HTTP Status | Meaning |
|---:|---|
| `200` | Báo cáo hoạt động |
| `403` | Không có quyền xem báo cáo |

**Response Model:** `OperationsReport`

---

### POST `/system/trips/{tripId}/dispatch`

**Operation ID:** `dispatchDriver`  
**Use Case / FR:** `UC05 - FR11-FR13, FR15-FR16`  
**Mô tả:** Tìm và phân công tài xế. API nội bộ của CAB System.

#### Path Parameter

| Parameter | Type | Required |
|---|---|---|
| `tripId` | integer (int64) | Yes |

#### Response

| HTTP Status | Meaning |
|---:|---|
| `200` | Đã gửi yêu cầu đến tài xế phù hợp |
| `404` | Không tìm được tài xế phù hợp |

---

### POST `/system/trips/{tripId}/fare`

**Operation ID:** `calculateFare`  
**Use Case / FR:** `UC09 - FR25`  
**Mô tả:** Tính cước chuyến đi. API nội bộ của CAB System.

#### Path Parameter

| Parameter | Type | Required |
|---|---|---|
| `tripId` | integer (int64) | Yes |

#### Response

| HTTP Status | Meaning |
|---:|---|
| `200` | Số tiền phải trả |
| `409` | Chuyến chưa hoàn thành hoặc công thức cước chưa được phê duyệt |

**Response Model:** `Trip`

## 3. Data Models

### DriverRequest

| Field | Type | Required |
|---|---|---|
| `full_name` | string | Yes |
| `phone` | string | Yes |
| `vehicle_type` | string | Yes |
| `license_plate` | string | Yes |
| `account_status` | string | No |
| `availability_status` | string | No |

### Trip

| Field | Type |
|---|---|
| `trip_id` | integer (int64) |
| `customer_id` | integer (int64) |
| `pickup_address` | string |
| `pickup_latitude` | number (double) |
| `pickup_longitude` | number (double) |
| `destination_address` | string |
| `destination_latitude` | number (double) |
| `destination_longitude` | number (double) |
| `requested_vehicle_type` | string |
| `trip_status` | string |
| `fare_amount` | number (double) |
| `requested_at` | string (date-time) |
| `completed_at` | string (date-time) |
| `cancelled_at` | string (date-time) |

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

- `createDriver` → UC02 - FR08
- `getActiveTrips` → UC13 - FR37-FR38
- `getTransactions` → UC13 - FR39
- `supportFailedTrip` → UC13 - FR40
- `getOperationsReport` → UC15 - FR43
- `dispatchDriver` → UC05 - FR11-FR13, FR15-FR16
- `calculateFare` → UC09 - FR25

## 5. Ghi chú

- Không bổ sung business rule hoặc giới hạn dữ liệu ngoài tài liệu nguồn.
- Các API nội bộ `/system/...` thuộc CAB System theo API Specification.
- Khi SRS/API Specification chưa quy định chi tiết thêm, tài liệu này không tự suy diễn.
