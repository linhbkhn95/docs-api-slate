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

Welcome to the Service socket API! You can use our API to access Service socket API endpoints

use flow with reference for connect to service:

- <a href="https://stackoverflow.com/questions/25081188/sending-socket-request-from-client-ios-android-to-sails-js-server">https://stackoverflow.com/questions/25081188/sending-socket-request-from-client-ios-android-to-sails-js-server</a>

- <a href="https://www.logisticinfotech.com/blog/realtime-communication-using-socketio-sailsjs">https://www.logisticinfotech.com/blog/realtime-communication-using-socketio-sailsjs/</a>

- <a href="https://stackoverflow.com/questions/46514939/problems-subscribing-to-a-room-socket-with-socket-io-client-swift-and-swift-s?rq=1">https://stackoverflow.com/questions/46514939/problems-subscribing-to-a-room-socket-with-socket-io-client-swift-and-swift-s?rq=1</a>

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

# Connection

## Config

use flow with reference for connect to service:

- <a href="https://stackoverflow.com/questions/25081188/sending-socket-request-from-client-ios-android-to-sails-js-server">https://stackoverflow.com/questions/25081188/sending-socket-request-from-client-ios-android-to-sails-js-server</a>

- <a href="https://www.logisticinfotech.com/blog/realtime-communication-using-socketio-sailsjs">https://www.logisticinfotech.com/blog/realtime-communication-using-socketio-sailsjs/</a>

- <a href="https://stackoverflow.com/questions/46514939/problems-subscribing-to-a-room-socket-with-socket-io-client-swift-and-swift-s?rq=1">https://stackoverflow.com/questions/46514939/problems-subscribing-to-a-room-socket-with-socket-io-client-swift-and-swift-s?rq=1</a>

### Query Parameters

| Parameter                | Type   | Default | Description                     |
| ------------------------ | ------ | ------- | ------------------------------- |
| url                      | String | ''      | Url for connection              |
| key                      | String | ''      | Your Appsecret                  |
| \_\_sails_io_sdk_version | String | ''      | version sdk sails socket client |

# Channel

## Subscribe

This endpoint send to subcribe channel.

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

### HTTP Request

`POST /channel/subscribe`,

### Header

### Query Parameters

| Parameter | Type                   | Default | Description                   |
| --------- | ---------------------- | ------- | ----------------------------- |
| channel   | String or Array String | Guest   | Channel you want to subsribe. |

<aside class="success">
Remember — a happy send is an authenticated !
</aside>

## unSubscribe

This endpoint send to unsubcribe channel joined.

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

### HTTP Request

`POST /channel/unsubscribe`,

### Header

### Query Parameters

| Parameter | Type                   | Default | Description                   |
| --------- | ---------------------- | ------- | ----------------------------- |
| channel   | String or Array String | Guest   | Channel you want to subsribe. |

<aside class="success">
Remember — a happy send is an authenticated !
</aside>
# Push Message

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

`POST /wssv/send`

### Header

| Parameter | Default | Description |
| --------- | ------- | ----------- |


Authorization key=Appsecret

### Query Parameters

| Parameter | Type                   | Default | Description              |
| --------- | ---------------------- | ------- | ------------------------ |
| channel   | String or Array String | null    | channel you want to send |
| event     | String                 | Message | event you want to send   |
| data      | Full body              | null    | data you want to send    |

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

`POST /wssv/send-multi`

### Header

| Parameter | Default | Description |
| --------- | ------- | ----------- |


Authorization key=Appsecret

### Query Parameters

| Parameter | Type  | Default | Description                    |
| --------- | ----- | ------- | ------------------------------ |
| body      | Array | []      | array message you want to send |

### Message Parameters

| Parameter | Type                   | Default | Description              |
| --------- | ---------------------- | ------- | ------------------------ |
| channel   | String or Array String | null    | channel you want to send |
| event     | String                 | Message | event you want to send   |
| data      | Full body              |         | data you want to send    |

<aside class="success">
Remember — a happy send is an authenticated!
</aside>

## get list message

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

`GET /wssv/message`

### Header

| Parameter | Default | Description |
| --------- | ------- | ----------- |


Authorization key=Appsecret

### Query Parameters

| Parameter | Type   | Default            | Description                  |
| --------- | ------ | ------------------ | ---------------------------- |
| channel   | string |                    | channel of message sent      |
| event     | string |                    | event of message sent        |
| data      | string |                    | data of message sent         |
| sort      | array  | ['createdAt_DESC'] | sort                         |
| limit     | number | 10                 | limit record response        |
| skip      | number | 0                  | skip record from option skip |

<aside class="success">
Remember — a happy send is an authenticated!
</aside>
