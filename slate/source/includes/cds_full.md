<h1 id="consumer-data-standards">Consumer Data Standards v1</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

API sets created by the Australian  Consumer Data Standards to meet the needs of the Consumer Data Right

Base URLs:

* <a href="https://data.provider.com.au/cds-au/v1">https://data.provider.com.au/cds-au/v1</a>

License: <a href="https://opensource.org/licenses/MIT">MIT Licence</a>

<h1 id="consumer-data-standards-accounts">Accounts</h1>

## G-BA

<a id="opIdG-BA"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://data.provider.com.au/cds-au/v1/banking/accounts \
  -H 'Accept: application/json'

```

```http
GET https://data.provider.com.au/cds-au/v1/banking/accounts HTTP/1.1
Host: data.provider.com.au
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/accounts',
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
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/accounts',
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

result = RestClient.get 'https://data.provider.com.au/cds-au/v1/banking/accounts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://data.provider.com.au/cds-au/v1/banking/accounts', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/accounts");
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

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://data.provider.com.au/cds-au/v1/banking/accounts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banking/accounts`

*Get Accounts*

Obtain a list of accounts

<h3 id="g-ba-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|open-status|query|string|false|Used to filter results according to open/closed status. Values can be OPEN, CLOSED or ALL. If absent then ALL is assumed|
|product-category|query|string|false|Used to filter results on the productCategory field applicable to accounts. Any one of the valid values for this field can be supplied. If absent then all accounts returned.|
|page|query|integer|false|Page of results to request (standard pagination)|
|page-size|query|integer|false|Page size to request. Default is 25 (standard pagination)|
|start-time|query|string|false|Constrain the transaction history request to transactions with effective time at or after this date/time. If absent defaults to today. Format is aligned to DateTimeString common type|
|end-time|query|string|false|Constrain the transaction history request to transactions with effective time at or before this date/time. If absent defaults to start-time plus 100 days. Format is aligned to DateTimeString common type|
|min-amount|query|number|false|Filter transactions to only transactions with amounts higher or equal to than this amount|
|max-amount|query|number|false|Filter transactions to only transactions with amounts less than or equal to than this amount|
|text|query|string|false|Filter transactions to only transactions where this string value is found as a substring of either the reference or description fields. Format is arbitrary ASCII string|

> Example responses

> 200 Response

```json
{
  "data": {
    "accounts": [
      {
        "accountid": "",
        "displayName": "",
        "nickname": "",
        "maskedNumber": "",
        "productCategory": "",
        "providerType": "",
        "balance$type": "",
        "deposits": {
          "currentBalance": {
            "amount": "",
            "currency": ""
          },
          "availableBalance": {
            "amount": "",
            "currency": ""
          }
        },
        "lending": {
          "accountBalance": {
            "amount": "",
            "currency": ""
          },
          "availableBalance": {
            "amount": "",
            "currency": ""
          },
          "creditLimit": {
            "amount": "",
            "currency": ""
          },
          "amortisedLimit": {
            "amount": "",
            "currency": ""
          }
        },
        "purses": [
          {
            "amount": "",
            "currency": ""
          }
        ]
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}
```

<h3 id="g-ba-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Banking_Accounts](#schema200_get_banking_accounts)|

<aside class="success">
This operation does not require authentication
</aside>

## G-BA-D

<a id="opIdG-BA-D"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId} \
  -H 'Accept: application/json'

```

```http
GET https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId} HTTP/1.1
Host: data.provider.com.au
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}',
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
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}',
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

result = RestClient.get 'https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}");
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

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banking/accounts/{accountId}`

*Get Account Detail*

Obtain detailed information on a single account

<h3 id="g-ba-d-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|accountId|path|string|true|A tokenised identifier for the account which is unique but not shareable|

> Example responses

> 200 Response

```json
{
  "data": {
    "accountid": "",
    "displayName": "",
    "nickname": "",
    "maskedNumber": "",
    "productCategory": "",
    "providerType": "",
    "balance$type": "",
    "deposits": {
      "currentBalance": {
        "amount": "",
        "currency": ""
      },
      "availableBalance": {
        "amount": "",
        "currency": ""
      }
    },
    "lending": {
      "accountBalance": {
        "amount": "",
        "currency": ""
      },
      "availableBalance": {
        "amount": "",
        "currency": ""
      },
      "creditLimit": {
        "amount": "",
        "currency": ""
      },
      "amortisedLimit": {
        "amount": "",
        "currency": ""
      }
    },
    "purses": [
      {
        "amount": "",
        "currency": ""
      }
    ],
    "bundleName": "",
    "specificAccount$type": "",
    "termDeposit": {
      "lodgementDate": "",
      "maturityDate": "",
      "maturityAmount": "",
      "maturityCurrency": "",
      "maturityInstructions": ""
    },
    "creditCard": {
      "minPaymentAmount": "",
      "paymentDueAmount": "",
      "paymentCurrency": "",
      "paymentDueDate": ""
    },
    "loan": {
      "originalStartDate": "",
      "originalLoanAmount": "",
      "originalLoanCurrency": "",
      "loanEndDate": "",
      "nextInstalmentDate": "",
      "minInstalmentAmount": "",
      "minInstalmentCurrency": "",
      "maxRedraw": "",
      "maxRedrawCurrency": "",
      "minRedraw": "",
      "minRedrawCurrency": "",
      "offsetAccountEnabled": "",
      "offsetAccountIds": [
        "string"
      ],
      "repaymentType": "",
      "repaymentFrequency": ""
    },
    "features": [
      {
        "featureType": "",
        "additionalValue": ""
      }
    ],
    "fees": [
      {
        "name": "",
        "feeType": "",
        "amount": "",
        "balanceRate": "",
        "transactionRate": "",
        "currency": "",
        "additionalValue": "",
        "additionalInfo": "",
        "additionalInfoUri": "",
        "discounts": [
          {
            "description": "",
            "discountType": "",
            "amount": "",
            "additionalValue": ""
          }
        ]
      }
    ],
    "depositRates": [
      {
        "depositRateType": "",
        "rate": "",
        "additionalValue": "",
        "additionalInfo": "",
        "additionalInfoUri": ""
      }
    ],
    "lendingRates": [
      {
        "lendingRateType": "",
        "rate": "",
        "additionalValue": "",
        "additionalInfo": "",
        "additionalInfoUri": ""
      }
    ],
    "address": {
      "address$type": "",
      "simple": {
        "mailingName": "",
        "addressLine1": "",
        "addressLine2": "",
        "addressLine3": "",
        "postcode": "",
        "city": "",
        "state": "",
        "country": ""
      },
      "paf": {}
    }
  },
  "links": {
    "self": ""
  },
  "meta": {}
}
```

<h3 id="g-ba-d-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Banking_Account](#schema200_get_banking_account)|

<aside class="success">
This operation does not require authentication
</aside>

## G-BAB

<a id="opIdG-BAB"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://data.provider.com.au/cds-au/v1/banking/accounts/balances \
  -H 'Accept: application/json'

```

```http
GET https://data.provider.com.au/cds-au/v1/banking/accounts/balances HTTP/1.1
Host: data.provider.com.au
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/accounts/balances',
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
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/accounts/balances',
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

result = RestClient.get 'https://data.provider.com.au/cds-au/v1/banking/accounts/balances',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://data.provider.com.au/cds-au/v1/banking/accounts/balances', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/accounts/balances");
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

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://data.provider.com.au/cds-au/v1/banking/accounts/balances", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banking/accounts/balances`

*Get Bulk Balances*

Obtain balances for multiple, filtered accounts

<h3 id="g-bab-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|product-category|query|string|false|Used to filter results on the productCategory field applicable to accounts. Any one of the valid values for this field can be supplied. If absent then all accounts returned|
|page|query|integer|false|Page of results to request (standard pagination)|
|page-size|query|integer|false|Page size to request. Default is 25 (standard pagination)|

> Example responses

> 200 Response

```json
{
  "data": {
    "balances": [
      {
        "accountid": "",
        "balance$type": "",
        "deposits": {
          "currentBalance": {
            "amount": "",
            "currency": ""
          },
          "availableBalance": {
            "amount": "",
            "currency": ""
          }
        },
        "lending": {
          "accountBalance": {
            "amount": "",
            "currency": ""
          },
          "availableBalance": {
            "amount": "",
            "currency": ""
          },
          "creditLimit": {
            "amount": "",
            "currency": ""
          },
          "amortisedLimit": {
            "amount": "",
            "currency": ""
          }
        },
        "purses": [
          {
            "amount": "",
            "currency": ""
          }
        ]
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}
```

<h3 id="g-bab-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|resource listing the financial balances for the account|[200_GET_Banking_Accounts_Balances](#schema200_get_banking_accounts_balances)|

<aside class="success">
This operation does not require authentication
</aside>

## P-BAB-Q

<a id="opIdP-BAB-Q"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://data.provider.com.au/cds-au/v1/banking/accounts/balances \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://data.provider.com.au/cds-au/v1/banking/accounts/balances HTTP/1.1
Host: data.provider.com.au
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/accounts/balances',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "data": {
    "accountIds": [
      "string"
    ]
  },
  "meta": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/accounts/balances',
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
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://data.provider.com.au/cds-au/v1/banking/accounts/balances',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://data.provider.com.au/cds-au/v1/banking/accounts/balances', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/accounts/balances");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://data.provider.com.au/cds-au/v1/banking/accounts/balances", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /banking/accounts/balances`

*Get Balances For Specific Accounts*

Obtain balances for a specified list of accounts

> Body parameter

```json
{
  "data": {
    "accountIds": [
      "string"
    ]
  },
  "meta": {}
}
```

<h3 id="p-bab-q-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AccountIds_Request](#schemaaccountids_request)|true|The list of account IDs to obtain information for|

> Example responses

> 200 Response

```json
{
  "data": {
    "balances": [
      {
        "accountid": "",
        "balance$type": "",
        "deposits": {
          "currentBalance": {
            "amount": "",
            "currency": ""
          },
          "availableBalance": {
            "amount": "",
            "currency": ""
          }
        },
        "lending": {
          "accountBalance": {
            "amount": "",
            "currency": ""
          },
          "availableBalance": {
            "amount": "",
            "currency": ""
          },
          "creditLimit": {
            "amount": "",
            "currency": ""
          },
          "amortisedLimit": {
            "amount": "",
            "currency": ""
          }
        },
        "purses": [
          {
            "amount": "",
            "currency": ""
          }
        ]
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}
```

<h3 id="p-bab-q-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Banking_Accounts_Balances](#schema200_get_banking_accounts_balances)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|The request was well formed but was unable to be processed due to business logic specific to the request|[422_Errors](#schema422_errors)|

<aside class="success">
This operation does not require authentication
</aside>

## G-BA-D-T

<a id="opIdG-BA-D-T"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions \
  -H 'Accept: application/json'

```

```http
GET https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions HTTP/1.1
Host: data.provider.com.au
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions',
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
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions',
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

