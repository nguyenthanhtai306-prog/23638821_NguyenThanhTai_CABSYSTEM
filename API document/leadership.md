# CAB System - Leadership API

## 1. Thông tin chung

- **Base URL:** `http://localhost:8080/api`
- **Version:** `1.0.0`
- **Actor / Use Case:** ACT07 – Ban lãnh đạo; UC15
- **Protocol:** HTTP
- **Content-Type:** `application/json` khi có request body
- **Authentication:** Các API có bảo mật sử dụng `Authorization: Bearer <JWT>` theo Swagger Specification.

## 2. API Endpoints

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
