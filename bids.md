# Bid endpoints

### Get all bids 
`GET` /bids?product_id=:product_id

Returns a list of bids in the following format:
```json
{
  "pagination": {...},
  "sort_by": "id",
  "order": "desc",
  "asks": [
    {
      "id": 69714,
      "created_at": 1603649484,
      "expiration": null,
      "key_type": "lifetime",
      "price": 200,
      "product_id": 30,
      "specification": null
    },
    {
      "id": 69714,
      "created_at": 1603649484,
      "expiration": null,
      "key_type": "lifetime",
      "price": 200,
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

### Get specific bid
`GET` /bids/:id

Returns a bid object in the following format:
```json
{
  "bid": {
    "id": 71687,
    "created_at": 1605015032,
    "expiration": null,
    "key_type": "lifetime",
    "price": 230,
    "product_id": 30,
    "specification": null
  }
}
```