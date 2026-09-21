# CAB System - Admin API

## 1. Thông tin chung

- **Base URL:** `http://localhost:8080/api`
- **Version:** `1.0.0`
- **Actor / Use Case:** ACT04 – Quản trị viên; UC14
- **Protocol:** HTTP
- **Content-Type:** `application/json` khi có request body
- **Authentication:** Các API có bảo mật sử dụng `Authorization: Bearer <JWT>` theo Swagger Specification.

## 2. API Endpoints

### POST `/admin/actions`

**Operation ID:** `adminAction`  
**Use Case / FR:** `UC14 - FR41-FR42`  
**Mô tả:** Thực hiện thao tác quản trị

#### Request Body: `AdminActionRequest`

```json
{
  "example": "..."
}
```

> Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

#### Response

| HTTP Status | Meaning |
|---:|---|
| `200` | Thao tác được thực hiện và lưu vết |
| `403` | Không đủ quyền |

### GET `/admin/audit-logs`

**Operation ID:** `getAuditLogs`  
**Use Case / FR:** `UC14 - FR42`  
**Mô tả:** Kiểm tra nhật ký thao tác

#### Response

| HTTP Status | Meaning |
|---:|---|
| `200` | Danh sách nhật ký |
| `403` | Không đủ quyền |

## 3. Data Models

### AdminActionRequest
| Field | Type | Required |
|---|---|---|
| `action_type` | string | Yes |
| `target_type` | string | Yes |
| `target_id` | integer (int64) | No |
| `action_detail` | string | No |

### AuditLog
| Field | Type |
|---|---|
| `audit_id` | integer (int64) |
| `operator_id` | integer (int64) |
| `action_type` | string |
| `target_type` | string |
| `target_id` | integer (int64) |
| `action_detail` | string |
| `created_at` | string (date-time) |

## 4. Traceability

Các API trong tài liệu này giữ mã Use Case và Functional Requirement theo API Specification của repository.

## 5. Ghi chú

- Không bổ sung business rule hoặc giới hạn dữ liệu ngoài tài liệu nguồn.
- Khi SRS/API Specification chưa quy định giá trị cụ thể, tài liệu này không tự suy diễn.
