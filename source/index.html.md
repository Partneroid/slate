---
title: Partneroid Public API
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="partneroid-public-api">Partneroid Public API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Public API to be used by user

Base URLs:

* <a href="https://api.partneroid.com/v1">https://api.partneroid.com/v1</a>

# Authentication

* API Key (PartneroidKeyAuth)
    - Parameter Name: **x-partneroid-token**, in: header. 

<h1 id="partneroid-public-api-default">Default</h1>

## get__partnerships

> Code samples

```shell
# You can also use wget
curl -X GET https://api.partneroid.com/v1/partnerships?url=string \
  -H 'Accept: application/json' \
  -H 'x-partneroid-token: API_KEY'

```

```http
GET https://api.partneroid.com/v1/partnerships?url=string HTTP/1.1
Host: api.partneroid.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'x-partneroid-token':'API_KEY'

};

$.ajax({
  url: 'https://api.partneroid.com/v1/partnerships',
  method: 'get',
  data: '?url=string',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'x-partneroid-token':'API_KEY'

};

fetch('https://api.partneroid.com/v1/partnerships?url=string',
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
  'Accept' => 'application/json',
  'x-partneroid-token' => 'API_KEY'
}

result = RestClient.get 'https://api.partneroid.com/v1/partnerships',
  params: {
  'url' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-partneroid-token': 'API_KEY'
}

r = requests.get('https://api.partneroid.com/v1/partnerships', params={
  'url': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.partneroid.com/v1/partnerships?url=string");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-partneroid-token": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.partneroid.com/v1/partnerships", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /partnerships`

Get partnerships data for a brand

<h3 id="get__partnerships-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|url|query|string|true|Brand URL to fetch partnerships|

> Example responses

> 200 Response

```json
{
  "data": [
    {
      "url": "http://example.com",
      "name": "string",
      "categories": [
        {
          "name": "string"
        }
      ],
      "image": {
        "inline": {
          "uri": "string"
        }
      }
    }
  ]
}
```

<h3 id="get__partnerships-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|4xx|[**Client Error**](https://tools.ietf.org/html/rfc7231#section-6.5)|Bad request|Inline|

<h3 id="get__partnerships-responseschema">Response Schema</h3>

Status Code **200**

*OK*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[object]|true|none|Partnerships data|
|»» url|string(uri)\|null|false|none|Partner website url|
|»» name|string|true|none|Partner name|
|»» categories|[object]|false|none|none|
|»»» name|string|true|none|none|
|»» image|object|false|none|Partner logo|
|»»» inline|object|false|none|Image in base64 format|
|»»»» uri|string|false|none|Image URI|

Status Code **4xx**

*Bad request*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» statusCode|number|true|none|Response status code|
|» error|string|true|none|Response error information|
|» message|string|true|none|Response message|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
PartneroidKeyAuth
</aside>

## get__competitors

> Code samples

```shell
# You can also use wget
curl -X GET https://api.partneroid.com/v1/competitors?url=string \
  -H 'Accept: application/json' \
  -H 'x-partneroid-token: API_KEY'

```

```http
GET https://api.partneroid.com/v1/competitors?url=string HTTP/1.1
Host: api.partneroid.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'x-partneroid-token':'API_KEY'

};

$.ajax({
  url: 'https://api.partneroid.com/v1/competitors',
  method: 'get',
  data: '?url=string',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'x-partneroid-token':'API_KEY'

};

fetch('https://api.partneroid.com/v1/competitors?url=string',
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
  'Accept' => 'application/json',
  'x-partneroid-token' => 'API_KEY'
}

result = RestClient.get 'https://api.partneroid.com/v1/competitors',
  params: {
  'url' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-partneroid-token': 'API_KEY'
}

r = requests.get('https://api.partneroid.com/v1/competitors', params={
  'url': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.partneroid.com/v1/competitors?url=string");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-partneroid-token": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.partneroid.com/v1/competitors", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /competitors`

Get competitors for a brand

<h3 id="get__competitors-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|url|query|string|true|Brand URL to fetch competitors|

> Example responses

> 200 Response

```json
{
  "data": [
    {
      "url": "http://example.com",
      "name": "string",
      "categories": [
        {
          "name": "string"
        }
      ],
      "countries": [
        {
          "name": "string",
          "code": "string"
        }
      ],
      "image": {
        "inline": {
          "uri": "string"
        }
      }
    }
  ]
}
```

