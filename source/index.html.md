---
title: API Reference

language_tabs:
  - shell
  - go

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Takonews API! You can use our API to access Takonews API endpoints, which can get information on various articles, news_sites, and feeds in our database.

We have language bindings in Shell and Go! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```go
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Takonews uses Basic authentication to allow access to the API. 

Takonews expects for ID/PASS to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>ID/PASS</code> with your personal ID/PASS.
</aside>

# Articles

## Article Resource

Generic article information. By default, only public information is shared without any scopes. More detailed information or email can be requested with additional scopes.

Fields | Description
--------- | -----------
id | article id
title | article's title
news_site_id | news site's id
url | article's url
title | article's title
full_text | article's full text
published_at | published_at

## Get All Articles

```shell
curl --user tako:nasu "http://<hostname>/api/v2/articles"
```

```go
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
 [
    {
      "id": 1,
      "title": "TITLE", 
      "news_site_id": 5,         
      "url": "http:..",           
      "published_at": "2015-02-20 9:00:00"
    },
    {
      "id": 2, 
      "title": "TITLE",                  
      "news_site_id": 3,           
      "url": "http:..",      
      "published_at": "2015-02-21 9:00:00"
    }
  ]
```

This endpoint retrieves all articles.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
fileds | id,title,news_site_id,url | filter output fields.
start-date | 0:00  | format: YYYY-MM-DD
end-date | 24:00 | format: YYYY-MM-DD

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

# Kittens

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

