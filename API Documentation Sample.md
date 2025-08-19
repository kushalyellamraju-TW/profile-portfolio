# API Documentation for creating an order using Product ID 
The following code snippet is used for creating documentation.<br>
```{
  "customer_id": "string",
  "items": [
    {
      "product_id": "string",
      "quantity": "integer"
    }
  ],
  "payment_method": "card | upi | cod"
}
```

# Description
Creates a new customer order with the selected items and payment method.<br>

# Method
POST - //server:port/v1/orders

# Authorization
Bearer [token]

# Request Parameters 
|Parameters| Data Type |  Mandatory(Y/N) | Description |
|-----------|-----------|-----------------|-------------|
| customer_id| String   |    Y            |Unique Id of customer placing the order|
|   items|Array    | Y|     List of items in the order. Each item must include product_id and quantity.  |
|product_id| String| Y| Unique identifier for the product|
|quantity|Integer|Y| Defines the number of items ordered|
|payment_method|String|Y|Defines the type of payment. Namely Card, UPI, COD (Cash on delivery)|

# cURL Command
Use the example curl command to submit a request on the REST resource:
```
curl \
   -X POST \
   -H "Content-Type: application/json" \
   -u 'Authorization: Bearer <token> \
   -L "http://server:port/v1/orders" \
   -d '{"Use this placeholder to plug-in the example request body given below"}'
```

# Example Request Code
```
{
  "customer_id": "CUST1234",
  "items": [
    {
      "product_id": "BIRYANI002",
      "quantity": 4
    }
  ],
  "payment_method": "upi"
}
```
# Example Response Code
```
{
  "order_id": "ORD112233",
  "status": "confirmed",
  "estimated_delivery": "11-08-2024 18:25"
}
```
# Response Parameters
|Parameters| Data Type |  Mandatory(Y/N) | Description |
|-----------|-----------|-----------------|-------------|
| order_id| String   |    Y            |Unique Id of order|
|   status|String    | Y|     Tells if the order is confirmed or denied|
|estimated_delivery| String| Y| Tells the delivery date and time|

# Example Error Code 
```
{
  "error_code": "INVALID_PAYMENT",
  "message": "Payment method not supported."
}
```
# Response Codes 
| Code| Description |
|-----------|-----------|
| 201| Created (The request is created)|  
| 400 |Bad Request (The server could not understand the request, make modifications to proceed)|
|401| Unauthorized (When authentication is invaild)|
|404| Not Found (Server could not find the request resource)|
