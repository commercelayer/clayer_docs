# Place order

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

## Direct payments (Credit card, wire transfer)

#### Example request

```http
PUT /channel/orders/<order_token>/place

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en
```

#### Example response
```http
...
```

## Offsite payments (PayPal)

#### Example request

```http
PUT /channel/orders/<order_token>/place

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en
```

#### Example response
```http
...
```

#### Example request

```http
GET /channel/transactions/<transaction_token>

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en
```

#### Example response
```http
...
```
