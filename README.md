## BotBroker v2 API docs

Welcome to the documentation for the v2 API for [BotBroker](https://botbroker.io). If you're moving from the private v1, the information is more organized and in a more flexible format. There's also performance improvements.

API keys will be given out on a request basis. To request, DM [@66_shrey](https://twitter.com/66_shrey) on Twitter. Any API updates will be posted there as well, so I'd follow if you'll be using the API
in any capacity.

### Introduction

There's just a few main resources in this API that you should understand:

1. **Bots** are a type of product. They can have asks, bids, and sales
2. **Groups** are also a type of product. They're exactly like bots
3. **Asks** are active listings that are available for purchase right now
4. **Sales** are purchased listings. They are almost exactly the same as asks
5. **Bids** are active purchase orders that sellers can sell to right now

Each of these have their own endpoints, and will have their own documentation file in this repo.

### Structure

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