<h3 id="get__competitors-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|4xx|[**Client Error**](https://tools.ietf.org/html/rfc7231#section-6.5)|Bad request|Inline|

<h3 id="get__competitors-responseschema">Response Schema</h3>

Status Code **200**

*OK*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[object]|true|none|Competitors data|
|»» url|string(uri)\|null|false|none|Competitor website url|
|»» name|string|true|none|Competitor name|
|»» categories|[object]|false|none|none|
|»»» name|string|true|none|none|
|»» countries|[object]|true|none|Competitor available countries|
|»»» name|string|true|none|Country name|
|»»» code|string|true|none|Country code|
|»» image|object|false|none|Competitor logo|
|»»» inline|object|false|none|Image in base64 format|
|»»»» uri|string|false|none|Image URI|

Status Code **4xx**

*Bad request*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» statusCode|number|true|none|Response status code|
|» error|string|true|none|Response error information|
|» message|string|true|none|Response message|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
PartneroidKeyAuth
</aside>

## get__countries

> Code samples

```shell
# You can also use wget
curl -X GET https://api.partneroid.com/v1/countries \
  -H 'Accept: application/json' \
  -H 'x-partneroid-token: API_KEY'

```

```http
GET https://api.partneroid.com/v1/countries HTTP/1.1
Host: api.partneroid.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'x-partneroid-token':'API_KEY'

};

$.ajax({
  url: 'https://api.partneroid.com/v1/countries',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'x-partneroid-token':'API_KEY'

};

fetch('https://api.partneroid.com/v1/countries',
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
  'Accept' => 'application/json',
  'x-partneroid-token' => 'API_KEY'
}

result = RestClient.get 'https://api.partneroid.com/v1/countries',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-partneroid-token': 'API_KEY'
}

r = requests.get('https://api.partneroid.com/v1/countries', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.partneroid.com/v1/countries");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-partneroid-token": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.partneroid.com/v1/countries", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /countries`

List all supported countries

> Example responses

> 200 Response

```json
{
  "data": [
    {
      "code": "string",
      "name": "string"
    }
  ]
}
```

<h3 id="get__countries-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|Inline|

<h3 id="get__countries-responseschema">Response Schema</h3>

Status Code **200**

*OK*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[object]|true|none|Countries information|
|»» code|string|true|none|Country code|
|»» name|string|true|none|Country name|

Status Code **400**

*Bad request*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» statusCode|number|true|none|Response status code|
|» error|string|true|none|Response error information|
|» message|string|true|none|Response message|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
PartneroidKeyAuth
</aside>

## get__api-usages

> Code samples

```shell
# You can also use wget
curl -X GET https://api.partneroid.com/v1/api-usages \
  -H 'Accept: application/json' \
  -H 'x-partneroid-token: API_KEY'

```

```http
GET https://api.partneroid.com/v1/api-usages HTTP/1.1
Host: api.partneroid.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'x-partneroid-token':'API_KEY'

};

$.ajax({
  url: 'https://api.partneroid.com/v1/api-usages',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'x-partneroid-token':'API_KEY'

};

fetch('https://api.partneroid.com/v1/api-usages',
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
  'Accept' => 'application/json',
  'x-partneroid-token' => 'API_KEY'
}

result = RestClient.get 'https://api.partneroid.com/v1/api-usages',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-partneroid-token': 'API_KEY'
}

r = requests.get('https://api.partneroid.com/v1/api-usages', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.partneroid.com/v1/api-usages");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-partneroid-token": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.partneroid.com/v1/api-usages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api-usages`

Get API usages bucket by date

> Example responses

> 200 Response

```json
{
  "data": [
    {
      "value": 0,
      "interval": {
        "startTime": 0,
        "endTime": 0
      }
    }
  ]
}
```

<h3 id="get__api-usages-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|Inline|

<h3 id="get__api-usages-responseschema">Response Schema</h3>

Status Code **200**

*OK*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[object]|true|none|Api|
|»» value|number|false|none|none|
|»» interval|object|false|none|none|
|»»» startTime|number|false|none|none|
|»»» endTime|number|false|none|none|

Status Code **400**

*Bad request*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» statusCode|number|true|none|Response status code|
|» error|string|true|none|Response error information|
|» message|string|true|none|Response message|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
PartneroidKeyAuth
</aside>

