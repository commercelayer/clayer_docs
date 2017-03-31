# Shopping Cart

### Add to cart (empty)

##### Example request

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

##### Example response
```http
```

### Add to cart (not empty)

##### Option 1: Example request

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
				"sellable_id": 24,
				"quantity": 1
			}
		]
	}	
}
```

##### Example response
```http
```

##### Option 2: Example request

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

##### Example response
```http
```

### Edit cart

#### Edit a line item quantity

##### Option 1: Example request

```http
PUT /channel/orders/<order_token>

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en

{
	"order": {
		"line_items_attributes": [
			{
				"id": 23
				"quantity": 4
			}
		]
	}	
}
```

##### Example response
```http
```

##### Option 2: Example request

```http
PUT /channel/orders/<order_token>/line_items/23

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

##### Example response
```http
```

#### Remove from cart

##### Option 1: Example request

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
			}
		]
	}	
}
```

##### Example response
```http
```

##### Option 2: Example request

```http
DELETE /channel/orders/<order_token>/line_items/23

Authorization: Bearer <access_token>
Content-Type: application/json
Accept-Language: en
```

##### Example response
```http
```