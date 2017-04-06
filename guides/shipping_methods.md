# Shipping Methods

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est laborum. This is my change.

## Add shipping method to order

### Option 1: New shipping recipient and address

#### Example request

```http
POST /channel/orders/<order_token>/shipping_methods

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "shipping_method": {
    "shipping_recipient_attributes": {
      "name": "Filippo Conforti",
      "phone": "+39 1234567890"
    },
    "shipping_address_attributes": {
      "geocoding_street": "Via Del Carmine",
      "geocoding_number": "11",
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

### Option 2: Existing shipping recipient and address

#### Example request

```http
POST /channel/orders/<order_token>/shipping_methods

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "shipping_method": {
    "shipping_recipient_id": 321,
    "shipping_address_id": 456
  } 
}
```

#### Example response
```http
...
```

## Get available shipping services

#### Example request

```http
GET /channel/shipping_methods/223/available_shipping_services

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en
```

#### Example response
```http
...
```

## Add shipping service to shipping method

#### Example request

```http
PUT /channel/shipping_methods/223

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "shipping_method": {
    "shipping_service_id": 1234
  } 
}
```

#### Example response
```http
...
```

## Add multiple shipping methods to order

### Option 1: Single line item

#### Example request

```http
POST /channel/line_items/123/shipping_methods

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "shipping_method": {
    "shipping_recipient_attributes": {
      "name": "Filippo Conforti",
      "phone": "+39 1234567890"
    },
    "shipping_address_attributes": {
      "geocoding_street": "Via Del Carmine",
      "geocoding_number": "11",
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

### Option 2: Multiple line items

#### Example request

```http
POST /channel/orders/<order_token>/shipping_methods

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "shipping_method": {
    "_line_item_ids": [1,2,3],
    "shipping_recipient_attributes": {
      "name": "Filippo Conforti",
      "phone": "+39 1234567890"
    },
    "shipping_address_attributes": {
      "geocoding_street": "Via Del Carmine",
      "geocoding_number": "11",
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