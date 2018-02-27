---
title: Peatio SDK v0.2.6
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2


---


<h1 id="Peatio-SDK">Peatio SDK v0.2.6</h1>


> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.


Base URLs:


* <a href="http://localhost:8000/api/v2">http://localhost:8000/api/v2</a>


* <a href="https://localhost:8000/api/v2">https://localhost:8000/api/v2</a>


# Authentication


- oAuth2 authentication. 


    - Flow: implicit
    - Authorization URL = [https://demo.peatio.tech/auth/auth0](https://demo.peatio.tech/auth/auth0)


|Scope|Scope Description|
|---|---|
|write:peatio|base write scope|
|read:peatio|base read scope|


<h1 id="Peatio-SDK-markets">markets</h1>


Operations about markets


## getV2Markets


<a id="opIdgetV2Markets"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/markets \
  -H 'Accept: application/json'


```


```http
GET http://localhost:8000/api/v2/markets HTTP/1.1
Host: localhost:8000


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: 'http://localhost:8000/api/v2/markets',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('http://localhost:8000/api/v2/markets',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get 'http://localhost:8000/api/v2/markets',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('http://localhost:8000/api/v2/markets', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/markets");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /markets`


*Get all available markets.*


Get all available markets.


> Example responses


```json
[
  {
    "id": "btcusd",
    "name": "BTC/USD"
  }
]
```


<h3 id="getV2Markets-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get all available markets.|Inline|


<h3 id="getV2Markets-responseschema">Response Schema</h3>


Status Code **200**


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[[Market](#schemamarket)]|false|No description|
|» id|string|false|No description|
|» name|string|false|No description|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


<h1 id="Peatio-SDK-tickers">tickers</h1>


Operations about tickers


## getV2Tickers


<a id="opIdgetV2Tickers"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/tickers \
  -H 'Accept: application/json'


```


```http
GET http://localhost:8000/api/v2/tickers HTTP/1.1
Host: localhost:8000


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: 'http://localhost:8000/api/v2/tickers',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('http://localhost:8000/api/v2/tickers',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get 'http://localhost:8000/api/v2/tickers',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('http://localhost:8000/api/v2/tickers', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/tickers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /tickers`


*Get ticker of all markets.*


Get ticker of all markets.


> Example responses


```json
{
  "property1": {
    "at": 1515672822,
    "ticker": {
      "buy": 3000,
      "sell": 3100,
      "low": 3000,
      "high": 3000,
      "last": 3000,
      "vol": 0.11
    }
  },
  "property2": {
    "at": 1515672822,
    "ticker": {
      "buy": 3000,
      "sell": 3100,
      "low": 3000,
      "high": 3000,
      "last": 3000,
      "vol": 0.11
    }
  }
}
```


<h3 id="getV2Tickers-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get ticker of all markets.|Inline|


<h3 id="getV2Tickers-responseschema">Response Schema</h3>


Status Code **200**


|Name|Type|Required|Description|
|---|---|---|---|
|» **additionalProperties**|[TickerInfo](#schematickerinfo)|false|No description|
|»» at|integer|false|No description|
|»» ticker|object|false|No description|
|»»» buy|number|false|No description|
|»»» sell|number|false|No description|
|»»» low|number|false|No description|
|»»» high|number|false|No description|
|»»» last|number|false|No description|
|»»» vol|number|false|No description|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


## getV2TickersMarket


<a id="opIdgetV2TickersMarket"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/tickers/{market} \
  -H 'Accept: application/json'


```


```http
GET http://localhost:8000/api/v2/tickers/{market} HTTP/1.1
Host: localhost:8000


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: 'http://localhost:8000/api/v2/tickers/{market}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('http://localhost:8000/api/v2/tickers/{market}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get 'http://localhost:8000/api/v2/tickers/{market}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('http://localhost:8000/api/v2/tickers/{market}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/tickers/{market}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /tickers/{market}`


*Get ticker of specific market.*


Get ticker of specific market.


<h3 id="getV2TickersMarket-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|market|path|string|true|Unique market id. It's always in the form of xxxyyy, where xxx is the base currency code, yyy is the quote currency code, e.g. 'btcusd'. All available markets can be found at /api/markets.|


#### Enumerated Values


|Parameter|Value|
|---|---|
|market|btcusd|
|market|xrpusd|
|market|btcxrp|


> Example responses


```json
{
  "at": 1515672822,
  "ticker": {
    "buy": 3000,
    "sell": 3100,
    "low": 3000,
    "high": 3000,
    "last": 3000,
    "vol": 0.11
  }
}
```


<h3 id="getV2TickersMarket-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get ticker of specific market.|[TickerInfo](#schematickerinfo)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


<h1 id="Peatio-SDK-members">members</h1>


Operations about members


## getV2MembersMe


<a id="opIdgetV2MembersMe"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/members/me \
  -H 'Accept: application/json'


```


```http
GET http://localhost:8000/api/v2/members/me HTTP/1.1
Host: localhost:8000


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: 'http://localhost:8000/api/v2/members/me',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('http://localhost:8000/api/v2/members/me',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get 'http://localhost:8000/api/v2/members/me',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('http://localhost:8000/api/v2/members/me', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/members/me");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /members/me`


*Get your profile and accounts info.*


Get your profile and accounts info.


> Example responses


```json
{
  "sn": "PEAUV8S2JNPTIO",
  "name": "John Doe",
  "email": "jdoe@peatio.tech",
  "accounts": [
    {
      "currency": "usd",
      "balance": 0,
      "locked": 0
    }
  ]
}
```


<h3 id="getV2MembersMe-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get your profile and accounts info.|[Member](#schemamember)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


<h1 id="Peatio-SDK-deposits">deposits</h1>


Operations about deposits


## getV2Deposits


<a id="opIdgetV2Deposits"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/deposits


```


```http
GET http://localhost:8000/api/v2/deposits HTTP/1.1
Host: localhost:8000


```


```javascript


$.ajax({
  url: 'http://localhost:8000/api/v2/deposits',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('http://localhost:8000/api/v2/deposits',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'http://localhost:8000/api/v2/deposits',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('http://localhost:8000/api/v2/deposits', params={


)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/deposits");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /deposits`


*Get your deposits history.*


Get your deposits history.


<h3 id="getV2Deposits-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|currency|query|string|false|Currency value contains  usd,btc,xrp|
|limit|query|integer(int32)|false|Set result limit.|
|state|query|string|false|No description|


#### Enumerated Values


|Parameter|Value|
|---|---|
|currency|usd|
|currency|btc|
|currency|xrp|
|state|submitting|
|state|cancelled|
|state|submitted|
|state|rejected|
|state|accepted|
|state|checked|
|state|warning|


<h3 id="getV2Deposits-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get your deposits history.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


<h1 id="Peatio-SDK-deposit">deposit</h1>


Operations about deposits


## getV2Deposit


<a id="opIdgetV2Deposit"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/deposit?txid=string


```


```http
GET http://localhost:8000/api/v2/deposit?txid=string HTTP/1.1
Host: localhost:8000


```


```javascript


$.ajax({
  url: 'http://localhost:8000/api/v2/deposit',
  method: 'get',
  data: '?txid=string',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('http://localhost:8000/api/v2/deposit?txid=string',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'http://localhost:8000/api/v2/deposit',
  params: {
  'txid' => 'string'
}


p JSON.parse(result)


```


```python
import requests


r = requests.get('http://localhost:8000/api/v2/deposit', params={
  'txid': 'string'
)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/deposit?txid=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /deposit`


*Get details of specific deposit.*


Get details of specific deposit.


<h3 id="getV2Deposit-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|txid|query|string|true|No description|


<h3 id="getV2Deposit-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get details of specific deposit.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


<h1 id="Peatio-SDK-depositAddress">depositAddress</h1>


Operations about deposit addresses


## getV2DepositAddress


<a id="opIdgetV2DepositAddress"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/deposit_address?currency=usd


```


```http
GET http://localhost:8000/api/v2/deposit_address?currency=usd HTTP/1.1
Host: localhost:8000


```


```javascript


$.ajax({
  url: 'http://localhost:8000/api/v2/deposit_address',
  method: 'get',
  data: '?currency=usd',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('http://localhost:8000/api/v2/deposit_address?currency=usd',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'http://localhost:8000/api/v2/deposit_address',
  params: {
  'currency' => 'string'
}


p JSON.parse(result)


```


```python
import requests


r = requests.get('http://localhost:8000/api/v2/deposit_address', params={
  'currency': 'usd'
)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/deposit_address?currency=usd");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /deposit_address`


*Where to deposit. The address field could be empty when a new address is generating (e.g. for bitcoin), you should try again later in that case.*


Where to deposit. The address field could be empty when a new address is generating (e.g. for bitcoin), you should try again later in that case.


<h3 id="getV2DepositAddress-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|currency|query|string|true|The account to which you want to deposit. Available values: usd, btc, xrp|


#### Enumerated Values


|Parameter|Value|
|---|---|
|currency|usd|
|currency|btc|
|currency|xrp|


<h3 id="getV2DepositAddress-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Where to deposit. The address field could be empty when a new address is generating (e.g. for bitcoin), you should try again later in that case.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


<h1 id="Peatio-SDK-orders">orders</h1>


Operations about orders


## getV2Orders


<a id="opIdgetV2Orders"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/orders?market=btcusd


```


```http
GET http://localhost:8000/api/v2/orders?market=btcusd HTTP/1.1
Host: localhost:8000


```


```javascript


$.ajax({
  url: 'http://localhost:8000/api/v2/orders',
  method: 'get',
  data: '?market=btcusd',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('http://localhost:8000/api/v2/orders?market=btcusd',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'http://localhost:8000/api/v2/orders',
  params: {
  'market' => 'string'
}


p JSON.parse(result)


```


```python
import requests


r = requests.get('http://localhost:8000/api/v2/orders', params={
  'market': 'btcusd'
)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/orders?market=btcusd");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /orders`


*Get your orders, results is paginated.*


Get your orders, results is paginated.


<h3 id="getV2Orders-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|market|query|string|true|Unique market id. It's always in the form of xxxyyy, where xxx is the base currency code, yyy is the quote currency code, e.g. 'btcusd'. All available markets can be found at /api/markets.|
|state|query|string|false|Filter order by state, default to 'wait' (active orders).|
|limit|query|integer(int32)|false|Limit the number of returned orders, default to 100.|
|page|query|integer(int32)|false|Specify the page of paginated results.|
|order_by|query|string|false|If set, returned orders will be sorted in specific order, default to 'asc'.|


#### Enumerated Values


|Parameter|Value|
|---|---|
|market|btcusd|
|market|xrpusd|
|market|btcxrp|
|state|wait|
|state|done|
|state|cancel|
|order_by|asc|
|order_by|desc|


<h3 id="getV2Orders-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get your orders, results is paginated.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


## postV2Orders


<a id="opIdpostV2Orders"></a>


> Code samples


```shell
# You can also use wget
curl -X POST http://localhost:8000/api/v2/orders \
  -H 'Content-Type: application/x-www-form-urlencoded'


```


```http
POST http://localhost:8000/api/v2/orders HTTP/1.1
Host: localhost:8000
Content-Type: application/x-www-form-urlencoded


```


```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded'


};


$.ajax({
  url: 'http://localhost:8000/api/v2/orders',
  method: 'post',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "market": "btcusd",
  "side": "sell",
  "volume": "string",
  "price": "string",
  "ord_type": "limit"
}';
const headers = {
  'Content-Type':'application/x-www-form-urlencoded'


};


fetch('http://localhost:8000/api/v2/orders',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Content-Type' => 'application/x-www-form-urlencoded'
}


result = RestClient.post 'http://localhost:8000/api/v2/orders',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Content-Type': 'application/x-www-form-urlencoded'
}


r = requests.post('http://localhost:8000/api/v2/orders', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/orders");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /orders`


*Create a Sell/Buy order.*


Create a Sell/Buy order.


> Body parameter


```yaml
market: btcusd
side: sell
volume: string
price: string
ord_type: limit


```


<h3 id="postV2Orders-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|No description|
|» market|body|string|true|Unique market id. It's always in the form of xxxyyy, where xxx is the base currency code, yyy is the quote currency code, e.g. 'btcusd'. All available markets can be found at /api/markets.|
|» side|body|string|true|Either 'sell' or 'buy'.|
|» volume|body|string|true|The amount user want to sell/buy. An order could be partially executed, e.g. an order sell 5 btc can be matched with a buy 3 btc order, left 2 btc to be sold; in this case the order's volume would be '5.0', its remaining_volume would be '2.0', its executed volume is '3.0'.|
|» price|body|string|false|Price for each unit. e.g. If you want to sell/buy 1 btc at 3000 USD, the price is '3000.0'|
|» ord_type|body|string|false|No description|


#### Enumerated Values


|Parameter|Value|
|---|---|
|» market|btcusd|
|» market|xrpusd|
|» market|btcxrp|
|» side|sell|
|» side|buy|
|» ord_type|limit|
|» ord_type|market|


<h3 id="postV2Orders-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Create a Sell/Buy order.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


## postV2OrdersMulti


<a id="opIdpostV2OrdersMulti"></a>


> Code samples


```shell
# You can also use wget
curl -X POST http://localhost:8000/api/v2/orders/multi \
  -H 'Content-Type: application/x-www-form-urlencoded'


```


```http
POST http://localhost:8000/api/v2/orders/multi HTTP/1.1
Host: localhost:8000
Content-Type: application/x-www-form-urlencoded


```


```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded'


};


$.ajax({
  url: 'http://localhost:8000/api/v2/orders/multi',
  method: 'post',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "market": "btcusd",
  "orders[side]": "sell",
  "orders[volume]": [
    "string"
  ],
  "orders[price]": [
    "string"
  ],
  "orders[ord_type]": "limit"
}';
const headers = {
  'Content-Type':'application/x-www-form-urlencoded'


};


fetch('http://localhost:8000/api/v2/orders/multi',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Content-Type' => 'application/x-www-form-urlencoded'
}


result = RestClient.post 'http://localhost:8000/api/v2/orders/multi',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Content-Type': 'application/x-www-form-urlencoded'
}


r = requests.post('http://localhost:8000/api/v2/orders/multi', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/orders/multi");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /orders/multi`


*Create multiple sell/buy orders.*


Create multiple sell/buy orders.


> Body parameter


```yaml
market: btcusd
'orders[side]': sell
'orders[volume]':
  - string
'orders[price]':
  - string
'orders[ord_type]': limit


```


<h3 id="postV2OrdersMulti-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|No description|
|» market|body|string|true|Unique market id. It's always in the form of xxxyyy, where xxx is the base currency code, yyy is the quote currency code, e.g. 'btcusd'. All available markets can be found at /api/markets.|
|» orders[side]|body|[string]|true|Either 'sell' or 'buy'.|
|» orders[volume]|body|[string]|true|The amount user want to sell/buy. An order could be partially executed, e.g. an order sell 5 btc can be matched with a buy 3 btc order, left 2 btc to be sold; in this case the order's volume would be '5.0', its remaining_volume would be '2.0', its executed volume is '3.0'.|
|» orders[price]|body|[string]|false|Price for each unit. e.g. If you want to sell/buy 1 btc at 3000 USD, the price is '3000.0'|
|» orders[ord_type]|body|[string]|false|No description|


#### Enumerated Values


|Parameter|Value|
|---|---|
|» market|btcusd|
|» market|xrpusd|
|» market|btcxrp|
|» orders[side]|sell|
|» orders[side]|buy|
|» orders[ord_type]|limit|
|» orders[ord_type]|market|


<h3 id="postV2OrdersMulti-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Create multiple sell/buy orders.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


## postV2OrdersClear


<a id="opIdpostV2OrdersClear"></a>


> Code samples


```shell
# You can also use wget
curl -X POST http://localhost:8000/api/v2/orders/clear \
  -H 'Content-Type: application/x-www-form-urlencoded'


```


```http
POST http://localhost:8000/api/v2/orders/clear HTTP/1.1
Host: localhost:8000
Content-Type: application/x-www-form-urlencoded


```


```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded'


};


$.ajax({
  url: 'http://localhost:8000/api/v2/orders/clear',
  method: 'post',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "side": "sell"
}';
const headers = {
  'Content-Type':'application/x-www-form-urlencoded'


};


fetch('http://localhost:8000/api/v2/orders/clear',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Content-Type' => 'application/x-www-form-urlencoded'
}


result = RestClient.post 'http://localhost:8000/api/v2/orders/clear',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Content-Type': 'application/x-www-form-urlencoded'
}


r = requests.post('http://localhost:8000/api/v2/orders/clear', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/orders/clear");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /orders/clear`


*Cancel all my orders.*


Cancel all my orders.


> Body parameter


```yaml
side: sell


```


<h3 id="postV2OrdersClear-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|No description|
|» side|body|string|false|If present, only sell orders (asks) or buy orders (bids) will be canncelled.|


#### Enumerated Values


|Parameter|Value|
|---|---|
|» side|sell|
|» side|buy|


<h3 id="postV2OrdersClear-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Cancel all my orders.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


<h1 id="Peatio-SDK-order">order</h1>


Operations about orders


## getV2Order


<a id="opIdgetV2Order"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/order?id=0


```


```http
GET http://localhost:8000/api/v2/order?id=0 HTTP/1.1
Host: localhost:8000


```


```javascript


$.ajax({
  url: 'http://localhost:8000/api/v2/order',
  method: 'get',
  data: '?id=0',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('http://localhost:8000/api/v2/order?id=0',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'http://localhost:8000/api/v2/order',
  params: {
  'id' => 'integer(int32)'
}


p JSON.parse(result)


```


```python
import requests


r = requests.get('http://localhost:8000/api/v2/order', params={
  'id': '0'
)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/order?id=0");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /order`


*Get information of specified order.*


Get information of specified order.


<h3 id="getV2Order-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|query|integer(int32)|true|Unique order id.|


<h3 id="getV2Order-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get information of specified order.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


## postV2OrderDelete


<a id="opIdpostV2OrderDelete"></a>


> Code samples


```shell
# You can also use wget
curl -X POST http://localhost:8000/api/v2/order/delete \
  -H 'Content-Type: application/x-www-form-urlencoded'


```


```http
POST http://localhost:8000/api/v2/order/delete HTTP/1.1
Host: localhost:8000
Content-Type: application/x-www-form-urlencoded


```


```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded'


};


$.ajax({
  url: 'http://localhost:8000/api/v2/order/delete',
  method: 'post',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "id": 0
}';
const headers = {
  'Content-Type':'application/x-www-form-urlencoded'


};


fetch('http://localhost:8000/api/v2/order/delete',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Content-Type' => 'application/x-www-form-urlencoded'
}


result = RestClient.post 'http://localhost:8000/api/v2/order/delete',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Content-Type': 'application/x-www-form-urlencoded'
}


r = requests.post('http://localhost:8000/api/v2/order/delete', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/order/delete");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /order/delete`


*Cancel an order.*


Cancel an order.


> Body parameter


```yaml
id: 0


```


<h3 id="postV2OrderDelete-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|No description|
|» id|body|integer(int32)|true|Unique order id.|


<h3 id="postV2OrderDelete-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Cancel an order.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


<h1 id="Peatio-SDK-orderBook">orderBook</h1>


Operations about order books


## getV2OrderBook


<a id="opIdgetV2OrderBook"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/order_book?market=btcusd


```


```http
GET http://localhost:8000/api/v2/order_book?market=btcusd HTTP/1.1
Host: localhost:8000


```


```javascript


$.ajax({
  url: 'http://localhost:8000/api/v2/order_book',
  method: 'get',
  data: '?market=btcusd',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('http://localhost:8000/api/v2/order_book?market=btcusd',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'http://localhost:8000/api/v2/order_book',
  params: {
  'market' => 'string'
}


p JSON.parse(result)


```


```python
import requests


r = requests.get('http://localhost:8000/api/v2/order_book', params={
  'market': 'btcusd'
)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/order_book?market=btcusd");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /order_book`


*Get the order book of specified market.*


Get the order book of specified market.


<h3 id="getV2OrderBook-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|market|query|string|true|Unique market id. It's always in the form of xxxyyy, where xxx is the base currency code, yyy is the quote currency code, e.g. 'btcusd'. All available markets can be found at /api/markets.|
|asks_limit|query|integer(int32)|false|Limit the number of returned sell orders. Default to 20.|
|bids_limit|query|integer(int32)|false|Limit the number of returned buy orders. Default to 20.|


#### Enumerated Values


|Parameter|Value|
|---|---|
|market|btcusd|
|market|xrpusd|
|market|btcxrp|


<h3 id="getV2OrderBook-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get the order book of specified market.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


<h1 id="Peatio-SDK-depth">depth</h1>


Operations about depths


## getV2Depth


<a id="opIdgetV2Depth"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/depth?market=btcusd


```


```http
GET http://localhost:8000/api/v2/depth?market=btcusd HTTP/1.1
Host: localhost:8000


```


```javascript


$.ajax({
  url: 'http://localhost:8000/api/v2/depth',
  method: 'get',
  data: '?market=btcusd',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('http://localhost:8000/api/v2/depth?market=btcusd',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'http://localhost:8000/api/v2/depth',
  params: {
  'market' => 'string'
}


p JSON.parse(result)


```


```python
import requests


r = requests.get('http://localhost:8000/api/v2/depth', params={
  'market': 'btcusd'
)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/depth?market=btcusd");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /depth`


*Get depth or specified market. Both asks and bids are sorted from highest price to lowest.*


Get depth or specified market. Both asks and bids are sorted from highest price to lowest.


<h3 id="getV2Depth-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|market|query|string|true|Unique market id. It's always in the form of xxxyyy, where xxx is the base currency code, yyy is the quote currency code, e.g. 'btcusd'. All available markets can be found at /api/markets.|
|limit|query|integer(int32)|false|Limit the number of returned price levels. Default to 300.|


#### Enumerated Values


|Parameter|Value|
|---|---|
|market|btcusd|
|market|xrpusd|
|market|btcxrp|


<h3 id="getV2Depth-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get depth or specified market. Both asks and bids are sorted from highest price to lowest.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


<h1 id="Peatio-SDK-trades">trades</h1>


Operations about trades


## getV2Trades


<a id="opIdgetV2Trades"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/trades?market=btcusd


```


```http
GET http://localhost:8000/api/v2/trades?market=btcusd HTTP/1.1
Host: localhost:8000


```


```javascript


$.ajax({
  url: 'http://localhost:8000/api/v2/trades',
  method: 'get',
  data: '?market=btcusd',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('http://localhost:8000/api/v2/trades?market=btcusd',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'http://localhost:8000/api/v2/trades',
  params: {
  'market' => 'string'
}


p JSON.parse(result)


```


```python
import requests


r = requests.get('http://localhost:8000/api/v2/trades', params={
  'market': 'btcusd'
)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/trades?market=btcusd");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /trades`


*Get recent trades on market, each trade is included only once. Trades are sorted in reverse creation order.*


Get recent trades on market, each trade is included only once. Trades are sorted in reverse creation order.


<h3 id="getV2Trades-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|market|query|string|true|Unique market id. It's always in the form of xxxyyy, where xxx is the base currency code, yyy is the quote currency code, e.g. 'btcusd'. All available markets can be found at /api/markets.|
|limit|query|integer(int32)|false|Limit the number of returned trades. Default to 50.|
|timestamp|query|integer(int32)|false|An integer represents the seconds elapsed since Unix epoch. If set, only trades executed before the time will be returned.|
|from|query|integer(int32)|false|Trade id. If set, only trades created after the trade will be returned.|
|to|query|integer(int32)|false|Trade id. If set, only trades created before the trade will be returned.|
|order_by|query|string|false|If set, returned trades will be sorted in specific order, default to 'desc'.|


#### Enumerated Values


|Parameter|Value|
|---|---|
|market|btcusd|
|market|xrpusd|
|market|btcxrp|
|order_by|asc|
|order_by|desc|


<h3 id="getV2Trades-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get recent trades on market, each trade is included only once. Trades are sorted in reverse creation order.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


## getV2TradesMy


<a id="opIdgetV2TradesMy"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/trades/my?market=btcusd


```


```http
GET http://localhost:8000/api/v2/trades/my?market=btcusd HTTP/1.1
Host: localhost:8000


```


```javascript


$.ajax({
  url: 'http://localhost:8000/api/v2/trades/my',
  method: 'get',
  data: '?market=btcusd',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('http://localhost:8000/api/v2/trades/my?market=btcusd',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'http://localhost:8000/api/v2/trades/my',
  params: {
  'market' => 'string'
}


p JSON.parse(result)


```


```python
import requests


r = requests.get('http://localhost:8000/api/v2/trades/my', params={
  'market': 'btcusd'
)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/trades/my?market=btcusd");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /trades/my`


*Get your executed trades. Trades are sorted in reverse creation order.*


Get your executed trades. Trades are sorted in reverse creation order.


<h3 id="getV2TradesMy-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|market|query|string|true|Unique market id. It's always in the form of xxxyyy, where xxx is the base currency code, yyy is the quote currency code, e.g. 'btcusd'. All available markets can be found at /api/markets.|
|limit|query|integer(int32)|false|Limit the number of returned trades. Default to 50.|
|timestamp|query|integer(int32)|false|An integer represents the seconds elapsed since Unix epoch. If set, only trades executed before the time will be returned.|
|from|query|integer(int32)|false|Trade id. If set, only trades created after the trade will be returned.|
|to|query|integer(int32)|false|Trade id. If set, only trades created before the trade will be returned.|
|order_by|query|string|false|If set, returned trades will be sorted in specific order, default to 'desc'.|


#### Enumerated Values


|Parameter|Value|
|---|---|
|market|btcusd|
|market|xrpusd|
|market|btcxrp|
|order_by|asc|
|order_by|desc|


<h3 id="getV2TradesMy-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get your executed trades. Trades are sorted in reverse creation order.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


<h1 id="Peatio-SDK-k">k</h1>


Operations about k


## getV2K


<a id="opIdgetV2K"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/k?market=btcusd


```


```http
GET http://localhost:8000/api/v2/k?market=btcusd HTTP/1.1
Host: localhost:8000


```


```javascript


$.ajax({
  url: 'http://localhost:8000/api/v2/k',
  method: 'get',
  data: '?market=btcusd',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('http://localhost:8000/api/v2/k?market=btcusd',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'http://localhost:8000/api/v2/k',
  params: {
  'market' => 'string'
}


p JSON.parse(result)


```


```python
import requests


r = requests.get('http://localhost:8000/api/v2/k', params={
  'market': 'btcusd'
)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/k?market=btcusd");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /k`


*Get OHLC(k line) of specific market.*


Get OHLC(k line) of specific market.


<h3 id="getV2K-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|market|query|string|true|Unique market id. It's always in the form of xxxyyy, where xxx is the base currency code, yyy is the quote currency code, e.g. 'btcusd'. All available markets can be found at /api/markets.|
|limit|query|integer(int32)|false|Limit the number of returned data points, default to 30.|
|period|query|integer(int32)|false|Time period of K line, default to 1. You can choose between 1, 5, 15, 30, 60, 120, 240, 360, 720, 1440, 4320, 10080|
|timestamp|query|integer(int32)|false|An integer represents the seconds elapsed since Unix epoch. If set, only k-line data after that time will be returned.|


#### Enumerated Values


|Parameter|Value|
|---|---|
|market|btcusd|
|market|xrpusd|
|market|btcxrp|
|period|1|
|period|5|
|period|15|
|period|30|
|period|60|
|period|120|
|period|240|
|period|360|
|period|720|
|period|1440|
|period|4320|
|period|10080|


<h3 id="getV2K-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get OHLC(k line) of specific market.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


<h1 id="Peatio-SDK-kWithPendingTrades">kWithPendingTrades</h1>


Operations about k with pending trades


## getV2KWithPendingTrades


<a id="opIdgetV2KWithPendingTrades"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/k_with_pending_trades?market=btcusd&trade_id=0


```


```http
GET http://localhost:8000/api/v2/k_with_pending_trades?market=btcusd&trade_id=0 HTTP/1.1
Host: localhost:8000


```


```javascript


$.ajax({
  url: 'http://localhost:8000/api/v2/k_with_pending_trades',
  method: 'get',
  data: '?market=btcusd&trade_id=0',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('http://localhost:8000/api/v2/k_with_pending_trades?market=btcusd&trade_id=0',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'http://localhost:8000/api/v2/k_with_pending_trades',
  params: {
  'market' => 'string',
'trade_id' => 'integer(int32)'
}


p JSON.parse(result)


```


```python
import requests


r = requests.get('http://localhost:8000/api/v2/k_with_pending_trades', params={
  'market': 'btcusd',  'trade_id': '0'
)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/k_with_pending_trades?market=btcusd&trade_id=0");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /k_with_pending_trades`


*Get K data with pending trades, which are the trades not included in K data yet, because there's delay between trade generated and processed by K data generator.*


Get K data with pending trades, which are the trades not included in K data yet, because there's delay between trade generated and processed by K data generator.


<h3 id="getV2KWithPendingTrades-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|market|query|string|true|Unique market id. It's always in the form of xxxyyy, where xxx is the base currency code, yyy is the quote currency code, e.g. 'btcusd'. All available markets can be found at /api/markets.|
|trade_id|query|integer(int32)|true|The trade id of the first trade you received.|
|limit|query|integer(int32)|false|Limit the number of returned data points, default to 30.|
|period|query|integer(int32)|false|Time period of K line, default to 1. You can choose between 1, 5, 15, 30, 60, 120, 240, 360, 720, 1440, 4320, 10080|
|timestamp|query|integer(int32)|false|An integer represents the seconds elapsed since Unix epoch. If set, only k-line data after that time will be returned.|


#### Enumerated Values


|Parameter|Value|
|---|---|
|market|btcusd|
|market|xrpusd|
|market|btcxrp|
|period|1|
|period|5|
|period|15|
|period|30|
|period|60|
|period|120|
|period|240|
|period|360|
|period|720|
|period|1440|
|period|4320|
|period|10080|


<h3 id="getV2KWithPendingTrades-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get K data with pending trades, which are the trades not included in K data yet, because there's delay between trade generated and processed by K data generator.|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwt ( Scopes: write:peatio read:peatio )
</aside>


<h1 id="Peatio-SDK-timestamp">timestamp</h1>


Operations about timestamps


## timestamp


<a id="opIdtimestamp"></a>


> Code samples


```shell
# You can also use wget
curl -X GET http://localhost:8000/api/v2/timestamp \
  -H 'Accept: application/json'


```


```http
GET http://localhost:8000/api/v2/timestamp HTTP/1.1
Host: localhost:8000


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: 'http://localhost:8000/api/v2/timestamp',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('http://localhost:8000/api/v2/timestamp',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get 'http://localhost:8000/api/v2/timestamp',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('http://localhost:8000/api/v2/timestamp', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("http://localhost:8000/api/v2/timestamp");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /timestamp`


*Get server current time, in seconds since Unix epoch.*


Get server current time, in seconds since Unix epoch.


> Example responses


```json
0
```


<h3 id="timestamp-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get server current time, in seconds since Unix epoch.|integer|


<aside class="success">
This operation does not require authentication
</aside>


# Schemas


<h2 id="tocSaccount">Account</h2>


<a id="schemaaccount"></a>


```json
{
  "currency": "usd",
  "balance": 0,
  "locked": 0
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|currency|string|false|No description|
|balance|number|false|No description|
|locked|number|false|No description|


#### Enumerated Values


|Property|Value|
|---|---|
|currency|usd|
|currency|btc|
|currency|xrp|


<h2 id="tocSmember">Member</h2>


<a id="schemamember"></a>


```json
{
  "sn": "PEAUV8S2JNPTIO",
  "name": "John Doe",
  "email": "jdoe@peatio.tech",
  "accounts": [
    {
      "currency": "usd",
      "balance": 0,
      "locked": 0
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|sn|string|false|No description|
|name|string|false|No description|
|email|string|false|No description|
|accounts|[[Account](#schemaaccount)]|false|No description|


<h2 id="tocSmarket">Market</h2>


<a id="schemamarket"></a>


```json
{
  "id": "btcusd",
  "name": "BTC/USD"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|name|string|false|No description|


<h2 id="tocStickerinfo">TickerInfo</h2>


<a id="schematickerinfo"></a>


```json
{
  "at": 1515672822,
  "ticker": {
    "buy": 3000,
    "sell": 3100,
    "low": 3000,
    "high": 3000,
    "last": 3000,
    "vol": 0.11
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|at|integer|false|No description|
|ticker|object|false|No description|
|» buy|number|false|No description|
|» sell|number|false|No description|
|» low|number|false|No description|
|» high|number|false|No description|
|» last|number|false|No description|
|» vol|number|false|No description|


