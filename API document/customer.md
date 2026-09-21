CAB System - Customer API

1. Thông tin chung

Base URL: http://localhost:8080/api

Version: 1.0.0

Actor / Use Case: ACT01 – Khách hàng; UC01, UC04, UC07, UC10, UC12

Protocol: HTTP

Content-Type: application/json khi có request body

Authentication: Các API có bảo mật sử dụng Authorization: Bearer <JWT> theo Swagger Specification.

2. API Endpoints

POST /customers/register

Operation ID: registerCustomer
Use Case / FR: UC01 - FR01
Mô tả: Đăng ký tài khoản khách hàng

Request Body: CustomerRegisterRequest

{
  "example": "..."
}

Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

Response

HTTP Status

Meaning

201

Tài khoản được tạo

400

Thông tin không hợp lệ

POST /customers/login

Operation ID: loginCustomer
Use Case / FR: UC01 - FR02
Mô tả: Đăng nhập khách hàng

Request Body: LoginRequest

{
  "example": "..."
}

Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

Response

HTTP Status

Meaning

200

Đăng nhập thành công

401

Xác thực không thành công

PUT /customers/{customerId}

Operation ID: updateCustomer
Use Case / FR: UC01 - FR03
Mô tả: Cập nhật thông tin khách hàng

Path Parameter

Parameter

Type

Required

customerId

integer (int64)

Yes

Request Body: CustomerUpdateRequest

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

Thông tin không hợp lệ

POST /trips

Operation ID: createTrip
Use Case / FR: UC04 - FR04-FR07
Mô tả: Tạo yêu cầu đặt chuyến

Request Body: TripRequest

{
  "example": "..."
}

Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

Response

HTTP Status

Meaning

201

Yêu cầu được tiếp nhận

400

Thiếu hoặc sai thông tin

GET /trips/{tripId}

Operation ID: getTrip
Use Case / FR: UC07 - FR18-FR24
Mô tả: Xem thông tin và trạng thái chuyến

Path Parameter

Parameter

Type

Required

tripId

integer (int64)

Yes

Response

HTTP Status

Meaning

200

Thông tin chuyến

POST /trips/{tripId}/payments

Operation ID: payTrip
Use Case / FR: UC10 - FR26-FR30
Mô tả: Thanh toán chuyến đi

Path Parameter

Parameter

Type

Required

tripId

integer (int64)

Yes

Request Body: PaymentRequest

{
  "example": "..."
}

Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

Response

HTTP Status

Meaning

200

Kết quả thanh toán

400

Thanh toán thất bại

GET /customers/{customerId}/trips

Operation ID: getCustomerTripHistory
Use Case / FR: UC12 - FR34-FR35
Mô tả: Xem lịch sử chuyến

Path Parameter

Parameter

Type

Required

customerId

integer (int64)

Yes

Response

HTTP Status

Meaning

200

Danh sách lịch sử chuyến

POST /trips/{tripId}/ratings

Operation ID: rateDriver
Use Case / FR: UC12 - FR36
Mô tả: Đánh giá tài xế

Path Parameter

Parameter

Type

Required

tripId

integer (int64)

Yes

Request Body: RatingRequest

{
  "example": "..."
}

Payload fields are defined in the schema section below. Values shown above are placeholders, not business requirements.

Response

HTTP Status

Meaning

201

Đánh giá được lưu

400

Chuyến chưa hoàn thành hoặc đã có đánh giá

3. Data Models

CustomerRegisterRequest

Field

Type

Required

full_name

string

Yes

phone

string

Yes

email

string (email)

No

LoginRequest

Field

Type

Required

phone

string

Yes

password

string

No

CustomerUpdateRequest

Field

Type

Required

full_name

string

No

phone

string

No

email

string (email)

No

TripRequest

Field

Type

Required

customer_id

integer (int64)

Yes

pickup_address

string

Yes

pickup_latitude

number (double)

No

pickup_longitude

number (double)

No

destination_address

string

Yes

destination_latitude

number (double)

No

destination_longitude

number (double)

No

requested_vehicle_type

string

Yes

Trip

Field

Type

trip_id

integer (int64)

customer_id

integer (int64)

pickup_address

string

pickup_latitude

number (double)

pickup_longitude

number (double)

destination_address

string

destination_latitude

number (double)

destination_longitude

number (double)

requested_vehicle_type

string

trip_status

string

fare_amount

number (double)

requested_at

string (date-time)

completed_at

string (date-time)

cancelled_at

string (date-time)

PaymentRequest

Field

Type

Required

payment_method

string

Yes

Allowed values: CASH, ELECTRONIC.

PaymentResult

Field

Type

payment_id

integer (int64)

trip_id

integer (int64)

payment_method

string

amount

number (double)

payment_status

string

provider_reference

string

retry_count

integer

paid_at

string (date-time)

RatingRequest

Field

Type

Required

customer_id

integer (int64)

Yes

driver_id

integer (int64)

Yes

score

integer

Yes

comment

string

No

score: minimum 1, maximum 5.

4. Traceability

Các API trong tài liệu này giữ mã Use Case và Functional Requirement theo API Specification của repository.

5. Ghi chú

Không bổ sung business rule hoặc giới hạn dữ liệu ngoài tài liệu nguồn.

Khi SRS/API Specification chưa quy định giá trị cụ thể, tài liệu này không tự suy diễn.
