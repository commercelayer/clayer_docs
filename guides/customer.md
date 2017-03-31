# Customer

## Create a new customer

### Example request

```http
POST /channel/customers

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
    "customer": {
        "email": "jason@commercelayer.io"
	}	
}
```

### Example response
```http
...
```

## Add customer to order

### Option 1: Example request

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

### Example response
```http
...
```

### Option 2: Example request

```http
PUT /channel/orders/<order_token>

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
    "order": {
        "customer_attributes": {
            "email": "jason@commercelayer.io"
        }
	}	
}
```

### Example response
```http
...
```