# Payment Methods

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

## Get available payment types

#### Example request

```http
GET /channel/orders/<order_token>/available_payment_types

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en
```

#### Example response
```http
...
```

## Add payment method to order

### Option 1: New credit card, billing address same as shipping

#### Example request

```http
POST /channel/orders/<order_token>/payment_methods

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "payment_method": {
    "payment_source_attributes": {
      "resource": "credit_card",
      "first_name": "Filippo",
      "last_name": "Conforti",
      "number": "4111111111111111",
      "verification_value": "423",
      "month": "3",
      "year": "2032"
    },
    "billing_recipient_id": 555,
    "billing_address_id": 777
  } 
}
```

#### Example response
```http
...
```

### Option 2: New paypal_account, billing address same as shipping

#### Example request

```http
POST /channel/orders/<order_token>/payment_methods

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "payment_method": {
    "payment_source_attributes": {
      "resource": "paypal_account"
    },
    "redirect_url": "http://example.com/redirect",
    "billing_recipient_id": 555,
    "billing_address_id": 777
  } 
}
```

#### Example response
```http
...
```

### Option 3: New wire_transfer, billing address same as shipping

#### Example request

```http
POST /channel/orders/<order_token>/payment_methods

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "payment_method": {
    "payment_source_attributes": {
      "resource": "wire_transfer"
    },
    "billing_recipient_id": 555,
    "billing_address_id": 777
  } 
}
```

#### Example response
```http
...
```

### Option 4: Any payment type, new billing address and recipient

#### Example request

```http
POST /channel/orders/<order_token>/payment_methods

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "payment_method": {
    "payment_source_attributes": {
      "resource": "wire_transfer"
    },
    "billing_recipient_attributes": {
      "name": "Massimo Scardellato",
      "phone": "+39 1234567890"
    },
    "billing_address_attributes": {
      "geocoding_street": "Via Del Carmine",
      "geocoding_number": "13",
      "geocoding_city": "Prato",
      "geocoding_zip": "59100"
    }
  } 
}
```

#### Example response
```http
...
```

## Add multiple payment methods to order

#### Example request

```http
POST /channel/orders/<order_token>/payment_methods

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "payment_method": {
    "payment_source_attributes": {
      "resource": "credit_card",
      "first_name": "Filippo",
      "last_name": "Conforti",
      "number": "4111111111111111",
      "verification_value": "423",
      "month": "3",
      "year": "2032"
    },
    "billing_recipient_id": 555,
    "billing_address_id": 777,
    "amount": 300
  } 
}
```

#### Example response
```http
...
```

#### Example request

```http
POST /channel/orders/<order_token>/payment_methods

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "payment_method": {
    "payment_source_attributes": {
      "resource": "wire_transfer"
    },
    "billing_recipient_id": 555,
    "billing_address_id": 777
  } 
}
```

#### Example response
```http
...
```