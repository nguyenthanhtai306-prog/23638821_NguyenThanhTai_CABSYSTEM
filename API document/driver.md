CAB System - Driver API

1. Thông tin chung

Base URL: http://localhost:8080/api

Version: 1.0.0

Actor / Use Case: ACT02 – Tài xế; UC02, UC03, UC06, UC07, UC08

Protocol: HTTP

Content-Type: application/json khi có request body

Authentication: Các API có bảo mật sử dụng Authorization: Bearer <JWT> theo Swagger Specification.

2. API Endpoints

PUT /drivers/{driverId}

Operation ID: updateDriver
Use Case / FR: UC02 - FR08-FR09
Mô tả: Cập nhật hồ sơ và phương tiện tài xế

Path Parameter

Parameter

Type

Required

driverId

integer (int64)

Yes

Request Body: DriverRequest

{
  "example": "..."
}

Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

Response

HTTP Status

Meaning

200

Cập nhật thành công

400

Thông tin chưa đầy đủ

PUT /drivers/{driverId}/availability

Operation ID: updateDriverAvailability
Use Case / FR: UC03 - FR10
Mô tả: Cập nhật trạng thái sẵn sàng

Path Parameter

Parameter

Type

Required

driverId

integer (int64)

Yes

Request Body: AvailabilityRequest

{
  "example": "..."
}

Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

Response

HTTP Status

Meaning

200

Cập nhật trạng thái thành công

400

Tài khoản không hợp lệ

POST /trips/{tripId}/response

Operation ID: respondToTrip
Use Case / FR: UC06 - FR14-FR17
Mô tả: Chấp nhận hoặc từ chối chuyến

Path Parameter

Parameter

Type

Required

tripId

integer (int64)

Yes

Request Body: DriverResponseRequest

{
  "example": "..."
}

Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

Response

HTTP Status

Meaning

200

Đã ghi nhận phản hồi

409

Chuyến đã được gán cho tài xế khác

PUT /trips/{tripId}/status

Operation ID: updateTripStatus
Use Case / FR: UC07 - FR20-FR23
Mô tả: Cập nhật trạng thái chuyến

Path Parameter

Parameter

Type

Required

tripId

integer (int64)

Yes

Request Body: TripStatusRequest

{
  "example": "..."
}

Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

Response

HTTP Status

Meaning

200

Trạng thái được cập nhật

400

Sai trình tự trạng thái

POST /drivers/{driverId}/locations

Operation ID: updateDriverLocation
Use Case / FR: UC08 - FR19
Mô tả: Cập nhật vị trí tài xế

Path Parameter

Parameter

Type

Required

driverId

integer (int64)

Yes

Request Body: LocationRequest

{
  "example": "..."
}

Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

Response

HTTP Status

Meaning

201

Vị trí được lưu

400

Dữ liệu vị trí không hợp lệ

3. Data Models

DriverRequest

Field

Type

Required

full_name

string

Yes

phone

string

Yes

vehicle_type

string

Yes

license_plate

string

Yes

account_status

string

No

availability_status

string

No

AvailabilityRequest

Field

Type

Required

availability_status

string

Yes

Allowed values: AVAILABLE, UNAVAILABLE.

DriverResponseRequest

Field

Type

Required

driver_id

integer (int64)

Yes

response_status

string

Yes

Allowed values: ACCEPTED, REJECTED.

TripStatusRequest

Field

Type

Required

trip_status

string

Yes

Allowed values: RECEIVED, SEARCHING_DRIVER, DRIVER_ASSIGNED, DRIVER_ARRIVED, PASSENGER_PICKED_UP, IN_PROGRESS, COMPLETED.

LocationRequest

Field

Type

Required

latitude

number (double)

Yes

longitude

number (double)

Yes

recorded_at

string (date-time)

No

4. Traceability

Các API trong tài liệu này giữ mã Use Case và Functional Requirement theo API Specification của repository.

5. Ghi chú

Không bổ sung business rule hoặc giới hạn dữ liệu ngoài tài liệu nguồn.

Khi SRS/API Specification chưa quy định giá trị cụ thể, tài liệu này không tự suy diễn.
