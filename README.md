## BotBroker v2 API docs

Welcome to the documentation for the v2 API for [BotBroker](https://botbroker.io). If you're moving from the private v1, the information is more organized and in a more flexible format. There's also performance improvements.

API keys will be given out on a request basis. To request, DM [@66_shrey](https://twitter.com/66_shrey) on Twitter. Any API updates will be posted there as well, so I'd follow if you'll be using the API
in any capacity.

### Introduction

The base URL is `https://api.botbroker.io/api/v2` and all API routes will come
after this base URL.

There's just a few main resources in this API that you should understand:

1. **Bots** are a type of product. They can have asks, bids, and sales
2. **Groups** are also a type of product. They're exactly like bots
3. **Asks** are active listings that are available for purchase right now
4. **Sales** are purchased listings. They are almost exactly the same as asks
5. **Bids** are active purchase orders that sellers can sell to right now

Each of these have their own endpoints, and will have their own documentation file in this repo.

### Parameters

All parameters in `GET` requests should be specified in the URL unless stated otherwise. In all
`POST` requests, parameters should be sent via a json body.

### Success / Errors

Each successful request will either be of status code `200` or `204` (if the body is empty). On errors you'll get a status code along with a 
`message` parameter describing the error in more detail. Here's an example:

```json
{
  "message": "Invalid bot ID"
}
```

### Authentication / rate limiting

Every request must have an `x-api-key` header in it with your API key. The default rate limit is 5 requests in a 20 second span.
This is just the default. If you need this rate limit raised, feel free to reach out to me.

If you pass your rate limit, you'll get `429` responses with a message describing how long until you're allowed again.

Here's an example:
```json
{
  "message": "You are rate limited for the next 36 seconds"
}
```

### Pagination

Requests in this API that involve lists are paginated unless they explicity state that they aren't. To paginate through a list,
supply a `page` url parameter. For example: `/v2/bots?page=2` will take you to the 2nd page of the list.

If a request is paginated, it'll come with a `pagination` parameter that looks like this:

```json
{
  "pagination": {
    "next": 2,
    "page": 1,
    "per_page": 20,
    "prev": null,
    "total_count": 40
  },
  "paginated_list": [...]
}
```

`next` is the next page in the list. `prev` is the previous page. Both of those can be null if there's no previous/next page. `per_page` is the # of items on the current page, and `total_count` is the size of the entire list.



