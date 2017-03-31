# Customer

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

## Create a new customer

#### Example request

```http
POST /channel/customers

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "customer": {
    "email": "filippo@commercelayer.io"
  } 
}
```

#### Example response
```http
...
```

## Add customer to order

### Option 1: Existing customer

#### Example request

```http
PUT /channel/orders/<order_token>

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "order": {
    "customer_id": 123
  } 
}
```

#### Example response
```http
...
```

### Option 2: New customer

#### Example request

```http
PUT /channel/orders/<order_token>

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
  "order": {
    "customer_attributes": {
      "email": "filippo@commercelayer.io"
    }
  } 
}
```

#### Example response
```http
...
```