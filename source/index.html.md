---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

# toc_footers:
#   - <a href='#'>Sign Up for a Developer Key</a>
#   - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Service socket API! You can use our API to access Service socket API endpoints,

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can jus=t pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: key=app_secret"
```

```javascript
const kittn = require("kittn");

let api = kittn.authorize("meowmeowmeow");
```

> Make sure to replace `meowmeowmeow` with your API key.

`Authorization: key=Appsecret`

<aside class="notice">
You must replace <code>Appsecret</code> with your personal Appsecret key.
</aside>

# Channel

## Subscribe

<!-- ```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
``` -->

```javascript
const kittn = require("kittn");

let api = kittn.authorize("meowmeowmeow");
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
"code":0
"data":{},
"message":"Success",
"Error":null
```

This endpoint retrieves all kittens.

### HTTP Request

`POST /channel/subscribe`,

### Header

### Query Parameters

| Parameter  | Default | Description                   |
| ---------- | ------- | ----------------------------- |
| channel    | null    | Channel you want to subsribe. |
| app_secret | null    | your App_secret .             |

<aside class="success">
Remember — a happy send is an authenticated !
</aside>

# Chat

## send

```javascript
const kittn = require("kittn");

let api = kittn.authorize("meowmeowmeow");
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
"code":0
"data":{},
"message":"Success",
"Error":null
```

This endpoint send to channel, event include data.

### HTTP Request

`POST /chat/send`

### Header

| Parameter | Default | Description |
| --------- | ------- | ----------- |


Authorization key=Appsecret

### Query Parameters

| Parameter | Default | Description              |
| --------- | ------- | ------------------------ |
| channel   | null    | channel you want to send |
| event     | null    | event you want to send   |
| data      | null    | data you want to send    |

<aside class="success">
Remember — a happy send is an authenticated!
</aside>

## sendMulti

```javascript
const kittn = require("kittn");

let api = kittn.authorize("meowmeowmeow");
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
"code":0
"data":{},
"message":"Success",
"Error":null
```

This endpoint send multi message to multi channel, event include data.

### HTTP Request

`POST /chat/send-multi`

### Header

| Parameter | Default | Description |
| --------- | ------- | ----------- |


Authorization key=Appsecret

### Query Parameters

| Parameter | Default | Description                    |
| --------- | ------- | ------------------------------ |
| body      | []      | array message you want to send |

### Message Parameters

| Parameter | Default | Description              |
| --------- | ------- | ------------------------ |
| channel   | null    | channel you want to send |
| event     | null    | event you want to send   |
| data      | null    | data you want to send    |

<aside class="success">
Remember — a happy send is an authenticated!
</aside>
