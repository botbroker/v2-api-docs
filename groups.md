# Group endpoints

### Get all groups 
`GET` /groups

Returns a list of groups in the following format:
```json
{
  "pagination": {...},
  "sort_by": "id",
  "order": "asc",
  "bots": [
    {
      "id": 16,
      "category": "groups",
      "color": "#252525",
      "image": "https://i.imgur.com/dW6eG6j.png",
      "maintenance": true,
      "maintenance_message": null,
      "name": "351io",
      "twitter": "351io",
      "url": "/groups/351io"
    }
  ]
}
```

Optional parameters:
- `page` to paginate through the list
- `sort_by` parameter to sort by: id (default) or name
- `order` the direction to sort the list in: desc (default) or asc

### Get specific group
`GET` /groups/:id

Returns a group object in the following format:
```json
{
  "group": {
    "id": 16,
    "category": "groups",
    "color": "#252525",
    "image": "https://i.imgur.com/dW6eG6j.png",
    "maintenance": true,
    "maintenance_message": null,
    "name": "351io",
    "twitter": "351io",
    "url": "/groups/351io"
  }
}
```