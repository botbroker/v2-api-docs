# Sale endpoints

### Get all sales 
`GET` /sales?product_id=:product_id

Returns a list of sales in the following format:
```json
{
  "pagination": {...},
  "sort_by": "id",
  "order": "desc",
  "asks": [
    {
      "id": 77912,
      "created_at": 1604356618,
      "expiration": null,
      "key_type": "lifetime",
      "matched_at": 1604364551,
      "price": 470,
      "product_id": 30,
      "specification": null
    },
    {
      "id": 77912,
      "created_at": 1604356618,
      "expiration": null,
      "key_type": "lifetime",
      "matched_at": 1604364551,
      "price": 470,
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
- `sort_by` the parameter to sort by. either "id" (default), "price", or "matched_at"
- `order` the direction to sort the list in: desc (default) or asc
- `key_type` either "lifetime" or "renewal". Will return both types if left blank

### Get chart data
`GET` /sales/chart?product_id=:product_id&days=:days&key_type=:key_type

Will return a full list of sales in the following format:
```json
{
  "sales": [
    {
      "matched_at": 1605106453,
      "price": 5252
    },
    {
      "matched_at": 1604980272,
      "price": 5400
    },
    {
      "matched_at": 1604971704,
      "price": 5250
    }
  ]
}
```

Required parameters:
- `product_id` the bot / group to filter by
- `days` how many days of sale history you'd like to see. Must be between 1 - 365
- `key_type` either "lifetime" or "renewal"

### Get specific sale
`GET` /sales/:id

Returns a sale object in the following format:
```json
{
  "sale": {
    "id": 77912,
    "created_at": 1604356618,
    "expiration": null,
    "key_type": "lifetime",
    "matched_at": 1604364551,
    "price": 470,
    "product_id": 30,
    "specification": null
  }
}
```