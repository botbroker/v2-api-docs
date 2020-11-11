# Ask endpoints

### Get all asks 
`GET` /asks?product_id=:product_id

Returns a list of asks (sorted by the ID) in the following format:
```json
{
  "pagination": {...},
  "sort_by": "id",
  "order": "desc",
  "asks": [
    {
      "id": 79502,
      "created_at": 1605047025,
      "expiration": null,
      "key_type": "lifetime",
      "price": 365,
      "product_id": 30,
      "specification": null
    },
    {
      "id": 79502,
      "created_at": 1605047025,
      "expiration": null,
      "key_type": "lifetime",
      "price": 365,
      "product_id": 30,
      "specification": null
    }
  ]
}
```

Required parameters
- `product_id` the ID of the bot / group to filter by

Optional parameters:
- `page` to paginate through the list
- `sort_by` the parameter to sort by. either "id" (default) or "price"
- `order` the direction to sort the list in: desc (default) or asc
- `key_type` either "lifetime" or "renewal". Will return both types if left blank

### Get specific ask
`GET` /asks/:id

Returns an ask object in the following format:
```json
{
  "ask": {
    "id": 79502,
    "created_at": 1605047025,
    "expiration": 3155840024,
    "key_type": "lifetime",
    "price": 365,
    "specification": null
  }
}
```