result = RestClient.get 'https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions");
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

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banking/accounts/{accountId}/transactions`

*Get Transactions For Account*

Obtain transactions for a specific account

<h3 id="g-ba-d-t-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|accountId|path|string|true|ID of the account to get transactions for.  Must have previously been returned by one of the account list end points.|
|start-time|query|string|false|Constrain the transaction history request to transactions with effective time at or after this date/time. If absent defaults to today. Format is aligned to DateTimeString common type|
|end-time|query|string|false|Constrain the transaction history request to transactions with effective time at or before this date/time. If absent defaults to start-time plus 100 days. Format is aligned to DateTimeString common type|
|min-amount|query|number|false|Filter transactions to only transactions with amounts higher or equal to this amount|
|max-amount|query|number|false|Filter transactions to only transactions with amounts less than or equal to than this amount|
|text|query|string|false|Filter transactions to only transactions where this string value is found as a substring of either the reference or description fields. Format is arbitrary ASCII string|
|page|query|integer|false|Page of results to request (standard pagination)|
|page-size|query|integer|false|Page size to request. Default is 25 (standard pagination)|

> Example responses

> 200 Response

```json
{
  "data": {
    "accountId": "",
    "displayName": "",
    "nickname": "",
    "transactions": [
      {
        "transactionid": "",
        "isDetailAvailable": "",
        "status": "",
        "description": "",
        "postDateTime": "",
        "executionDateTime": "",
        "amount": "",
        "currency": "",
        "reference": ""
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}
```

<h3 id="g-ba-d-t-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Banking_Account_Transactions](#schema200_get_banking_account_transactions)|

<aside class="success">
This operation does not require authentication
</aside>

## G-BA-D-T-D

<a id="opIdG-BA-D-T-D"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions/{transactionId} \
  -H 'Accept: application/json'

```

```http
GET https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions/{transactionId} HTTP/1.1
Host: data.provider.com.au
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions/{transactionId}',
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
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions/{transactionId}',
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

result = RestClient.get 'https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions/{transactionId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions/{transactionId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions/{transactionId}");
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

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/transactions/{transactionId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banking/accounts/{accountId}/transactions/{transactionId}`

*Get Transaction Detail*

Obtain detailed information on a transaction for a specific account

<h3 id="g-ba-d-t-d-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|accountId|path|string|true|The account id token that is used to uniquely represent the account|
|transactionId|path|string|true|The unique identifier for the specific transaction for which details are being requested|

> Example responses

> 200 Response

```json
{
  "data": {
    "accountId": "",
    "displayName": "",
    "nickname": "",
    "transaction": [
      {
        "transactionid": "",
        "status": "",
        "description": "",
        "postDateTime": "",
        "executionDateTime": "",
        "amount": "",
        "currency": "",
        "reference": "",
        "extendedData": {
          "payer": "",
          "payee": "",
          "extension$type": "",
          "extendedDescription": "",
          "service": ""
        }
      }
    ]
  },
  "links": {
    "self": ""
  },
  "meta": {}
}
```

<h3 id="g-ba-d-t-d-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Banking_Transactions_Detail](#schema200_get_banking_transactions_detail)|

<aside class="success">
This operation does not require authentication
</aside>

## G-BAT

<a id="opIdG-BAT"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://data.provider.com.au/cds-au/v1/banking/accounts/transactions \
  -H 'Accept: application/json'

```

```http
GET https://data.provider.com.au/cds-au/v1/banking/accounts/transactions HTTP/1.1
Host: data.provider.com.au
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/accounts/transactions',
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
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/accounts/transactions',
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

result = RestClient.get 'https://data.provider.com.au/cds-au/v1/banking/accounts/transactions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://data.provider.com.au/cds-au/v1/banking/accounts/transactions', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/accounts/transactions");
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

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://data.provider.com.au/cds-au/v1/banking/accounts/transactions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banking/accounts/transactions`

*Get Transactions For Account*

Obtain transactions for multiple, filtered accounts

<h3 id="g-bat-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|product-category|query|string|false|Used to filter results on the productCategory field applicable to accounts. Any one of the valid values for this field can be supplied. If absent then all accounts returned|
|start-time|query|string|false|Constrain the transaction history request to transactions with effective time at or after this date/time. If absent defaults to today. Format is aligned to DateTimeString common type|
|end-time|query|string|false|Constrain the transaction history request to transactions with effective time at or before this date/time. If absent defaults to start-time plus 100 days. Format is aligned to DateTimeString common type|
|min-amount|query|number|false|Filter transactions to only transactions with amounts higher or equal to this amount|
|max-amount|query|string|false|Filter transactions to only transactions with amounts less than or equal to this amount|
|text|query|string|false|Filter transactions to only transactions where this string value is found as a substring of either the reference or description fields. Format is arbitrary ASCII string|
|page|query|integer|false|Page of results to request (standard pagination)|
|page-size|query|integer|false|Page size to request. Default is 25 (standard pagination)|

> Example responses

> 200 Response

```json
{
  "data": {
    "transactions": [
      {
        "accountId": "",
        "transactionid": "",
        "isDetailAvailable": "",
        "status": "",
        "description": "",
        "postDateTime": "",
        "executionDateTime": "",
        "amount": "",
        "currency": "",
        "reference": ""
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}
```

<h3 id="g-bat-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Banking_Bulk_Transactions](#schema200_get_banking_bulk_transactions)|

<aside class="success">
This operation does not require authentication
</aside>

## P-BAT-Q

<a id="opIdP-BAT-Q"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://data.provider.com.au/cds-au/v1/banking/accounts/transactions \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://data.provider.com.au/cds-au/v1/banking/accounts/transactions HTTP/1.1
Host: data.provider.com.au
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/accounts/transactions',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "data": {
    "accountIds": [
      "string"
    ]
  },
  "meta": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/accounts/transactions',
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
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://data.provider.com.au/cds-au/v1/banking/accounts/transactions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://data.provider.com.au/cds-au/v1/banking/accounts/transactions', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/accounts/transactions");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://data.provider.com.au/cds-au/v1/banking/accounts/transactions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /banking/accounts/transactions`

*Get Transactions For Specific Accounts*

Obtain transactions for a specified list of transactions.

> Body parameter

```json
{
  "data": {
    "accountIds": [
      "string"
    ]
  },
  "meta": {}
}
```

<h3 id="p-bat-q-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|start-time|query|string|false|Constrain the transaction history request to transactions with effective time at or after this date/time. If absent defaults to today. Format is aligned to DateTimeString common type|
|end-time|query|string|false|Constrain the transaction history request to transactions with effective time at or before this date/time. If absent defaults to start-time plus 100 days. Format is aligned to DateTimeString common type|
|min-amount|query|number|false|Filter transactions to only transactions with amounts higher or equal to this amount|
|max-amount|query|number|false|Filter transactions to only transactions with amounts less than or equal to than this amount|
|text|query|string|false|Filter transactions to only transactions where this string value is found as a substring of either the reference or description fields. Format is arbitrary ASCII string|
|page|query|integer|false|Page of results to request (standard pagination)|
|page-size|query|integer|false|Page size to request. Default is 25 (standard pagination)|
|body|body|[AccountIds_Request](#schemaaccountids_request)|true|The list of account IDs to obtain information for|

> Example responses

> 200 Response

```json
{
  "data": {
    "transactions": [
      {
        "accountId": "",
        "transactionid": "",
        "isDetailAvailable": "",
        "status": "",
        "description": "",
        "postDateTime": "",
        "executionDateTime": "",
        "amount": "",
        "currency": "",
        "reference": ""
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}
```

<h3 id="p-bat-q-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Banking_Bulk_Transactions](#schema200_get_banking_bulk_transactions)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|The request was well formed but was unable to be processed due to business logic specific to the request|[422_Errors](#schema422_errors)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="consumer-data-standards-direct-debits">Direct Debits</h1>

## G-BAD-D

<a id="opIdG-BAD-D"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/direct-debits \
  -H 'Accept: application/json'

```

```http
GET https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/direct-debits HTTP/1.1
Host: data.provider.com.au
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/direct-debits',
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
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/direct-debits',
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

result = RestClient.get 'https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/direct-debits',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/direct-debits', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/direct-debits");
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

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://data.provider.com.au/cds-au/v1/banking/accounts/{accountId}/direct-debits", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banking/accounts/{accountId}/direct-debits`

*Get Direct Debits For Account*

Obtain direct debit authorisations for a specific account

<h3 id="g-bad-d-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|accountId|path|string|true|ID of the account to get direct debit authorisations for.  Must have previously been returned by one of the account list end points.|
|page|query|string|false|Page of results to request (standard pagination)|
|page-size|query|string|false|Page size to request.  Default is 25 (standard pagination)|

> Example responses

> 200 Response

```json
{
  "data": {
    "directDebitAuthorisations": [
      {
        "accountId": "",
        "authorisedEntity": {
          "name": "",
          "financialInstitution": "",
          "abn": "",
          "acn": ""
        },
        "lastDebitDateTime": "",
        "lastDebitAmount": ""
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}
```

<h3 id="g-bad-d-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Banking_Direct-Debits](#schema200_get_banking_direct-debits)|

<aside class="success">
This operation does not require authentication
</aside>

## G-BAD

<a id="opIdG-BAD"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits \
  -H 'Accept: application/json'

```

```http
GET https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits HTTP/1.1
Host: data.provider.com.au
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits',
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
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits',
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

result = RestClient.get 'https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits");
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

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banking/accounts/direct-debits`

*Get Bulk Direct Debits*

Obtain direct debit authorisations for multiple, filtered accounts

<h3 id="g-bad-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|Page of results to request (standard pagination)|
|page-size|query|integer|false|Page size to request.  Default is 25 (standard pagination)|
|product-category|query|string|false|Used to filter results on the productCategory field applicable to accounts. Any one of the valid values for this field can be supplied. If absent then all accounts returned|

> Example responses

> 200 Response

```json
{
  "data": {
    "directDebitAuthorisations": [
      {
        "accountId": "",
        "authorisedEntity": {
          "name": "",
          "financialInstitution": "",
          "abn": "",
          "acn": ""
        },
        "lastDebitDateTime": "",
        "lastDebitAmount": ""
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}
```

<h3 id="g-bad-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Banking_Direct-Debits](#schema200_get_banking_direct-debits)|

<aside class="success">
This operation does not require authentication
</aside>

## P-BAD-Q

<a id="opIdP-BAD-Q"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits HTTP/1.1
Host: data.provider.com.au
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "data": {
    "accountIds": [
      "string"
    ]
  },
  "meta": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits',
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
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://data.provider.com.au/cds-au/v1/banking/accounts/direct-debits", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /banking/accounts/direct-debits`

*Get Direct Debits For Specific Accounts*

Obtain direct debit authorisations for a specified list of accounts

> Body parameter

```json
{
  "data": {
    "accountIds": [
      "string"
    ]
  },
  "meta": {}
}
```

<h3 id="p-bad-q-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AccountIds_Request](#schemaaccountids_request)|true|The list of account IDs to obtain information for|

> Example responses

> 200 Response

```json
{
  "data": {
    "directDebitAuthorisations": [
      {
        "accountId": "",
        "authorisedEntity": {
          "name": "",
          "financialInstitution": "",
          "abn": "",
          "acn": ""
        },
        "lastDebitDateTime": "",
        "lastDebitAmount": ""
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}
```

<h3 id="p-bad-q-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Banking_Direct-Debits](#schema200_get_banking_direct-debits)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|The request was well formed but was unable to be processed due to business logic specific to the request|[422_Errors](#schema422_errors)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="consumer-data-standards-payees">Payees</h1>

## G-BPY

<a id="opIdG-BPY"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://data.provider.com.au/cds-au/v1/banking/payees \
  -H 'Accept: application/json'

```

```http
GET https://data.provider.com.au/cds-au/v1/banking/payees HTTP/1.1
Host: data.provider.com.au
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/payees',
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
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/payees',
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

result = RestClient.get 'https://data.provider.com.au/cds-au/v1/banking/payees',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://data.provider.com.au/cds-au/v1/banking/payees', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/payees");
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

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://data.provider.com.au/cds-au/v1/banking/payees", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banking/payees`

*Get Payees*

Obtain a list of pre-registered payees

<h3 id="g-bpy-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|type|query|string|false|Filter on the payee type field.  In addition to normal type field values, ALL can be specified to retrieve all payees.  If absent the assumed value is ALL|
|page|query|integer|false|Page of results to request (standard pagination)|
|page-size|query|integer|false|Page size to request. Default is 25 (standard pagination)|

> Example responses

> 200 Response

```json
{
  "data": {
    "payees": [
      {
        "payeeId": "",
        "nickname": "",
        "description": "",
        "type": ""
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}
```

<h3 id="g-bpy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Banking_Payees](#schema200_get_banking_payees)|

<aside class="success">
This operation does not require authentication
</aside>

## G-BPY-D

<a id="opIdG-BPY-D"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://data.provider.com.au/cds-au/v1/banking/payees/{payeeId} \
  -H 'Accept: application/json'

```

```http
GET https://data.provider.com.au/cds-au/v1/banking/payees/{payeeId} HTTP/1.1
Host: data.provider.com.au
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/payees/{payeeId}',
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
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/payees/{payeeId}',
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

result = RestClient.get 'https://data.provider.com.au/cds-au/v1/banking/payees/{payeeId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://data.provider.com.au/cds-au/v1/banking/payees/{payeeId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/payees/{payeeId}");
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

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://data.provider.com.au/cds-au/v1/banking/payees/{payeeId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banking/payees/{payeeId}`

*Get Payee Detail*

Obtain detailed information on a single payee

<h3 id="g-bpy-d-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|payeeId|path|string|true|The ID used to locate the details of a particular payee|

> Example responses

> 200 Response

```json
{
  "data": {
    "payeeId": "",
    "nickname": "",
    "description": "",
    "type": "",
    "payee$type": "",
    "domestic": {
      "payeeAccount$type": "",
      "account": {
        "accountName": "",
        "bsb": "",
        "accountNumber": ""
      },
      "card": {
        "cardNumber": ""
      },
      "payId": {
        "name": "",
        "identifier": "",
        "type": ""
      }
    },
    "biller": {
      "billerCode": "",
      "crn": "",
      "billerName": ""
    },
    "international": {
      "beneficiaryDetails": {
        "name": "",
        "country": "",
        "message": ""
      },
      "bankDetails": {
        "country": "",
        "accountNumber": "",
        "bankAddress": {
          "name": "",
          "address": ""
        },
        "beneficiaryBankBIC": "",
        "fedWireNumber": "",
        "sortCode": "",
        "chipNumber": "",
        "routingNumber": ""
      }
    }
  },
  "links": {
    "self": ""
  },
  "meta": {}
}
```

<h3 id="g-bpy-d-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Banking_Payee_Details](#schema200_get_banking_payee_details)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="consumer-data-standards-products">Products</h1>

## G-BP

<a id="opIdG-BP"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://data.provider.com.au/cds-au/v1/banking/products \
  -H 'Accept: application/json'

```

```http
GET https://data.provider.com.au/cds-au/v1/banking/products HTTP/1.1
Host: data.provider.com.au
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/products',
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
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/products',
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

result = RestClient.get 'https://data.provider.com.au/cds-au/v1/banking/products',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://data.provider.com.au/cds-au/v1/banking/products', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/products");
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

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://data.provider.com.au/cds-au/v1/banking/products", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banking/products`

*Get Products*

Obtain a list of products that are currently openly offered to the market

<h3 id="g-bp-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|product-category|query|string|false|Used to filter results on the productCategory field. Any one of the valid values for this field can be supplied. If absent then all products returned|
|effective|query|boolean|false|If true then only include products that are effective right now and exclude products that may be available at a future time. If false only include products effective in the future. If absent defaults to include all products|
|updated-since|query|string|false|Only include products that have been updated after the specified date and time. If absent defaults to include all products|
|brand|query|string|false|Filter results based on a specific brand|
|page|query|integer|false|Page of results to request (standard pagination)|
|page-size|query|integer|false|Page size to request. Default is 25 (standard pagination)|

> Example responses

> 200 Response

```json
{
  "data": {
    "products": [
      {
        "productId": "",
        "effectiveFrom": "",
        "effectiveTo": "",
        "lastUpdated": "",
        "productCategory": "",
        "name": "",
        "description": "",
        "brand": "",
        "brandName": "",
        "applicationUri": "",
        "isNegotiable": "",
        "additionalInformation": {
          "overviewUri": "",
          "termsUri": "",
          "eligibilityUri": "",
          "feesAndPricingUri": "",
          "bundleUri": ""
        }
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}
```

<h3 id="g-bp-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Banking_Products](#schema200_get_banking_products)|

<aside class="success">
This operation does not require authentication
</aside>

## G-BP-D

<a id="opIdG-BP-D"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://data.provider.com.au/cds-au/v1/banking/products/{productId} \
  -H 'Accept: application/json'

```

```http
GET https://data.provider.com.au/cds-au/v1/banking/products/{productId} HTTP/1.1
Host: data.provider.com.au
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/banking/products/{productId}',
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
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/banking/products/{productId}',
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

result = RestClient.get 'https://data.provider.com.au/cds-au/v1/banking/products/{productId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://data.provider.com.au/cds-au/v1/banking/products/{productId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/banking/products/{productId}");
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

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://data.provider.com.au/cds-au/v1/banking/products/{productId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banking/products/{productId}`

*Get Product Detail*

Obtain detailed information on a single product offered openly to the market

<h3 id="g-bp-d-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|productId|path|string|true|ID of the specific product requested|

> Example responses

> 200 Response

```json
{
  "data": {
    "productId": "",
    "effectiveFrom": "",
    "effectiveTo": "",
    "lastUpdated": "",
    "productCategory": "",
    "name": "",
    "description": "",
    "brand": "",
    "brandName": "",
    "applicationUri": "",
    "isNegotiable": "",
    "additionalInformation": {
      "overviewUri": "",
      "termsUri": "",
      "eligibilityUri": "",
      "feesAndPricingUri": "",
      "bundleUri": ""
    },
    "bundles": [
      {
        "name": "",
        "description": "",
        "additionalInfoUri": "",
        "productIds": [
          "string"
        ]
      }
    ],
    "features": [
      {
        "featureType": "",
        "additionalValue": ""
      }
    ],
    "constraints": [
      {
        "constraintType": "",
        "additionalValue": ""
      }
    ],
    "eligibility": [
      {
        "eligibilityType": "",
        "additionalValue": "",
        "additionalInfo": "",
        "additionalInfoUri": ""
      }
    ],
    "fees": [
      {
        "name": "",
        "feeType": "",
        "amount": "",
        "balanceRate": "",
        "transactionRate": "",
        "currency": "",
        "additionalValue": "",
        "additionalInfo": "",
        "additionalInfoUri": "",
        "discounts": [
          {
            "description": "",
            "discountType": "",
            "amount": "",
            "additionalValue": ""
          }
        ]
      }
    ],
    "depositRates": [
      {
        "depositRateType": "",
        "rate": "",
        "additionalValue": "",
        "additionalInfo": "",
        "additionalInfoUri": ""
      }
    ],
    "lendingRates": [
      {
        "lendingRateType": "",
        "rate": "",
        "additionalValue": "",
        "additionalInfo": "",
        "additionalInfoUri": ""
      }
    ]
  },
  "links": {
    "self": ""
  },
  "meta": {}
}
```

<h3 id="g-bp-d-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Banking_Product](#schema200_get_banking_product)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="consumer-data-standards-customer">Customer</h1>

## G-CC

<a id="opIdG-CC"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://data.provider.com.au/cds-au/v1/common/customer \
  -H 'Accept: application/json'

```

```http
GET https://data.provider.com.au/cds-au/v1/common/customer HTTP/1.1
Host: data.provider.com.au
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/common/customer',
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
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/common/customer',
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

result = RestClient.get 'https://data.provider.com.au/cds-au/v1/common/customer',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://data.provider.com.au/cds-au/v1/common/customer', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/common/customer");
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

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://data.provider.com.au/cds-au/v1/common/customer", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /common/customer`

*Get Customer*

Obtain basic information on the customer that has authorised the current session

> Example responses

> 200 Response

```json
{
  "data": {
    "customer$type": "",
    "person": {
      "lastUpdateTime": "",
      "firstName": "",
      "lastName": "",
      "middleNames": [
        "string"
      ],
      "prefix": "",
      "suffix": "",
      "occupationCode": ""
    },
    "organisation": {
      "lastUpdateTime": "",
      "agentFirstName": "",
      "agentLastName": "",
      "agentRole": "",
      "businessName": "",
      "legalName": "",
      "shortName": "",
      "abn": "",
      "acn": "",
      "isACNCRegistered": "",
      "industryCode": "",
      "organisationType": "",
      "registeredCountry": "",
      "establishmentDate": ""
    }
  },
  "links": {
    "self": ""
  },
  "meta": {}
}
```

<h3 id="g-cc-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Common_Customer](#schema200_get_common_customer)|

<aside class="success">
This operation does not require authentication
</aside>

## G-CCD

<a id="opIdG-CCD"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://data.provider.com.au/cds-au/v1/common/customer/detail \
  -H 'Accept: application/json'

```

```http
GET https://data.provider.com.au/cds-au/v1/common/customer/detail HTTP/1.1
Host: data.provider.com.au
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://data.provider.com.au/cds-au/v1/common/customer/detail',
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
  'Accept':'application/json'

};

fetch('https://data.provider.com.au/cds-au/v1/common/customer/detail',
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

result = RestClient.get 'https://data.provider.com.au/cds-au/v1/common/customer/detail',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://data.provider.com.au/cds-au/v1/common/customer/detail', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://data.provider.com.au/cds-au/v1/common/customer/detail");
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

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://data.provider.com.au/cds-au/v1/common/customer/detail", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /common/customer/detail`

*Get Customer Detail*

Obtain detailed information on the authorised customer within the current session.

> Example responses

> 200 Response

```json
{
  "data": {
    "customer$type": "",
    "person": {
      "lastUpdateTime": "",
      "firstName": "",
      "lastName": "",
      "middleNames": [
        "string"
      ],
      "prefix": "",
      "suffix": "",
      "occupationCode": "",
      "phoneNumbers": [
        {
          "isPreferred": "",
          "purpose": "",
          "countryCode": "",
          "areaCode": "",
          "number": "",
          "extension": "",
          "fullNumber": ""
        }
      ],
      "emailAddresses": [
        {
          "isPreferred": "",
          "purpose": "",
          "address": ""
        }
      ],
      "physicalAddresses": [
        {
          "purpose": "",
          "address$type": "",
          "simple": {
            "mailingName": "",
            "addressLine1": "",
            "addressLine2": "",
            "addressLine3": "",
            "postcode": "",
            "city": "",
            "state": "",
            "country": ""
          },
          "paf": {}
        }
      ]
    },
    "organisation": {
      "lastUpdateTime": "",
      "agentFirstName": "",
      "agentLastName": "",
      "agentRole": "",
      "businessName": "",
      "legalName": "",
      "shortName": "",
      "abn": "",
      "acn": "",
      "isACNCRegistered": "",
      "industryCode": "",
      "organisationType": "",
      "registeredCountry": "",
      "establishmentDate": "",
      "physicalAddress": [
        {
          "purpose": "",
          "address$type": "",
          "simple": {
            "mailingName": "",
            "addressLine1": "",
            "addressLine2": "",
            "addressLine3": "",
            "postcode": "",
            "city": "",
            "state": "",
            "country": ""
          },
          "paf": {}
        }
      ]
    }
  },
  "links": {
    "self": ""
  },
  "meta": {}
}
```

<h3 id="g-ccd-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[200_GET_Common_Customer_Detailed](#schema200_get_common_customer_detailed)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSaccountids_request">AccountIds_Request</h2>

<a id="schemaaccountids_request"></a>

```json
{
  "data": {
    "accountIds": [
      "string"
    ]
  },
  "meta": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|true|none|none|
|» accountIds|[string]|true|none|none|
|meta|[Meta_Object](#schemameta_object)|true|none|none|

<h2 id="tocS200_get_banking_products">200_GET_Banking_Products</h2>

<a id="schema200_get_banking_products"></a>

```json
{
  "data": {
    "products": [
      {
        "productId": "",
        "effectiveFrom": "",
        "effectiveTo": "",
        "lastUpdated": "",
        "productCategory": "",
        "name": "",
        "description": "",
        "brand": "",
        "brandName": "",
        "applicationUri": "",
        "isNegotiable": "",
        "additionalInformation": {
          "overviewUri": "",
          "termsUri": "",
          "eligibilityUri": "",
          "feesAndPricingUri": "",
          "bundleUri": ""
        }
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|true|none|none|
|» products|[[Product_Object](#schemaproduct_object)]|true|none|none|
|links|[LinksPaginated_Object](#schemalinkspaginated_object)|true|none|none|
|meta|[MetaPaginated_Object](#schemametapaginated_object)|true|none|none|

<h2 id="tocSproduct_object">Product_Object</h2>

<a id="schemaproduct_object"></a>

```json
{
  "productId": "",
  "effectiveFrom": "",
  "effectiveTo": "",
  "lastUpdated": "",
  "productCategory": "",
  "name": "",
  "description": "",
  "brand": "",
  "brandName": "",
  "applicationUri": "",
  "isNegotiable": "",
  "additionalInformation": {
    "overviewUri": "",
    "termsUri": "",
    "eligibilityUri": "",
    "feesAndPricingUri": "",
    "bundleUri": ""
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|productId|string(ASCIIString)|true|none|A provider specific unique identifier for this product. This identifier must be unique to a product but does not otherwise need to adhere to ID permanence guidelines.|
|effectiveFrom|string(DateTimeString)|false|none|The date and time from which this product is effective (ie. is available for origination)|
|effectiveTo|string(DateTimeString)|false|none|The date and time at which this product will be retired and will no longer be offered|
|lastUpdated|string(DateTimeString)|true|none|The last date and time that the information for this product was changed (or the creation date for the product if it has never been altered)|
|productCategory|string|true|none|The category of the accounts generated from this product|
|name|string|true|none|The display name of the product|
|description|string|true|none|A description of the product|
|brand|string|true|none|A label of the brand for the product. Able to be used for filtering. For data providers with single brands this value is still required|
|brandName|string|false|none|An optional display name of the brand|
|applicationUri|string|false|none|A link to the an application web page where this product can be applied for.|
|isNegotiable|boolean|true|none|Indicates whether the product is specifically designed so that fees and prices are negotiated depending on context. While all products are open to a degree of negotiation this flag indicates that negotiation is expected and thus that the provision of specific fees and rates is not applicable|
|additionalInformation|object|false|none|none|
|» overviewUri|string(URIString)|false|none|General overview of the product|
|» termsUri|string(URIString)|false|none|Terms and conditions for the product|
|» eligibilityUri|string(URIString)|false|none|Eligibility rules and criteria for the product|
|» feesAndPricingUri|string(URIString)|false|none|Description of fees, pricing, discounts, exemptions and bonuses for the product|
|» bundleUri|string(URIString)|false|none|Description of a bundle that this product can be part of|

#### Enumerated Values

|Property|Value|
|---|---|
|productCategory|PERS_AT_CALL_DEPOSITS|
|productCategory|BUS_AT_CALL_DEPOSITS|
|productCategory|TERM_DEPOSITS|
|productCategory|RESIDENTIAL_MORTGAGES|
|productCategory|PERS_CRED_AND_CHRG_CARDS|
|productCategory|BUS_CRED_AND_CHRG_CARDS|
|productCategory|PERS_LOANS|
|productCategory|PERS_LEASING|
|productCategory|BUS_LEASING|
|productCategory|TRADE_FINANCE|
|productCategory|PERS_OVERDRAFT|
|productCategory|BUS_OVERDRAFT|
|productCategory|BUS_LOANS|
|productCategory|FOREIGN_CURR_AT_CALL_DEPOSITS|
|productCategory|FOREIGN_CURR_TERM_DEPOSITS|
|productCategory|FOREIGN_CURR_LOAN|
|productCategory|FOREIGN_CURRRENCT_OVERDRAFT|
|productCategory|TRAVEL_CARD|

<h2 id="tocS200_get_banking_product">200_GET_Banking_Product</h2>

<a id="schema200_get_banking_product"></a>

```json
{
  "data": {
    "productId": "",
    "effectiveFrom": "",
    "effectiveTo": "",
    "lastUpdated": "",
    "productCategory": "",
    "name": "",
    "description": "",
    "brand": "",
    "brandName": "",
    "applicationUri": "",
    "isNegotiable": "",
    "additionalInformation": {
      "overviewUri": "",
      "termsUri": "",
      "eligibilityUri": "",
      "feesAndPricingUri": "",
      "bundleUri": ""
    },
    "bundles": [
      {
        "name": "",
        "description": "",
        "additionalInfoUri": "",
        "productIds": [
          "string"
        ]
      }
    ],
    "features": [
      {
        "featureType": "",
        "additionalValue": ""
      }
    ],
    "constraints": [
      {
        "constraintType": "",
        "additionalValue": ""
      }
    ],
    "eligibility": [
      {
        "eligibilityType": "",
        "additionalValue": "",
        "additionalInfo": "",
        "additionalInfoUri": ""
      }
    ],
    "fees": [
      {
        "name": "",
        "feeType": "",
        "amount": "",
        "balanceRate": "",
        "transactionRate": "",
        "currency": "",
        "additionalValue": "",
        "additionalInfo": "",
        "additionalInfoUri": "",
        "discounts": [
          {
            "description": "",
            "discountType": "",
            "amount": "",
            "additionalValue": ""
          }
        ]
      }
    ],
    "depositRates": [
      {
        "depositRateType": "",
        "rate": "",
        "additionalValue": "",
        "additionalInfo": "",
        "additionalInfoUri": ""
      }
    ],
    "lendingRates": [
      {
        "lendingRateType": "",
        "rate": "",
        "additionalValue": "",
        "additionalInfo": "",
        "additionalInfoUri": ""
      }
    ]
  },
  "links": {
    "self": ""
  },
  "meta": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[ProductDetail_Object](#schemaproductdetail_object)|true|none|none|
|links|[Links_Object](#schemalinks_object)|true|none|none|
|meta|[Meta_Object](#schemameta_object)|true|none|none|

<h2 id="tocSproductdetail_object">ProductDetail_Object</h2>

<a id="schemaproductdetail_object"></a>

```json
{
  "productId": "",
  "effectiveFrom": "",
  "effectiveTo": "",
  "lastUpdated": "",
  "productCategory": "",
  "name": "",
  "description": "",
  "brand": "",
  "brandName": "",
  "applicationUri": "",
  "isNegotiable": "",
  "additionalInformation": {
    "overviewUri": "",
    "termsUri": "",
    "eligibilityUri": "",
    "feesAndPricingUri": "",
    "bundleUri": ""
  },
  "bundles": [
    {
      "name": "",
      "description": "",
      "additionalInfoUri": "",
      "productIds": [
        "string"
      ]
    }
  ],
  "features": [
    {
      "featureType": "",
      "additionalValue": ""
    }
  ],
  "constraints": [
    {
      "constraintType": "",
      "additionalValue": ""
    }
  ],
  "eligibility": [
    {
      "eligibilityType": "",
      "additionalValue": "",
      "additionalInfo": "",
      "additionalInfoUri": ""
    }
  ],
  "fees": [
    {
      "name": "",
      "feeType": "",
      "amount": "",
      "balanceRate": "",
      "transactionRate": "",
      "currency": "",
      "additionalValue": "",
      "additionalInfo": "",
      "additionalInfoUri": "",
      "discounts": [
        {
          "description": "",
          "discountType": "",
          "amount": "",
          "additionalValue": ""
        }
      ]
    }
  ],
  "depositRates": [
    {
      "depositRateType": "",
      "rate": "",
      "additionalValue": "",
      "additionalInfo": "",
      "additionalInfoUri": ""
    }
  ],
  "lendingRates": [
    {
      "lendingRateType": "",
      "rate": "",
      "additionalValue": "",
      "additionalInfo": "",
      "additionalInfoUri": ""
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|productId|string(ASCIIString)|true|none|A provider specific unique identifier for this product. This identifier must be unique to a product but does not otherwise need to adhere to ID permanence guidelines.|
|effectiveFrom|string(DateTimeString)|false|none|The date and time from which this product is effective (ie. is available for origination)|
|effectiveTo|string(DateTimeString)|false|none|The date and time at which this product will be retired and will no longer be offered|
|lastUpdated|string(DateTimeString)|true|none|The last date and time that the information for this product was changed (or the creation date for the product if it has never been altered)|
|productCategory|string|true|none|The category of the accounts generated from this product|
|name|string|true|none|The display name of the product|
|description|string|true|none|A description of the product|
|brand|string|true|none|A label of the brand for the product. Able to be used for filtering. For data providers with single brands this value is still required|
|brandName|string|false|none|An optional display name of the brand|
|applicationUri|string|false|none|A link to the an application web page where this product can be applied for.|
|isNegotiable|boolean|true|none|Indicates whether the product is specifically designed so that fees and prices are negotiated depending on context. While all products are open to a degree of negotiation this flag indicates that negotiation is expected and thus that the provision of specific fees and rates is not applicable|
|additionalInformation|object|false|none|none|
|» overviewUri|string(URIString)|false|none|General overview of the product|
|» termsUri|string(URIString)|false|none|Terms and conditions for the product|
|» eligibilityUri|string(URIString)|false|none|Eligibility rules and criteria for the product|
|» feesAndPricingUri|string(URIString)|false|none|Description of fees, pricing, discounts, exemptions and bonuses for the product|
|» bundleUri|string(URIString)|false|none|Description of a bundle that this product can be part of|
|bundles|[[ProductBundles_Object](#schemaproductbundles_object)]|false|none|none|
|features|[[ProductFeatures_Object](#schemaproductfeatures_object)]|false|none|none|
|constraints|[[ProductConstraints_Object](#schemaproductconstraints_object)]|false|none|none|
|eligibility|[[ProductEligibility_Object](#schemaproducteligibility_object)]|false|none|none|
|fees|[[ProductFees_Object](#schemaproductfees_object)]|false|none|none|
|depositRates|[[ProductDepositRates_Object](#schemaproductdepositrates_object)]|false|none|none|
|lendingRates|[[ProductLendingRates_Object](#schemaproductlendingrates_object)]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|productCategory|PERS_AT_CALL_DEPOSITS|
|productCategory|BUS_AT_CALL_DEPOSITS|
|productCategory|TERM_DEPOSITS|
|productCategory|RESIDENTIAL_MORTGAGES|
|productCategory|PERS_CRED_AND_CHRG_CARDS|
|productCategory|BUS_CRED_AND_CHRG_CARDS|
|productCategory|PERS_LOANS|
|productCategory|PERS_LEASING|
|productCategory|BUS_LEASING|
|productCategory|TRADE_FINANCE|
|productCategory|PERS_OVERDRAFT|
|productCategory|BUS_OVERDRAFT|
|productCategory|BUS_LOANS|
|productCategory|FOREIGN_CURR_AT_CALL_DEPOSITS|
|productCategory|FOREIGN_CURR_TERM_DEPOSITS|
|productCategory|FOREIGN_CURR_LOAN|
|productCategory|FOREIGN_CURRRENCT_OVERDRAFT|
|productCategory|TRAVEL_CARD|

<h2 id="tocSproductbundles_object">ProductBundles_Object</h2>

<a id="schemaproductbundles_object"></a>

```json
{
  "name": "",
  "description": "",
  "additionalInfoUri": "",
  "productIds": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|Name of the bundle|
|description|string|true|none|Description of the bundle|
|additionalInfoUri|string(URIString)|false|none|Link to a web page with more information on the bundle criteria and benefits|
|productIds|[string]|true|none|Array of product IDs for products included in the bundle|

<h2 id="tocSproductfeatures_object">ProductFeatures_Object</h2>

<a id="schemaproductfeatures_object"></a>

```json
{
  "featureType": "",
  "additionalValue": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|featureType|string|true|none|The type of feature described|
|additionalValue|string|false|none|Generic field containing additional information relevant to the featureType specified. Whether mandatory or not is dependent on the value of featureType|

#### Enumerated Values

|Property|Value|
|---|---|
|featureType|CARD_ACCESS|
|featureType|ADDITIONAL_CARDS|
|featureType|UNLIMITED_TXNS|
|featureType|FREE_TXNS|
|featureType|FREE_TXNS_ALLOWANCE|
|featureType|LOYALTY_PROGRAM|
|featureType|OFFSET|
|featureType|OVERDRAFT|
|featureType|REDRAW|
|featureType|INSURANCE|
|featureType|BALANCE_TRANSFERS|
|featureType|INTEREST_FREE|
|featureType|INTEREST_FREE_TRANSFERS|
|featureType|DIGITAL_WALLET|
|featureType|DIGITAL_BANKING|
|featureType|NPP_PAYID|
|featureType|NPP_ENABLED|
|featureType|DONATE_INTEREST|
|featureType|BILL_PAYMENT|

<h2 id="tocSproductconstraints_object">ProductConstraints_Object</h2>

<a id="schemaproductconstraints_object"></a>

```json
{
  "constraintType": "",
  "additionalValue": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|constraintType|string|true|none|The type of constraint described.  See the next section for an overview of valid values and their meaning|
|additionalValue|string|false|none|Generic field containing additional information relevant to the constraintType specified.  Whether mandatory or not is dependent on the value of constraintType|

#### Enumerated Values

|Property|Value|
|---|---|
|constraintType|MIN_BALANCE|
|constraintType|OPENING_BALANCE|
|constraintType|MAX_LIMIT|
|constraintType|MIN_LIMIT|

<h2 id="tocSproducteligibility_object">ProductEligibility_Object</h2>

<a id="schemaproducteligibility_object"></a>

```json
{
  "eligibilityType": "",
  "additionalValue": "",
  "additionalInfo": "",
  "additionalInfoUri": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|eligibilityType|string|true|none|The type of eligibility criteria described.  See the next section for an overview of valid values and their meaning|
|additionalValue|string|false|none|Generic field containing additional information relevant to the eligibilityType specified.  Whether mandatory or not is dependent on the value of eligibilityType|
|additionalInfo|string|false|none|Display text providing more information on the eligibility criteria. Mandatory if the eligibilityType field is set to OTHER|
|additionalInfoUri|string(URIString)|false|none|Link to a web page with more information on this eligibility criteria|

#### Enumerated Values

|Property|Value|
|---|---|
|eligibilityType|BUSINESS|
|eligibilityType|PENSION_RECIPIENT|
|eligibilityType|MIN_AGE|
|eligibilityType|MAX_AGE|
|eligibilityType|MIN_INCOME|
|eligibilityType|MIN_TURNOVER|
|eligibilityType|STAFF|
|eligibilityType|STUDENT|
|eligibilityType|EMPLOYMENT_STATUS|
|eligibilityType|RESIDENCY_STATUS|
|eligibilityType|OTHER|

<h2 id="tocSproductfees_object">ProductFees_Object</h2>

<a id="schemaproductfees_object"></a>

```json
{
  "name": "",
  "feeType": "",
  "amount": "",
  "balanceRate": "",
  "transactionRate": "",
  "currency": "",
  "additionalValue": "",
  "additionalInfo": "",
  "additionalInfoUri": "",
  "discounts": [
    {
      "description": "",
      "discountType": "",
      "amount": "",
      "additionalValue": ""
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|Name of the fee|
|feeType|string|true|none|The type of fee|
|amount|string(AmountString)|false|none|The amount charged for the fee. Assumed to be in AUD. One of amount, balanceRate and transactionRate is mandatory|
|balanceRate|string(RateString)|false|none|A fee rate calculated based on a proportion of the balance. Assumed to be in AUD. One of amount, balanceRate and transactionRate is mandatory|
|transactionRate|string(RateString)|false|none|A fee rate calculated based on a proportion of a transaction. Assumed to be in AUD. One of amount, balanceRate and transactionRate is mandatory|
|currency|string(CurrencyString)|false|none|The currency the fee will be charged in. Assumes AUD if absent|
|additionalValue|string|false|none|Generic field containing additional information relevant to the feeType specified. Whether mandatory or not is dependent on the value of feeType|
|additionalInfo|string|false|none|Display text providing more information on the fee|
|additionalInfoUri|string(URIString)|false|none|Link to a web page with more information on this fee|
|discounts|[[ProductDiscounts_Object](#schemaproductdiscounts_object)]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|feeType|PERIODIC|
|feeType|TRANSACTION|
|feeType|ESTABLISHMENT|
|feeType|EXIT|
|feeType|OVERDRAW|
|feeType|MIN_BALANCE|
|feeType|REDRAW|
|feeType|CHEQUE_CASH|
|feeType|CHEQUE_STOP|
|feeType|CHEQUE_BOOK|
|feeType|CARD_REPLACE|
|feeType|PAPER_STATEMENT|
|feeType|OTHER_EVENT|

<h2 id="tocSproductdiscounts_object">ProductDiscounts_Object</h2>

<a id="schemaproductdiscounts_object"></a>

```json
{
  "description": "",
  "discountType": "",
  "amount": "",
  "additionalValue": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|description|string|true|none|Description of the discount|
|discountType|string|true|none|The type of discount. See the next section for an overview of valid values and their meaning|
|amount|string(AmountString)|true|none|Value of the discount. Note that the currency of the fee discount is expected to be the same as the currency of the fee itself|
|additionalValue|string|false|none|Generic field containing additional information relevant to the discountType specified. Whether mandatory or not is dependent on the value of discountType|

#### Enumerated Values

|Property|Value|
|---|---|
|discountType|BALANCE|
|discountType|DEPOSITS|
|discountType|PAYMENTS|
|discountType|BUNDLE|

<h2 id="tocSproductdepositrates_object">ProductDepositRates_Object</h2>

<a id="schemaproductdepositrates_object"></a>

```json
{
  "depositRateType": "",
  "rate": "",
  "additionalValue": "",
  "additionalInfo": "",
  "additionalInfoUri": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|depositRateType|string|true|none|The type of rate (base, bonus, etc). See the next section for an overview of valid values and their meaning|
|rate|string(RateString)|true|none|The rate to be applied|
|additionalValue|string|false|none|Generic field containing additional information relevant to the depositRateType specified. Whether mandatory or not is dependent on the value of depositRateType|
|additionalInfo|string|false|none|Display text providing more information on the fee|
|additionalInfoUri|string(URIString)|false|none|Link to a web page with more information on this fee|

#### Enumerated Values

|Property|Value|
|---|---|
|depositRateType|FIXED|
|depositRateType|BONUS|
|depositRateType|BUNDLE_BONUS|
|depositRateType|VARIABLE|
|depositRateType|INTRODUCTORY|

<h2 id="tocSproductlendingrates_object">ProductLendingRates_Object</h2>

<a id="schemaproductlendingrates_object"></a>

```json
{
  "lendingRateType": "",
  "rate": "",
  "additionalValue": "",
  "additionalInfo": "",
  "additionalInfoUri": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|lendingRateType|string|true|none|The type of rate (fixed, variable, etc). See the next section for an overview of valid values and their meaning|
|rate|string(RateString)|true|none|The rate to be applied|
|additionalValue|string|false|none|Information relevant to the lendingRateType specified.  Whether mandatory or not is dependent on the Generic field containing additional information relevant to the lendingRateType specified. Whether mandatory or not is dependent on the value of lendingRateType|
|additionalInfo|string|false|none|Display text providing more information on the fee.|
|additionalInfoUri|string(URIString)|false|none|Link to a web page with more information  on this fee|

#### Enumerated Values

|Property|Value|
|---|---|
|lendingRateType|FIXED|
|lendingRateType|INTRODUCTORY|
|lendingRateType|DISCOUNT|
|lendingRateType|PENALTY|
|lendingRateType|BUNDLE_DISCOUNT|
|lendingRateType|FLOATING|
|lendingRateType|MARKET_LINKED|
|lendingRateType|CASH_ADVANCE|
|lendingRateType|VARIABLE|
|lendingRateType|COMPARISON|

<h2 id="tocS200_get_banking_accounts">200_GET_Banking_Accounts</h2>

<a id="schema200_get_banking_accounts"></a>

```json
{
  "data": {
    "accounts": [
      {
        "accountid": "",
        "displayName": "",
        "nickname": "",
        "maskedNumber": "",
        "productCategory": "",
        "providerType": "",
        "balance$type": "",
        "deposits": {
          "currentBalance": {
            "amount": "",
            "currency": ""
          },
          "availableBalance": {
            "amount": "",
            "currency": ""
          }
        },
        "lending": {
          "accountBalance": {
            "amount": "",
            "currency": ""
          },
          "availableBalance": {
            "amount": "",
            "currency": ""
          },
          "creditLimit": {
            "amount": "",
            "currency": ""
          },
          "amortisedLimit": {
            "amount": "",
            "currency": ""
          }
        },
        "purses": [
          {
            "amount": "",
            "currency": ""
          }
        ]
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|true|none|none|
|» accounts|[[Account_Object](#schemaaccount_object)]|true|none|none|
|links|[LinksPaginated_Object](#schemalinkspaginated_object)|true|none|none|
|meta|[MetaPaginated_Object](#schemametapaginated_object)|true|none|none|

<h2 id="tocSaccount_object">Account_Object</h2>

<a id="schemaaccount_object"></a>

```json
{
  "accountid": "",
  "displayName": "",
  "nickname": "",
  "maskedNumber": "",
  "productCategory": "",
  "providerType": "",
  "balance$type": "",
  "deposits": {
    "currentBalance": {
      "amount": "",
      "currency": ""
    },
    "availableBalance": {
      "amount": "",
      "currency": ""
    }
  },
  "lending": {
    "accountBalance": {
      "amount": "",
      "currency": ""
    },
    "availableBalance": {
      "amount": "",
      "currency": ""
    },
    "creditLimit": {
      "amount": "",
      "currency": ""
    },
    "amortisedLimit": {
      "amount": "",
      "currency": ""
    }
  },
  "purses": [
    {
      "amount": "",
      "currency": ""
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|accountid|string(ASCIIString)|false|none|A unique ID of the account adhering to the standards for ID permanence|
|displayName|string|true|none|The display name of the account. If a customer provided nickname is available that value should be returned|
|nickname|string|false|none|A customer supplied nick name for the account|
|maskedNumber|string(MaskedAccountString)|true|none|A masked version of the account. Whether BSB/Account Number, Credit Card PAN or another number this should be formatted with each digit masked and the last three digits unmasked|
|productCategory|string|true|none|The category of the product or account|
|providerType|string|true|none|The unique type as defined by the account provider|
|balance$type|string|true|none|The type of balance object provided for the account. Must be one of: debit Debit Balance Type (see above) Conditional credit Credit Balance Type (see above) Conditional Multi Currency Purses Type (see above) Conditional purses debit credit purses|
|deposits|[DepositsBalance_Object](#schemadepositsbalance_object)|false|none|none|
|lending|[LendingBalance_Object](#schemalendingbalance_object)|false|none|none|
|purses|[[CurrencyAmount_Object](#schemacurrencyamount_object)]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|productCategory|PERS_AT_CALL_DEPOSITS|
|productCategory|BUS_AT_CALL_DEPOSITS|
|productCategory|TERM_DEPOSITS|
|productCategory|RESIDENTIAL_MORTGAGES|
|productCategory|PERS_CRED_AND_CHRG_CARDS|
|productCategory|BUS_CRED_AND_CHRG_CARDS|
|productCategory|PERS_LOANS|
|productCategory|PERS_LEASING|
|productCategory|BUS_LEASING|
|productCategory|TRADE_FINANCE|
|productCategory|PERS_OVERDRAFT|
|productCategory|BUS_OVERDRAFT|
|productCategory|BUS_LOANS|
|productCategory|FOREIGN_CURR_AT_CALL_DEPOSITS|
|productCategory|FOREIGN_CURR_TERM_DEPOSITS|
|productCategory|FOREIGN_CURR_LOAN|
|productCategory|FOREIGN_CURRRENCT_OVERDRAFT|
|productCategory|TRAVEL_CARD|
|balance$type|deposits|
|balance$type|lending|
|balance$type|purses|

<h2 id="tocS200_get_banking_account">200_GET_Banking_Account</h2>

<a id="schema200_get_banking_account"></a>

```json
{
  "data": {
    "accountid": "",
    "displayName": "",
    "nickname": "",
    "maskedNumber": "",
    "productCategory": "",
    "providerType": "",
    "balance$type": "",
    "deposits": {
      "currentBalance": {
        "amount": "",
        "currency": ""
      },
      "availableBalance": {
        "amount": "",
        "currency": ""
      }
    },
    "lending": {
      "accountBalance": {
        "amount": "",
        "currency": ""
      },
      "availableBalance": {
        "amount": "",
        "currency": ""
      },
      "creditLimit": {
        "amount": "",
        "currency": ""
      },
      "amortisedLimit": {
        "amount": "",
        "currency": ""
      }
    },
    "purses": [
      {
        "amount": "",
        "currency": ""
      }
    ],
    "bundleName": "",
    "specificAccount$type": "",
    "termDeposit": {
      "lodgementDate": "",
      "maturityDate": "",
      "maturityAmount": "",
      "maturityCurrency": "",
      "maturityInstructions": ""
    },
    "creditCard": {
      "minPaymentAmount": "",
      "paymentDueAmount": "",
      "paymentCurrency": "",
      "paymentDueDate": ""
    },
    "loan": {
      "originalStartDate": "",
      "originalLoanAmount": "",
      "originalLoanCurrency": "",
      "loanEndDate": "",
      "nextInstalmentDate": "",
      "minInstalmentAmount": "",
      "minInstalmentCurrency": "",
      "maxRedraw": "",
      "maxRedrawCurrency": "",
      "minRedraw": "",
      "minRedrawCurrency": "",
      "offsetAccountEnabled": "",
      "offsetAccountIds": [
        "string"
      ],
      "repaymentType": "",
      "repaymentFrequency": ""
    },
    "features": [
      {
        "featureType": "",
        "additionalValue": ""
      }
    ],
    "fees": [
      {
        "name": "",
        "feeType": "",
        "amount": "",
        "balanceRate": "",
        "transactionRate": "",
        "currency": "",
        "additionalValue": "",
        "additionalInfo": "",
        "additionalInfoUri": "",
        "discounts": [
          {
            "description": "",
            "discountType": "",
            "amount": "",
            "additionalValue": ""
          }
        ]
      }
    ],
    "depositRates": [
      {
        "depositRateType": "",
        "rate": "",
        "additionalValue": "",
        "additionalInfo": "",
        "additionalInfoUri": ""
      }
    ],
    "lendingRates": [
      {
        "lendingRateType": "",
        "rate": "",
        "additionalValue": "",
        "additionalInfo": "",
        "additionalInfoUri": ""
      }
    ],
    "address": {
      "address$type": "",
      "simple": {
        "mailingName": "",
        "addressLine1": "",
        "addressLine2": "",
        "addressLine3": "",
        "postcode": "",
        "city": "",
        "state": "",
        "country": ""
      },
      "paf": {}
    }
  },
  "links": {
    "self": ""
  },
  "meta": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[AccountDetail_Object](#schemaaccountdetail_object)|true|none|none|
|links|[Links_Object](#schemalinks_object)|true|none|none|
|meta|[Meta_Object](#schemameta_object)|true|none|none|

<h2 id="tocSaccountdetail_object">AccountDetail_Object</h2>

<a id="schemaaccountdetail_object"></a>

```json
{
  "accountid": "",
  "displayName": "",
  "nickname": "",
  "maskedNumber": "",
  "productCategory": "",
  "providerType": "",
  "balance$type": "",
  "deposits": {
    "currentBalance": {
      "amount": "",
      "currency": ""
    },
    "availableBalance": {
      "amount": "",
      "currency": ""
    }
  },
  "lending": {
    "accountBalance": {
      "amount": "",
      "currency": ""
    },
    "availableBalance": {
      "amount": "",
      "currency": ""
    },
    "creditLimit": {
      "amount": "",
      "currency": ""
    },
    "amortisedLimit": {
      "amount": "",
      "currency": ""
    }
  },
  "purses": [
    {
      "amount": "",
      "currency": ""
    }
  ],
  "bundleName": "",
  "specificAccount$type": "",
  "termDeposit": {
    "lodgementDate": "",
    "maturityDate": "",
    "maturityAmount": "",
    "maturityCurrency": "",
    "maturityInstructions": ""
  },
  "creditCard": {
    "minPaymentAmount": "",
    "paymentDueAmount": "",
    "paymentCurrency": "",
    "paymentDueDate": ""
  },
  "loan": {
    "originalStartDate": "",
    "originalLoanAmount": "",
    "originalLoanCurrency": "",
    "loanEndDate": "",
    "nextInstalmentDate": "",
    "minInstalmentAmount": "",
    "minInstalmentCurrency": "",
    "maxRedraw": "",
    "maxRedrawCurrency": "",
    "minRedraw": "",
    "minRedrawCurrency": "",
    "offsetAccountEnabled": "",
    "offsetAccountIds": [
      "string"
    ],
    "repaymentType": "",
    "repaymentFrequency": ""
  },
  "features": [
    {
      "featureType": "",
      "additionalValue": ""
    }
  ],
  "fees": [
    {
      "name": "",
      "feeType": "",
      "amount": "",
      "balanceRate": "",
      "transactionRate": "",
      "currency": "",
      "additionalValue": "",
      "additionalInfo": "",
      "additionalInfoUri": "",
      "discounts": [
        {
          "description": "",
          "discountType": "",
          "amount": "",
          "additionalValue": ""
        }
      ]
    }
  ],
  "depositRates": [
    {
      "depositRateType": "",
      "rate": "",
      "additionalValue": "",
      "additionalInfo": "",
      "additionalInfoUri": ""
    }
  ],
  "lendingRates": [
    {
      "lendingRateType": "",
      "rate": "",
      "additionalValue": "",
      "additionalInfo": "",
      "additionalInfoUri": ""
    }
  ],
  "address": {
    "address$type": "",
    "simple": {
      "mailingName": "",
      "addressLine1": "",
      "addressLine2": "",
      "addressLine3": "",
      "postcode": "",
      "city": "",
      "state": "",
      "country": ""
    },
    "paf": {}
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|accountid|string(ASCIIString)|false|none|A unique ID of the account adhering to the standards for ID permanence|
|displayName|string|true|none|The display name of the account. If a customer provided nickname is available that value should be returned|
|nickname|string|false|none|A customer supplied nick name for the account|
|maskedNumber|string(MaskedAccountString)|true|none|A masked version of the account. Whether BSB/Account Number, Credit Card PAN or another number this should be formatted with each digit masked and the last three digits unmasked|
|productCategory|string|true|none|The category of the product or account|
|providerType|string|true|none|The unique type as defined by the account provider|
|balance$type|string|true|none|The type of balance object provided for the account. Must be one of: debit Debit Balance Type (see above) Conditional credit Credit Balance Type (see above) Conditional Multi Currency Purses Type (see above) Conditional purses debit credit purses|
|deposits|[DepositsBalance_Object](#schemadepositsbalance_object)|false|none|none|
|lending|[LendingBalance_Object](#schemalendingbalance_object)|false|none|none|
|purses|[[CurrencyAmount_Object](#schemacurrencyamount_object)]|false|none|none|
|bundleName|string|false|none|Optional field to indicate if this account is part of a bundle that is providing additional benefit for to the customer|
|specificAccount$type|string|false|none|The type of structure to present account specific fields.|
|termDeposit|[TermDepositAccount_Object](#schematermdepositaccount_object)|false|none|none|
|creditCard|[CreditCardAccount_Object](#schemacreditcardaccount_object)|false|none|none|
|loan|[LoanAccount_Object](#schemaloanaccount_object)|false|none|none|
|features|[[AccountFeatures_Object](#schemaaccountfeatures_object)]|false|none|none|
|fees|[[AccountFees_Object](#schemaaccountfees_object)]|false|none|none|
|depositRates|[[AccountDepositRates_Object](#schemaaccountdepositrates_object)]|false|none|none|
|lendingRates|[[AccountLendingRates_Object](#schemaaccountlendingrates_object)]|false|none|none|
|address|object|false|none|none|
|» address$type|string|true|none|The type of address object present|
|» simple|[SimpleAddress_Object](#schemasimpleaddress_object)|false|none|none|
|» paf|[PAFAddress_Object](#schemapafaddress_object)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|productCategory|PERS_AT_CALL_DEPOSITS|
|productCategory|BUS_AT_CALL_DEPOSITS|
|productCategory|TERM_DEPOSITS|
|productCategory|RESIDENTIAL_MORTGAGES|
|productCategory|PERS_CRED_AND_CHRG_CARDS|
|productCategory|BUS_CRED_AND_CHRG_CARDS|
|productCategory|PERS_LOANS|
|productCategory|PERS_LEASING|
|productCategory|BUS_LEASING|
|productCategory|TRADE_FINANCE|
|productCategory|PERS_OVERDRAFT|
|productCategory|BUS_OVERDRAFT|
|productCategory|BUS_LOANS|
|productCategory|FOREIGN_CURR_AT_CALL_DEPOSITS|
|productCategory|FOREIGN_CURR_TERM_DEPOSITS|
|productCategory|FOREIGN_CURR_LOAN|
|productCategory|FOREIGN_CURRRENCT_OVERDRAFT|
|productCategory|TRAVEL_CARD|
|balance$type|deposits|
|balance$type|lending|
|balance$type|purses|
|specificAccount$type|termDeposit|
|specificAccount$type|creditCard|
|specificAccount$type|loan|
|address$type|simple|
|address$type|paf|

<h2 id="tocStermdepositaccount_object">TermDepositAccount_Object</h2>

<a id="schematermdepositaccount_object"></a>

```json
{
  "lodgementDate": "",
  "maturityDate": "",
  "maturityAmount": "",
  "maturityCurrency": "",
  "maturityInstructions": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|lodgementDate|string(DateTimeString)|true|none|The lodgement date of the original deposit|
|maturityDate|string(DateTimeString)|true|none|Maturity date for the term deposit|
|maturityAmount|string(AmountString)|false|none|Amount to be paid upon maturity. If absent it implies the amount to paid is variable and cannot currently be calculated|
|maturityCurrency|string(CurrencyString)|false|none|If absent assumes AUD|
|maturityInstructions|string|true|none|Current instructions on action to be taken at maturity|

#### Enumerated Values

|Property|Value|
|---|---|
|maturityInstructions|ROLLED_OVER|
|maturityInstructions|PAID_OUT_AT_MATURITY|

<h2 id="tocScreditcardaccount_object">CreditCardAccount_Object</h2>

<a id="schemacreditcardaccount_object"></a>

```json
{
  "minPaymentAmount": "",
  "paymentDueAmount": "",
  "paymentCurrency": "",
  "paymentDueDate": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|minPaymentAmount|string(AmountString)|true|none|The minimum payment amount due for the next card payment|
|paymentDueAmount|string(AmountString)|true|none|The amount due for the next card payment|
|paymentCurrency|string(CurrencyString)|false|none|If absent assumes AUD|
|paymentDueDate|string(DateTimeString)|true|none|Date that the next payment for the card is due|

<h2 id="tocSloanaccount_object">LoanAccount_Object</h2>

<a id="schemaloanaccount_object"></a>

```json
{
  "originalStartDate": "",
  "originalLoanAmount": "",
  "originalLoanCurrency": "",
  "loanEndDate": "",
  "nextInstalmentDate": "",
  "minInstalmentAmount": "",
  "minInstalmentCurrency": "",
  "maxRedraw": "",
  "maxRedrawCurrency": "",
  "minRedraw": "",
  "minRedrawCurrency": "",
  "offsetAccountEnabled": "",
  "offsetAccountIds": [
    "string"
  ],
  "repaymentType": "",
  "repaymentFrequency": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|originalStartDate|string(DateTimeString)|false|none|Optional original start date for the loan|
|originalLoanAmount|string(AmountString)|false|none|Optional original loan value|
|originalLoanCurrency|string(CurrencyString)|false|none|If absent assumes AUD|
|loanEndDate|string(DateTimeString)|true|none|Date that the loan is due to be repaid in full|
|nextInstalmentDate|string(DateTimeString)|true|none|Next date that an instalment is required|
|minInstalmentAmount|string(AmountString)|true|none|Minimum amount of next instalment|
|minInstalmentCurrency|string(CurrencyString)|false|none|If absent assumes AUD|
|maxRedraw|string(AmountString)|false|none|Maximum amount of funds that can be redrawn. If not present redraw is not available even if the feature exists for the account|
|maxRedrawCurrency|string(CurrencyString)|false|none|If absent assumes AUD|
|minRedraw|string|false|none|Minimum redraw amount|
|minRedrawCurrency|string(CurrencyString)|false|none|If absent assumes AUD|
|offsetAccountEnabled|boolean|false|none|Set to true if one or more offset accounts are configured for this loan account|
|offsetAccountIds|[string]|false|none|The accountIDs of the configured offset accounts attached to this loan. Only offset accounts that can be accesses under the current authorisation should be included. It is expected behaviour that offsetAccountEnabled is set to true but the offsetAccountIds field is absent or empty. This represents a situation where an offset account exists but details can not be accessed under the current authorisation|
|repaymentType|string|false|none|Options in place for repayments. If absent defaults to PRINCIPAL_AND_INTEREST|
|repaymentFrequency|string|true|none|The expected or required repayment frequency. Formatted according to ISO 8601 Durations|

#### Enumerated Values

|Property|Value|
|---|---|
|repaymentFrequency|INTEREST_ONLY|
|repaymentFrequency|PRINCIPAL_AND_INTEREST|

<h2 id="tocSaccountfeatures_object">AccountFeatures_Object</h2>

<a id="schemaaccountfeatures_object"></a>

```json
{
  "featureType": "",
  "additionalValue": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|featureType|string|true|none|The type of feature described|
|additionalValue|string|false|none|Generic field containing additional information relevant to the featureType specified. Whether mandatory or not is dependent on the value of featureType|

#### Enumerated Values

|Property|Value|
|---|---|
|featureType|CARD_ACCESS|
|featureType|ADDITIONAL_CARDS|
|featureType|UNLIMITED_TXNS|
|featureType|FREE_TXNS|
|featureType|FREE_TXNS_ALLOWANCE|
|featureType|LOYALTY_PROGRAM|
|featureType|OFFSET|
|featureType|OVERDRAFT|
|featureType|REDRAW|
|featureType|INSURANCE|
|featureType|BALANCE_TRANSFERS|
|featureType|INTEREST_FREE|
|featureType|INTEREST_FREE_TRANSFERS|
|featureType|DIGITAL_WALLET|
|featureType|DIGITAL_BANKING|
|featureType|NPP_PAYID|
|featureType|NPP_ENABLED|
|featureType|DONATE_INTEREST|
|featureType|BILL_PAYMENT|

<h2 id="tocSaccountfees_object">AccountFees_Object</h2>

<a id="schemaaccountfees_object"></a>

```json
{
  "name": "",
  "feeType": "",
  "amount": "",
  "balanceRate": "",
  "transactionRate": "",
  "currency": "",
  "additionalValue": "",
  "additionalInfo": "",
  "additionalInfoUri": "",
  "discounts": [
    {
      "description": "",
      "discountType": "",
      "amount": "",
      "additionalValue": ""
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|Name of the fee|
|feeType|string|true|none|The type of fee|
|amount|string(AmountString)|false|none|The amount charged for the fee. Assumed to be in AUD. One of amount, balanceRate and transactionRate is mandatory|
|balanceRate|string(RateString)|false|none|A fee rate calculated based on a proportion of the balance. Assumed to be in AUD. One of amount, balanceRate and transactionRate is mandatory|
|transactionRate|string(RateString)|false|none|A fee rate calculated based on a proportion of a transaction. Assumed to be in AUD. One of amount, balanceRate and transactionRate is mandatory|
|currency|string(CurrencyString)|false|none|The currency the fee will be charged in. Assumes AUD if absent|
|additionalValue|string|false|none|Generic field containing additional information relevant to the feeType specified. Whether mandatory or not is dependent on the value of feeType|
|additionalInfo|string|false|none|Display text providing more information on the fee|
|additionalInfoUri|string(URIString)|false|none|Link to a web page with more information on this fee|
|discounts|[[AccountDiscounts_Object](#schemaaccountdiscounts_object)]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|feeType|PERIODIC|
|feeType|TRANSACTION|
|feeType|EXIT|
|feeType|OVERDRAW|
|feeType|MIN_BALANCE|
|feeType|REDRAW|
|feeType|CHEQUE_CASH|
|feeType|CHEQUE_STOP|
|feeType|CHEQUE_BOOK|
|feeType|CARD_REPLACE|
|feeType|PAPER_STATEMENT|
|feeType|OTHER_EVENT|

<h2 id="tocSaccountdiscounts_object">AccountDiscounts_Object</h2>

<a id="schemaaccountdiscounts_object"></a>

```json
{
  "description": "",
  "discountType": "",
  "amount": "",
  "additionalValue": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|description|string|true|none|Description of the discount|
|discountType|string|true|none|The type of discount. See the next section for an overview of valid values and their meaning|
|amount|string(AmountString)|true|none|Value of the discount. Note that the currency of the fee discount is expected to be the same as the currency of the fee itself|
|additionalValue|string|false|none|Generic field containing additional information relevant to the discountType specified. Whether mandatory or not is dependent on the value of discountType|

#### Enumerated Values

|Property|Value|
|---|---|
|discountType|BALANCE|
|discountType|DEPOSITS|
|discountType|PAYMENTS|
|discountType|BUNDLE|

<h2 id="tocSaccountdepositrates_object">AccountDepositRates_Object</h2>

<a id="schemaaccountdepositrates_object"></a>

```json
{
  "depositRateType": "",
  "rate": "",
  "additionalValue": "",
  "additionalInfo": "",
  "additionalInfoUri": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|depositRateType|string|true|none|The type of rate (base, bonus, etc). See the next section for an overview of valid values and their meaning|
|rate|string(RateString)|true|none|The rate to be applied|
|additionalValue|string|false|none|Generic field containing additional information relevant to the depositRateType specified. Whether mandatory or not is dependent on the value of depositRateType|
|additionalInfo|string|false|none|Display text providing more information on the fee|
|additionalInfoUri|string(URIString)|false|none|Link to a web page with more information on this fee|

#### Enumerated Values

|Property|Value|
|---|---|
|depositRateType|FIXED|
|depositRateType|BONUS|
|depositRateType|BUNDLE_BONUS|
|depositRateType|VARIABLE|
|depositRateType|INTRODUCTORY|

<h2 id="tocSaccountlendingrates_object">AccountLendingRates_Object</h2>

<a id="schemaaccountlendingrates_object"></a>

```json
{
  "lendingRateType": "",
  "rate": "",
  "additionalValue": "",
  "additionalInfo": "",
  "additionalInfoUri": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|lendingRateType|string|true|none|The type of rate (fixed, variable, etc). See the next section for an overview of valid values and their meaning|
|rate|string(RateString)|true|none|The rate to be applied|
|additionalValue|string|false|none|Information relevant to the lendingRateType specified.  Whether mandatory or not is dependent on the Generic field containing additional information relevant to the lendingRateType specified. Whether mandatory or not is dependent on the value of lendingRateType|
|additionalInfo|string|false|none|Display text providing more information on the fee.|
|additionalInfoUri|string(URIString)|false|none|Link to a web page with more information  on this fee|

#### Enumerated Values

|Property|Value|
|---|---|
|lendingRateType|FIXED|
|lendingRateType|INTRODUCTORY|
|lendingRateType|DISCOUNT|
|lendingRateType|PENALTY|
|lendingRateType|BUNDLE_DISCOUNT|
|lendingRateType|FLOATING|
|lendingRateType|MARKET_LINKED|
|lendingRateType|CASH_ADVANCE|
|lendingRateType|VARIABLE|
|lendingRateType|COMPARISON|

<h2 id="tocS200_get_banking_account_transactions">200_GET_Banking_Account_Transactions</h2>

<a id="schema200_get_banking_account_transactions"></a>

```json
{
  "data": {
    "accountId": "",
    "displayName": "",
    "nickname": "",
    "transactions": [
      {
        "transactionid": "",
        "isDetailAvailable": "",
        "status": "",
        "description": "",
        "postDateTime": "",
        "executionDateTime": "",
        "amount": "",
        "currency": "",
        "reference": ""
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|true|none|none|
|» accountId|string(ASCIIString)|true|none|ID of the account for which transactions are provided|
|» displayName|string|true|none|The display name of the account as defined by the bank.  This should not incorporate account numbers or PANs.  If it does the values should be masked according to the rules of the MaskedAccountString common type.|
|» nickname|string|false|none|A customer supplied nick name for the account|
|» transactions|[[Transaction_Object](#schematransaction_object)]|true|none|none|
|links|[LinksPaginated_Object](#schemalinkspaginated_object)|true|none|none|
|meta|[MetaPaginated_Object](#schemametapaginated_object)|true|none|none|

<h2 id="tocStransaction_object">Transaction_Object</h2>

<a id="schematransaction_object"></a>

```json
{
  "transactionid": "",
  "isDetailAvailable": "",
  "status": "",
  "description": "",
  "postDateTime": "",
  "executionDateTime": "",
  "amount": "",
  "currency": "",
  "reference": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|transactionid|string(ASCIIString)|false|none|A unique ID of the transaction adhering to the standards for ID permanence. This is mandatory (through hashing if necessary) unless there are specific and justifiable technical reasons why a transaction cannot be uniquely identified for a particular account type|
|isDetailAvailable|boolean|true|none|True if extended information is available using the transaction detail end point. False if extended data is not available|
|status|string|true|none|Status of the transaction|
|description|string|true|none|The transaction description as applied by the financial institution|
|postDateTime|string(DateTimeString)|false|none|The time the transaction was posted. This field is mandatory if the transaction has status POSTED. This is the time that appears on a standard statement|
|executionDateTime|string(DateTimeString)|false|none|The time the transaction was executed by the originating customer, if available|
|amount|string(AmountString)|false|none|The value of the transaction. Negative values mean money was outgoing|
|currency|string(CurrencyString)|false|none|The currency for the transaction amount. AUD assumed if not present|
|reference|string|true|none|The reference for the transaction provided by the originating institution|

#### Enumerated Values

|Property|Value|
|---|---|
|status|PENDING|
|status|POSTED|

<h2 id="tocS200_get_banking_transactions_detail">200_GET_Banking_Transactions_Detail</h2>

<a id="schema200_get_banking_transactions_detail"></a>

```json
{
  "data": {
    "accountId": "",
    "displayName": "",
    "nickname": "",
    "transaction": [
      {
        "transactionid": "",
        "status": "",
        "description": "",
        "postDateTime": "",
        "executionDateTime": "",
        "amount": "",
        "currency": "",
        "reference": "",
        "extendedData": {
          "payer": "",
          "payee": "",
          "extension$type": "",
          "extendedDescription": "",
          "service": ""
        }
      }
    ]
  },
  "links": {
    "self": ""
  },
  "meta": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|true|none|none|
|» accountId|string(ASCIIString)|true|none|ID of the account for which transactions are provided|
|» displayName|string|true|none|The display name of the account as defined by the bank.  This should not incorporate account numbers or PANs.  If it does the values should be masked according to the rules of the MaskedAccountString common type.|
|» nickname|string|false|none|A customer supplied nick name for the account|
|» transaction|[[TransactionDetail_Object](#schematransactiondetail_object)]|true|none|none|
|links|[Links_Object](#schemalinks_object)|true|none|none|
|meta|[Meta_Object](#schemameta_object)|true|none|none|

<h2 id="tocStransactiondetail_object">TransactionDetail_Object</h2>

<a id="schematransactiondetail_object"></a>

```json
{
  "transactionid": "",
  "status": "",
  "description": "",
  "postDateTime": "",
  "executionDateTime": "",
  "amount": "",
  "currency": "",
  "reference": "",
  "extendedData": {
    "payer": "",
    "payee": "",
    "extension$type": "",
    "extendedDescription": "",
    "service": ""
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|transactionid|string(ASCIIString)|false|none|A unique ID of the transaction adhering to the standards for ID permanence. This is mandatory (through hashing if necessary) unless there are specific and justifiable technical reasons why a transaction cannot be uniquely identified for a particular account type|
|status|string|true|none|Status of the transaction|
|description|string|true|none|The transaction description as applied by the financial institution|
|postDateTime|string(DateTimeString)|false|none|The time the transaction was posted. This field is mandatory if the transaction has status POSTED. This is the time that appears on a standard statement|
|executionDateTime|string(DateTimeString)|false|none|The time the transaction was executed by the originating customer, if available|
|amount|string(AmountString)|false|none|The value of the transaction. Negative values mean money was outgoing|
|currency|string(CurrencyString)|false|none|The currency for the transaction amount. AUD assumed if not present|
|reference|string|true|none|The reference for the transaction provided by the originating institution|
|extendedData|[TransactionExtendedData_Object](#schematransactionextendeddata_object)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|PENDING|
|status|POSTED|

<h2 id="tocStransactionextendeddata_object">TransactionExtendedData_Object</h2>

<a id="schematransactionextendeddata_object"></a>

```json
{
  "payer": "",
  "payee": "",
  "extension$type": "",
  "extendedDescription": "",
  "service": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payer|string|false|none|Label of the originating payer.  Mandatory for inbound payment|
|payee|string|false|none|Label of the target PayID. Mandatory for an outbound payment|
|extension$type|string|false|none|Optional extended data provided specific to transaction originated via NPP|
|extendedDescription|string|false|none|An extended string description. Only present if specified by the extensionType field|
|service|string|true|none|Identifier of the applicable overlay service|

#### Enumerated Values

|Property|Value|
|---|---|
|extension$type|extendedDescription|
|service|X2P1.01|

<h2 id="tocS200_get_banking_bulk_transactions">200_GET_Banking_Bulk_Transactions</h2>

<a id="schema200_get_banking_bulk_transactions"></a>

```json
{
  "data": {
    "transactions": [
      {
        "accountId": "",
        "transactionid": "",
        "isDetailAvailable": "",
        "status": "",
        "description": "",
        "postDateTime": "",
        "executionDateTime": "",
        "amount": "",
        "currency": "",
        "reference": ""
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|true|none|none|
|» transactions|[[BulkTransaction_Object](#schemabulktransaction_object)]|true|none|none|
|links|[LinksPaginated_Object](#schemalinkspaginated_object)|true|none|none|
|meta|[MetaPaginated_Object](#schemametapaginated_object)|true|none|none|

<h2 id="tocSbulktransaction_object">BulkTransaction_Object</h2>

<a id="schemabulktransaction_object"></a>

```json
{
  "accountId": "",
  "transactionid": "",
  "isDetailAvailable": "",
  "status": "",
  "description": "",
  "postDateTime": "",
  "executionDateTime": "",
  "amount": "",
  "currency": "",
  "reference": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|accountId|string(ASCIIString)|true|none|A unique ID of the account adhering to the standards for ID permanence|
|transactionid|string(ASCIIString)|false|none|A unique ID of the transaction adhering to the standards for ID permanence. This is mandatory (through hashing if necessary) unless there are specific and justifiable technical reasons why a transaction cannot be uniquely identified for a particular account type|
|isDetailAvailable|boolean|true|none|True if extended information is available using the transaction detail end point. False if extended data is not available|
|status|string|true|none|Status of the transaction|
|description|string|true|none|The transaction description as applied by the financial institution|
|postDateTime|string(DateTimeString)|false|none|The time the transaction was posted. This field is mandatory if the transaction has status POSTED. This is the time that appears on a standard statement|
|executionDateTime|string(DateTimeString)|false|none|The time the transaction was executed by the originating customer, if available|
|amount|string(AmountString)|false|none|The value of the transaction. Negative values mean money was outgoing|
|currency|string(CurrencyString)|false|none|The currency for the transaction amount. AUD assumed if not present|
|reference|string|true|none|The reference for the transaction provided by the originating institution|

#### Enumerated Values

|Property|Value|
|---|---|
|status|PENDING|
|status|POSTED|

<h2 id="tocS200_get_banking_accounts_balances">200_GET_Banking_Accounts_Balances</h2>

<a id="schema200_get_banking_accounts_balances"></a>

```json
{
  "data": {
    "balances": [
      {
        "accountid": "",
        "balance$type": "",
        "deposits": {
          "currentBalance": {
            "amount": "",
            "currency": ""
          },
          "availableBalance": {
            "amount": "",
            "currency": ""
          }
        },
        "lending": {
          "accountBalance": {
            "amount": "",
            "currency": ""
          },
          "availableBalance": {
            "amount": "",
            "currency": ""
          },
          "creditLimit": {
            "amount": "",
            "currency": ""
          },
          "amortisedLimit": {
            "amount": "",
            "currency": ""
          }
        },
        "purses": [
          {
            "amount": "",
            "currency": ""
          }
        ]
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|true|none|none|
|» balances|[[Balance_Object](#schemabalance_object)]|true|none|none|
|links|[LinksPaginated_Object](#schemalinkspaginated_object)|true|none|none|
|meta|[MetaPaginated_Object](#schemametapaginated_object)|true|none|none|

<h2 id="tocSbalance_object">Balance_Object</h2>

<a id="schemabalance_object"></a>

```json
{
  "accountid": "",
  "balance$type": "",
  "deposits": {
    "currentBalance": {
      "amount": "",
      "currency": ""
    },
    "availableBalance": {
      "amount": "",
      "currency": ""
    }
  },
  "lending": {
    "accountBalance": {
      "amount": "",
      "currency": ""
    },
    "availableBalance": {
      "amount": "",
      "currency": ""
    },
    "creditLimit": {
      "amount": "",
      "currency": ""
    },
    "amortisedLimit": {
      "amount": "",
      "currency": ""
    }
  },
  "purses": [
    {
      "amount": "",
      "currency": ""
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|accountid|string|false|none|A unique ID of the account adhering to the standards for ID permanence|
|balance$type|string|true|none|The type of balance object provided for the account|
|deposits|[DepositsBalance_Object](#schemadepositsbalance_object)|false|none|none|
|lending|[LendingBalance_Object](#schemalendingbalance_object)|false|none|none|
|purses|[[CurrencyAmount_Object](#schemacurrencyamount_object)]|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|balance$type|debit|
|balance$type|lending|
|balance$type|purses|

<h2 id="tocSdepositsbalance_object">DepositsBalance_Object</h2>

<a id="schemadepositsbalance_object"></a>

```json
{
  "currentBalance": {
    "amount": "",
    "currency": ""
  },
  "availableBalance": {
    "amount": "",
    "currency": ""
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|currentBalance|[CurrencyAmount_Object](#schemacurrencyamount_object)|true|none|none|
|availableBalance|[CurrencyAmount_Object](#schemacurrencyamount_object)|true|none|none|

<h2 id="tocSlendingbalance_object">LendingBalance_Object</h2>

<a id="schemalendingbalance_object"></a>

```json
{
  "accountBalance": {
    "amount": "",
    "currency": ""
  },
  "availableBalance": {
    "amount": "",
    "currency": ""
  },
  "creditLimit": {
    "amount": "",
    "currency": ""
  },
  "amortisedLimit": {
    "amount": "",
    "currency": ""
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|accountBalance|[CurrencyAmount_Object](#schemacurrencyamount_object)|true|none|none|
|availableBalance|[CurrencyAmount_Object](#schemacurrencyamount_object)|true|none|none|
|creditLimit|[CurrencyAmount_Object](#schemacurrencyamount_object)|true|none|none|
|amortisedLimit|[CurrencyAmount_Object](#schemacurrencyamount_object)|false|none|none|

<h2 id="tocScurrencyamount_object">CurrencyAmount_Object</h2>

<a id="schemacurrencyamount_object"></a>

```json
{
  "amount": "",
  "currency": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|amount|string(AmountString)|true|none|The current balance of the account at this time. Should align to the current balance available via other channels such as ATM balance enquiry or Internet Banking|
|currency|string(CurrencyString)|false|none|If not present assumes AUD|

<h2 id="tocS200_get_banking_payees">200_GET_Banking_Payees</h2>

<a id="schema200_get_banking_payees"></a>

```json
{
  "data": {
    "payees": [
      {
        "payeeId": "",
        "nickname": "",
        "description": "",
        "type": ""
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|true|none|none|
|» payees|[[Payee_Object](#schemapayee_object)]|true|none|The list of payees returned|
|links|[LinksPaginated_Object](#schemalinkspaginated_object)|true|none|none|
|meta|[MetaPaginated_Object](#schemametapaginated_object)|true|none|none|

<h2 id="tocS200_get_banking_payee_details">200_GET_Banking_Payee_Details</h2>

<a id="schema200_get_banking_payee_details"></a>

```json
{
  "data": {
    "payeeId": "",
    "nickname": "",
    "description": "",
    "type": "",
    "payee$type": "",
    "domestic": {
      "payeeAccount$type": "",
      "account": {
        "accountName": "",
        "bsb": "",
        "accountNumber": ""
      },
      "card": {
        "cardNumber": ""
      },
      "payId": {
        "name": "",
        "identifier": "",
        "type": ""
      }
    },
    "biller": {
      "billerCode": "",
      "crn": "",
      "billerName": ""
    },
    "international": {
      "beneficiaryDetails": {
        "name": "",
        "country": "",
        "message": ""
      },
      "bankDetails": {
        "country": "",
        "accountNumber": "",
        "bankAddress": {
          "name": "",
          "address": ""
        },
        "beneficiaryBankBIC": "",
        "fedWireNumber": "",
        "sortCode": "",
        "chipNumber": "",
        "routingNumber": ""
      }
    }
  },
  "links": {
    "self": ""
  },
  "meta": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[PayeeDetail_Object](#schemapayeedetail_object)|true|none|none|
|links|[Links_Object](#schemalinks_object)|true|none|none|
|meta|[Meta_Object](#schemameta_object)|true|none|none|

<h2 id="tocSpayee_object">Payee_Object</h2>

<a id="schemapayee_object"></a>

```json
{
  "payeeId": "",
  "nickname": "",
  "description": "",
  "type": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payeeId|string|true|none|ID of the payee adhering to the rules of ID permanence|
|nickname|string|true|none|The short display name of the payee as provided by the customer|
|description|string|false|none|A description of the payee provided by the customer|
|type|string|true|none|The type of payee. DOMESTIC means a registered payee for domestic payments including NPP. INTERNATIONAL means a registered payee for international payments. BILLER means a registered payee for BPAY|

#### Enumerated Values

|Property|Value|
|---|---|
|type|DOMESTIC|
|type|INTERNATIONAL|
|type|BILLER|

<h2 id="tocSpayeedetail_object">PayeeDetail_Object</h2>

<a id="schemapayeedetail_object"></a>

```json
{
  "payeeId": "",
  "nickname": "",
  "description": "",
  "type": "",
  "payee$type": "",
  "domestic": {
    "payeeAccount$type": "",
    "account": {
      "accountName": "",
      "bsb": "",
      "accountNumber": ""
    },
    "card": {
      "cardNumber": ""
    },
    "payId": {
      "name": "",
      "identifier": "",
      "type": ""
    }
  },
  "biller": {
    "billerCode": "",
    "crn": "",
    "billerName": ""
  },
  "international": {
    "beneficiaryDetails": {
      "name": "",
      "country": "",
      "message": ""
    },
    "bankDetails": {
      "country": "",
      "accountNumber": "",
      "bankAddress": {
        "name": "",
        "address": ""
      },
      "beneficiaryBankBIC": "",
      "fedWireNumber": "",
      "sortCode": "",
      "chipNumber": "",
      "routingNumber": ""
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payeeId|string|true|none|ID of the payee adhering to the rules of ID permanence|
|nickname|string|true|none|The short display name of the payee as provided by the customer|
|description|string|false|none|A description of the payee provided by the customer|
|type|string|true|none|The type of payee. DOMESTIC means a registered payee for domestic payments including NPP. INTERNATIONAL means a registered payee for international payments. BILLER means a registered payee for BPAY|
|payee$type|string|true|none|Type of object included that describes the payee in detail|
|domestic|[DomesticPayee_Object](#schemadomesticpayee_object)|false|none|none|
|biller|[BillerPayee_Object](#schemabillerpayee_object)|false|none|none|
|international|[InternationalPayee_Object](#schemainternationalpayee_object)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|DOMESTIC|
|type|INTERNATIONAL|
|type|BILLER|
|payee$type|domestic|
|payee$type|biller|
|payee$type|international|

<h2 id="tocSdomesticpayee_object">DomesticPayee_Object</h2>

<a id="schemadomesticpayee_object"></a>

```json
{
  "payeeAccount$type": "",
  "account": {
    "accountName": "",
    "bsb": "",
    "accountNumber": ""
  },
  "card": {
    "cardNumber": ""
  },
  "payId": {
    "name": "",
    "identifier": "",
    "type": ""
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payeeAccount$type|string|true|none|Type of account object included. Valid values are: { payeeAccount$type - - account A standard Australian account defined by BSB/Account Number payId A PayID recognised by NPP|
|account|[DomesticPayeeAccount_Object](#schemadomesticpayeeaccount_object)|false|none|none|
|card|[DomesticPayeeCard_Object](#schemadomesticpayeecard_object)|false|none|none|
|payId|[DomesticPayeePayId_Object](#schemadomesticpayeepayid_object)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|payeeAccount$type|account|
|payeeAccount$type|card|
|payeeAccount$type|payid|

<h2 id="tocSdomesticpayeeaccount_object">DomesticPayeeAccount_Object</h2>

<a id="schemadomesticpayeeaccount_object"></a>

```json
{
  "accountName": "",
  "bsb": "",
  "accountNumber": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|accountName|string|true|none|Name of the account to pay to|
|bsb|string|true|none|BSB of the account to pay to|
|accountNumber|string|true|none|Number of the account to pay to|

<h2 id="tocSdomesticpayeecard_object">DomesticPayeeCard_Object</h2>

<a id="schemadomesticpayeecard_object"></a>

```json
{
  "cardNumber": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cardNumber|string(MaskedPANString)|true|none|Name of the account to pay to|

<h2 id="tocSdomesticpayeepayid_object">DomesticPayeePayId_Object</h2>

<a id="schemadomesticpayeepayid_object"></a>

```json
{
  "name": "",
  "identifier": "",
  "type": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|The name assigned to the PayID by the owner of the PayID|
|identifier|string|true|none|The identifier of the PayID (dependent on type)|
|type|string|true|none|The type of the PayID|

#### Enumerated Values

|Property|Value|
|---|---|
|type|EMAIL|
|type|MOBILE|
|type|ORG_NUMBER|
|type|ORG_NAME|

<h2 id="tocSbillerpayee_object">BillerPayee_Object</h2>

<a id="schemabillerpayee_object"></a>

```json
{
  "billerCode": "",
  "crn": "",
  "billerName": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|billerCode|string|true|none|BPay Biller Code of the Biller|
|crn|string|false|none|BPay CRN of the Biller. If the contents of the CRN match the format of a Credit Card PAN then it should be masked using the rules applicable for the MaskedPANString common type|
|billerName|string|true|none|Name of the Biller|

<h2 id="tocSinternationalpayee_object">InternationalPayee_Object</h2>

<a id="schemainternationalpayee_object"></a>

```json
{
  "beneficiaryDetails": {
    "name": "",
    "country": "",
    "message": ""
  },
  "bankDetails": {
    "country": "",
    "accountNumber": "",
    "bankAddress": {
      "name": "",
      "address": ""
    },
    "beneficiaryBankBIC": "",
    "fedWireNumber": "",
    "sortCode": "",
    "chipNumber": "",
    "routingNumber": ""
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|beneficiaryDetails|object|true|none|none|
|» name|string|false|none|Name of the beneficiary|
|» country|string|true|none|Country where the beneficiary resides|
|» message|string|false|none|Response message for the payment|
|bankDetails|object|true|none|none|
|» country|string|true|none|Country of the recipient institution|
|» accountNumber|string|true|none|Account Targeted for payment|
|» bankAddress|object|false|none|none|
|»» name|string|true|none|Name of the recipient Bank|
|»» address|string|true|none|Address of the recipient Bank|
|» beneficiaryBankBIC|string|false|none|Swift bank code|
|» fedWireNumber|string|false|none|Number for Fedwire payment (Federal Reserve Wire Network)|
|» sortCode|string|false|none|Sort code used for account identification in some jurisdictions|
|» chipNumber|string|false|none|Number for the Clearing House Interbank Payments System|
|» routingNumber|string|false|none|International bank routing number|

<h2 id="tocS200_get_banking_direct-debits">200_GET_Banking_Direct-Debits</h2>

<a id="schema200_get_banking_direct-debits"></a>

```json
{
  "data": {
    "directDebitAuthorisations": [
      {
        "accountId": "",
        "authorisedEntity": {
          "name": "",
          "financialInstitution": "",
          "abn": "",
          "acn": ""
        },
        "lastDebitDateTime": "",
        "lastDebitAmount": ""
      }
    ]
  },
  "links": {
    "self": "",
    "first": "",
    "prev": "",
    "next": "",
    "last": ""
  },
  "meta": {
    "totalRecords": "",
    "totalPages": ""
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|true|none|none|
|» directDebitAuthorisations|[[DirectDebits_Object](#schemadirectdebits_object)]|true|none|The list of authorisations returned|
|links|[LinksPaginated_Object](#schemalinkspaginated_object)|true|none|none|
|meta|[MetaPaginated_Object](#schemametapaginated_object)|true|none|none|

<h2 id="tocSdirectdebits_object">DirectDebits_Object</h2>

<a id="schemadirectdebits_object"></a>

```json
{
  "accountId": "",
  "authorisedEntity": {
    "name": "",
    "financialInstitution": "",
    "abn": "",
    "acn": ""
  },
  "lastDebitDateTime": "",
  "lastDebitAmount": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|accountId|string(ASCIIString)|true|none|A unique ID of the account adhering to the standards for ID permanence.|
|authorisedEntity|[AuthorisedEntity_Object](#schemaauthorisedentity_object)|false|none|none|
|lastDebitDateTime|string(DateTimeString)|false|none|The date and time of the last debit executed under this authorisation|
|lastDebitAmount|string(AmountString)|false|none|The amount of the last debit executed under this authorisation|

<h2 id="tocSauthorisedentity_object">AuthorisedEntity_Object</h2>

<a id="schemaauthorisedentity_object"></a>

```json
{
  "name": "",
  "financialInstitution": "",
  "abn": "",
  "acn": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|Name of the authorised entity|
|financialInstitution|string|true|none|Name of the financial institution through which the direct debit will be executed|
|abn|string|false|none|Australian Business Number for the authorised entity|
|acn|string|false|none|Australian Business Number for the authorised entity|

<h2 id="tocS200_get_common_customer">200_GET_Common_Customer</h2>

<a id="schema200_get_common_customer"></a>

```json
{
  "data": {
    "customer$type": "",
    "person": {
      "lastUpdateTime": "",
      "firstName": "",
      "lastName": "",
      "middleNames": [
        "string"
      ],
      "prefix": "",
      "suffix": "",
      "occupationCode": ""
    },
    "organisation": {
      "lastUpdateTime": "",
      "agentFirstName": "",
      "agentLastName": "",
      "agentRole": "",
      "businessName": "",
      "legalName": "",
      "shortName": "",
      "abn": "",
      "acn": "",
      "isACNCRegistered": "",
      "industryCode": "",
      "organisationType": "",
      "registeredCountry": "",
      "establishmentDate": ""
    }
  },
  "links": {
    "self": ""
  },
  "meta": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|true|none|none|
|» customer$type|string|true|none|The type of customer object that is present|
|» person|[Person_Object](#schemaperson_object)|false|none|none|
|» organisation|[Organisation_Object](#schemaorganisation_object)|false|none|none|
|links|[Links_Object](#schemalinks_object)|true|none|none|
|meta|[Meta_Object](#schemameta_object)|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|customer$type|person|
|customer$type|organisation|

<h2 id="tocS200_get_common_customer_detailed">200_GET_Common_Customer_Detailed</h2>

<a id="schema200_get_common_customer_detailed"></a>

```json
{
  "data": {
    "customer$type": "",
    "person": {
      "lastUpdateTime": "",
      "firstName": "",
      "lastName": "",
      "middleNames": [
        "string"
      ],
      "prefix": "",
      "suffix": "",
      "occupationCode": "",
      "phoneNumbers": [
        {
          "isPreferred": "",
          "purpose": "",
          "countryCode": "",
          "areaCode": "",
          "number": "",
          "extension": "",
          "fullNumber": ""
        }
      ],
      "emailAddresses": [
        {
          "isPreferred": "",
          "purpose": "",
          "address": ""
        }
      ],
      "physicalAddresses": [
        {
          "purpose": "",
          "address$type": "",
          "simple": {
            "mailingName": "",
            "addressLine1": "",
            "addressLine2": "",
            "addressLine3": "",
            "postcode": "",
            "city": "",
            "state": "",
            "country": ""
          },
          "paf": {}
        }
      ]
    },
    "organisation": {
      "lastUpdateTime": "",
      "agentFirstName": "",
      "agentLastName": "",
      "agentRole": "",
      "businessName": "",
      "legalName": "",
      "shortName": "",
      "abn": "",
      "acn": "",
      "isACNCRegistered": "",
      "industryCode": "",
      "organisationType": "",
      "registeredCountry": "",
      "establishmentDate": "",
      "physicalAddress": [
        {
          "purpose": "",
          "address$type": "",
          "simple": {
            "mailingName": "",
            "addressLine1": "",
            "addressLine2": "",
            "addressLine3": "",
            "postcode": "",
            "city": "",
            "state": "",
            "country": ""
          },
          "paf": {}
        }
      ]
    }
  },
  "links": {
    "self": ""
  },
  "meta": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|true|none|none|
|» customer$type|string|true|none|The type of customer object that is present|
|» person|[PersonDetail_Object](#schemapersondetail_object)|false|none|none|
|» organisation|[OrganisationDetail_Object](#schemaorganisationdetail_object)|false|none|none|
|links|[Links_Object](#schemalinks_object)|true|none|none|
|meta|[Meta_Object](#schemameta_object)|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|customer$type|person|
|customer$type|organisation|

<h2 id="tocSperson_object">Person_Object</h2>

<a id="schemaperson_object"></a>

```json
{
  "lastUpdateTime": "",
  "firstName": "",
  "lastName": "",
  "middleNames": [
    "string"
  ],
  "prefix": "",
  "suffix": "",
  "occupationCode": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|lastUpdateTime|string(DateTimeString)|true|none|The date and time that this record was last updated by the customer.  If no update has occurred then this date should reflect the initial creation date for the data|
|firstName|string|false|none|For people with single names this field need not be present.  The single name should be in the lastName field|
|lastName|string|true|none|For people with single names the single name should be in this field|
|middleNames|[string]|true|none|Field is mandatory but array may be empty|
|prefix|string|false|none|Also known as title or salutation.  The prefix to the name (e.g. Mr, Mrs, Ms, Miss, Sir, etc)|
|suffix|string|false|none|Used for a trailing suffix to the name (e.g. Jr)|
|occupationCode|string|false|none|Occupation code as defined by the ANZSCO  v1.2 Standard Classification of Occupations|

<h2 id="tocSpersondetail_object">PersonDetail_Object</h2>

<a id="schemapersondetail_object"></a>

```json
{
  "lastUpdateTime": "",
  "firstName": "",
  "lastName": "",
  "middleNames": [
    "string"
  ],
  "prefix": "",
  "suffix": "",
  "occupationCode": "",
  "phoneNumbers": [
    {
      "isPreferred": "",
      "purpose": "",
      "countryCode": "",
      "areaCode": "",
      "number": "",
      "extension": "",
      "fullNumber": ""
    }
  ],
  "emailAddresses": [
    {
      "isPreferred": "",
      "purpose": "",
      "address": ""
    }
  ],
  "physicalAddresses": [
    {
      "purpose": "",
      "address$type": "",
      "simple": {
        "mailingName": "",
        "addressLine1": "",
        "addressLine2": "",
        "addressLine3": "",
        "postcode": "",
        "city": "",
        "state": "",
        "country": ""
      },
      "paf": {}
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|lastUpdateTime|string(DateTimeString)|true|none|The date and time that this record was last updated by the customer.  If no update has occurred then this date should reflect the initial creation date for the data|
|firstName|string|false|none|For people with single names this field need not be present.  The single name should be in the lastName field|
|lastName|string|true|none|For people with single names the single name should be in this field|
|middleNames|[string]|true|none|Field is mandatory but array may be empty|
|prefix|string|false|none|Also known as title or salutation.  The prefix to the name (e.g. Mr, Mrs, Ms, Miss, Sir, etc)|
|suffix|string|false|none|Used for a trailing suffix to the name (e.g. Jr)|
|occupationCode|string|false|none|Occupation code as defined by the ANZSCO  v1.2 Standard Classification of Occupations|
|phoneNumbers|[[PhoneNumber](#schemaphonenumber)]|true|none|At least one record is required|
|emailAddresses|[[EmailAddress](#schemaemailaddress)]|true|none|May be empty|
|physicalAddresses|[[PhysicalAddress_Object](#schemaphysicaladdress_object)]|true|none|Must contain at least one address. One and only one address may have the purpose of REGISTERED. Zero or one, and no more than one, record may have the purpose of MAIL. If zero then the REGISTERED address is to be used for mail|

<h2 id="tocSorganisation_object">Organisation_Object</h2>

<a id="schemaorganisation_object"></a>

```json
{
  "lastUpdateTime": "",
  "agentFirstName": "",
  "agentLastName": "",
  "agentRole": "",
  "businessName": "",
  "legalName": "",
  "shortName": "",
  "abn": "",
  "acn": "",
  "isACNCRegistered": "",
  "industryCode": "",
  "organisationType": "",
  "registeredCountry": "",
  "establishmentDate": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|lastUpdateTime|string(DateTimeString)|true|none|The date and time that this record was last updated by the customer. If no update has occurred then this date should reflect the initial creation date for the data|
|agentFirstName|string|false|none|The first name of the individual providing access on behalf of the organisation. For people with single names this field need not be present.  The single name should be in the lastName field|
|agentLastName|string|true|none|The last name of the individual providing access on behalf of the organisation. For people with single names the single name should be in this field|
|agentRole|string|true|none|The role of the individual identified as the agent who is providing authorisation.  Expected to be used for display.  Default to “Unspecified” if the role is not known|
|businessName|string|true|none|Name of the organisation|
|legalName|string|false|none|Legal name, if different to the business name|
|shortName|string|false|none|Short name used for communication, if  different to the business name|
|abn|string|false|none|Australian Business Number for the organisation|
|acn|string|false|none|Australian Company Number for the organisation. Required only if an ACN is applicable for the organisation type|
|isACNCRegistered|boolean|false|none|True if registered with the ACNC.  False if not. Absent or null if not confirmed.|
|industryCode|string|false|none|ANZSIC (2006) code for the organisation.|
|organisationType|string|true|none|Legal organisation type|
|registeredCountry|string|false|none|Enumeration with values from ISO 3166 Alpha-3 country codes.  Assumed to be AUS if absent|
|establishmentDate|string(DateTimeString)|false|none|The date the organisation described was established|

#### Enumerated Values

|Property|Value|
|---|---|
|organisationType|SOLE_TRADER|
|organisationType|COMPANY|
|organisationType|PARTNERSHIP|
|organisationType|TRUST|
|organisationType|GOVERNMENT_ENTITY|
|organisationType|OTHER|

<h2 id="tocSorganisationdetail_object">OrganisationDetail_Object</h2>

<a id="schemaorganisationdetail_object"></a>

```json
{
  "lastUpdateTime": "",
  "agentFirstName": "",
  "agentLastName": "",
  "agentRole": "",
  "businessName": "",
  "legalName": "",
  "shortName": "",
  "abn": "",
  "acn": "",
  "isACNCRegistered": "",
  "industryCode": "",
  "organisationType": "",
  "registeredCountry": "",
  "establishmentDate": "",
  "physicalAddress": [
    {
      "purpose": "",
      "address$type": "",
      "simple": {
        "mailingName": "",
        "addressLine1": "",
        "addressLine2": "",
        "addressLine3": "",
        "postcode": "",
        "city": "",
        "state": "",
        "country": ""
      },
      "paf": {}
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|lastUpdateTime|string(DateTimeString)|true|none|The date and time that this record was last updated by the customer. If no update has occurred then this date should reflect the initial creation date for the data|
|agentFirstName|string|false|none|The first name of the individual providing access on behalf of the organisation. For people with single names this field need not be present.  The single name should be in the lastName field|
|agentLastName|string|true|none|The last name of the individual providing access on behalf of the organisation. For people with single names the single name should be in this field|
|agentRole|string|true|none|The role of the individual identified as the agent who is providing authorisation.  Expected to be used for display.  Default to “Unspecified” if the role is not known|
|businessName|string|true|none|Name of the organisation|
|legalName|string|false|none|Legal name, if different to the business name|
|shortName|string|false|none|Short name used for communication, if  different to the business name|
|abn|string|false|none|Australian Business Number for the organisation|
|acn|string|false|none|Australian Company Number for the organisation. Required only if an ACN is applicable for the organisation type|
|isACNCRegistered|boolean|false|none|True if registered with the ACNC.  False if not. Absent or null if not confirmed.|
|industryCode|string|false|none|ANZSIC (2006) code for the organisation.|
|organisationType|string|true|none|Legal organisation type|
|registeredCountry|string|false|none|Enumeration with values from ISO 3166 Alpha-3 country codes.  Assumed to be AUS if absent|
|establishmentDate|string(DateTimeString)|false|none|The date the organisation described was established|
|physicalAddress|[[PhysicalAddress_Object](#schemaphysicaladdress_object)]|true|none|Must contain at least one address. One and only one address may have the purpose of REGISTERED. Zero or one, and no more than one, record may have the purpose of MAIL. If zero then the REGISTERED address is to be used for mail|

#### Enumerated Values

|Property|Value|
|---|---|
|organisationType|SOLE_TRADER|
|organisationType|COMPANY|
|organisationType|PARTNERSHIP|
|organisationType|TRUST|
|organisationType|GOVERNMENT_ENTITY|
|organisationType|OTHER|

<h2 id="tocSphonenumber">PhoneNumber</h2>

<a id="schemaphonenumber"></a>

```json
{
  "isPreferred": "",
  "purpose": "",
  "countryCode": "",
  "areaCode": "",
  "number": "",
  "extension": "",
  "fullNumber": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isPreferred|boolean|true|none|Required to be true for one and only one entry to indicate the preferred phone number|
|purpose|string|true|none|The purpose of the number as specified by the customer|
|countryCode|string|false|none|If absent, assumed to be Australia (+61). The + should be included|
|areaCode|string|false|none|Required for non Mobile Phones, if field is present and refers to Australian code - the leading 0 should be omitted.|
|number|string|true|none|The actual phone number, with leading zeros as appropriate|
|extension|string|false|none|An extension number (if applicable)|
|fullNumber|string|true|none|Fully formatted phone number with country code, area code, number and extension incorporated. Formatted according to section 5.1.4. of RFC 3966|

#### Enumerated Values

|Property|Value|
|---|---|
|purpose|MOBILE|
|purpose|HOME|
|purpose|WORK|
|purpose|OTHER|
|purpose|INTERNATIONAL|
|purpose|UNSPECIFIED|

<h2 id="tocSemailaddress">EmailAddress</h2>

<a id="schemaemailaddress"></a>

```json
{
  "isPreferred": "",
  "purpose": "",
  "address": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isPreferred|boolean|true|none|Required for one and only one email record in the collection. Denotes the default email address|
|purpose|string|true|none|The purpose for the email, as specified by the customer (Enumeration)|
|address|string|true|none|A correctly formatted email address, as defined by the addr_spec format in RFC_5322|

#### Enumerated Values

|Property|Value|
|---|---|
|purpose|WORK|
|purpose|HOME|
|purpose|OTHER|
|purpose|UNSPECIFIED|

<h2 id="tocSphysicaladdress_object">PhysicalAddress_Object</h2>

<a id="schemaphysicaladdress_object"></a>

```json
{
  "purpose": "",
  "address$type": "",
  "simple": {
    "mailingName": "",
    "addressLine1": "",
    "addressLine2": "",
    "addressLine3": "",
    "postcode": "",
    "city": "",
    "state": "",
    "country": ""
  },
  "paf": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|purpose|string|true|none|Enumeration of values indicating the purpose of the physical address|
|address$type|string|true|none|The type of address object present|
|simple|[SimpleAddress_Object](#schemasimpleaddress_object)|false|none|none|
|paf|[PAFAddress_Object](#schemapafaddress_object)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|purpose|REGISTERED|
|purpose|MAIL|
|purpose|PHYSICAL|
|purpose|WORK|
|purpose|OTHER|
|address$type|simple|
|address$type|paf|

<h2 id="tocSsimpleaddress_object">SimpleAddress_Object</h2>

<a id="schemasimpleaddress_object"></a>

```json
{
  "mailingName": "",
  "addressLine1": "",
  "addressLine2": "",
  "addressLine3": "",
  "postcode": "",
  "city": "",
  "state": "",
  "country": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mailingName|string|false|none|Name of the individual or business formatted for inclusion in an address used for physical mail|
|addressLine1|string|true|none|First line of the standard address object|
|addressLine2|string|false|none|Second line of the standard address object|
|addressLine3|string|false|none|Third line of the standard address object|
|postcode|string|false|none|Mandatory for Australian addresses|
|city|string|true|none|Name of the city or locality|
|state|string|true|none|Free text if the country is not Australia. If country is Australia then must be one of the values defined by the ISO 3166:AU standard|
|country|string|false|none|A valid ISO 3166 Alpha-3 country code|

<h2 id="tocSpafaddress_object">PAFAddress_Object</h2>

<a id="schemapafaddress_object"></a>

```json
{}

```

### Properties

*None*

<h2 id="tocSlinks_object">Links_Object</h2>

<a id="schemalinks_object"></a>

```json
{
  "self": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|self|string(URIString)|false|none|Fully qualified link to this API call|

<h2 id="tocSmeta_object">Meta_Object</h2>

<a id="schemameta_object"></a>

```json
{}

```

### Properties

*None*

<h2 id="tocSlinkspaginated_object">LinksPaginated_Object</h2>

<a id="schemalinkspaginated_object"></a>

```json
{
  "self": "",
  "first": "",
  "prev": "",
  "next": "",
  "last": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|self|string(URIString)|false|none|Fully qualified link to this API call|
|first|string(URIString)|false|none|URI to the first page of this set. Mandatory if this response is not the first page|
|prev|string(URIString)|false|none|URI to the first previous page of this set. Mandatory if this response is not the first page|
|next|string(URIString)|false|none|URI to the first next page of this set. Mandatory if this response is not the last page|
|last|string(URIString)|false|none|URI to the first last page of this set. Mandatory if this response is not the last page|

<h2 id="tocSmetapaginated_object">MetaPaginated_Object</h2>

<a id="schemametapaginated_object"></a>

```json
{
  "totalRecords": "",
  "totalPages": ""
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalRecords|integer(NaturalNumber)|false|none|The total number of records in the full set|
|totalPages|integer(NaturalNumber)|false|none|The total number of pages in the full set|

<h2 id="tocS422_errors">422_Errors</h2>

<a id="schema422_errors"></a>

```json
{
  "errors": [
    {
      "code": "",
      "title": "",
      "detail": "",
      "meta": ""
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errors|[object]|true|none|none|
|» code|string|true|none|The code of the error|
|» title|string|true|none|A displayable title of the error type|
|» detail|string|true|none|Detail of the error|
|» meta|object|false|none|Optional additional data for specific error types|