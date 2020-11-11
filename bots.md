# Bot endpoints

### Get all bots 
`GET` /bots

Returns a list of bots in the following format:
```json
{
  "pagination": {...},
  "sort_by": "id",
  "order": "asc",
  "bots": [
    {
      "id": 2,
      "category": "footsites,adidas,supreme,yeezysupply",
      "color": "#2d252c",
      "image": "https://i.imgur.com/8satPLU.png",
      "maintenance": true,
      "maintenance_message": "The Phantom team is performing some routine maintenance, and we'll be back very very soon",
      "name": "Phantom",
      "twitter": "GhostAIO",
      "url": "/products/phantom"
    },
    {
      "id": 4,
      "category": "shopify,supreme,yeezysupply",
      "color": "#314071",
      "image": "https://i.imgur.com/CV6MWXM.png",
      "maintenance": false,
      "maintenance_message": null,
      "name": "Dashe",
      "twitter": "Dashe",
      "url": "/products/dashe"
    }
  ]
}
```

Optional parameters:
- `page` to paginate through the list
- `sort_by` parameter to sort by: id (default) or name
- `order` the direction to sort the list in: desc (default) or asc

### Get specific bot
`GET` /bots/:id

Returns a bot object in the following format:
```json
{
  "bot": {
    "id": 6,
    "category": "shopify,supreme,footsites,mesh,offwhite",
    "color": "#282828",
    "image": "https://i.imgur.com/cvdVKqb.png",
    "maintenance": false,
    "maintenance_message": "Bids and asks for Cybersole are paused while they make API updates",
    "name": "CyberAIO",
    "twitter": "Cybersole",
    "url": "/products/cyberaio"
  }
}
```