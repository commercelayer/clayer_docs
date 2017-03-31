# Shopping Cart

## Add to cart (empty)

#### Example request

```http
POST /channel/orders

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "order": {
    "line_items_attributes": [
      {
        "sellable_resource": "product",
        "sellable_id": 23,
        "quantity": 2
      }
    ]
  } 
}
```

#### Example response
```http
...
```

## Get shopping cart

#### Example request

```http
GET /channel/orders/<order_token>

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

```

#### Example response
```http
...
```

## Add to cart (not empty)

### Option 1: single line item

#### Example request

```http
POST /channel/orders/<order_token>/line_items

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "line_item": {
    {
      "sellable_resource": "product",
      "sellable_id": 24,
      "quantity": 1
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
PUT /channel/orders/<order_token>

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "order": {
    "line_items_attributes": [
      {
        "sellable_resource": "product",
        "sellable_id": 23,
        "quantity": 5
      },
      {
        "sellable_resource": "product",
        "sellable_id": 24,
        "quantity": 1
      }
    ]
  } 
}
```

#### Example response
```http
...
```

## Edit cart (quantity)

### Option 1: Single line item

#### Example request

```http
PUT /channel/orders/<order_token>/line_items/123

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "line_item": {
    {
      "quantity": 4
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
PUT /channel/orders/<order_token>

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "order": {
    "line_items_attributes": [
      {
        "id": 123
        "quantity": 4
      },
      {
        "id": 124
        "quantity": 7
      }     
    ]
  } 
}
```

#### Example response
```http
...
```

## Remove from cart

### Option 1: Single line item

#### Example request

```http
DELETE /channel/orders/<order_token>/line_items/123

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en
```

#### Example response
```http
...
```

### Option 2: Multiple line items

#### Example request

```http
PUT /channel/orders/<order_token>

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "order": {
    "line_items_attributes": [
      {
        "id": 123,
        "_destroy": "1"       
      },
      {
        "id": 124,
        "_destroy": "1"       
      }     
    ]
  } 
}
```

#### Example response
```http
...
```

## Estimate Shipping cost

#### Example request

```http
GET /channel/orders/<order_token>/available_shipping_services?estimate=true&state_code=NY&zip=10005

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

```

#### Example response
```http
...
```