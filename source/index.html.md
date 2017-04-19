---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='mailto:info@getlivesmart.com'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Livesmart API! You can use our API to access Livesmart API endpoints.

We have language bindings in Shell! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "https://api.getlivesmart.com/api/v2/company/employee/register"
  -H "API-KEY: 131234345435" -H "LIVESMART-HMAC-SHA256:34jkWE2RTFhjhd32d2d22a1SAW"
```


> Make sure to replace `131234345435` with your API key.

Livesmart uses API keys to allow access to the API. We ll provide you API key upon request.

All API requests must be made over HTTPS. Calls made over plain HTTP will fail. API requests without authentication will also fail.

Livesmart expects for the API key to be included in all API requests to the server in a header that looks like the following:

`API-KEY: 131234345435`

`LIVESMART-HMAC-SHA256: 34jkWE2RTFhjhd32d2d22a1SAW`

<aside class="notice">
You must replace <code>131234345435</code> with your personal API key and 34jkWE2RTFhjhd32d2d22a1SAW with the HMAC of the request body using the secret key.
</aside>


# User Purchase

## Register User Purchase


```shell
curl "https://api.getlivesmart.com/api/v2/purchase/register"
  -H "API-KEY: 131234345435" -H "LIVESMART-HMAC-SHA256: dsfjsdklfjwef2342jkh14141jkh124h4k1h"
  -H "Content-Type: application/json"
  -X POST -d '{
    "email": "johndoe@domain.com",
    "sku": "LSP3",
    "collectionMethod": "HomeKit",
    "birthDate": "1974-12-16",
    "firstName": "John",
    "lastName": "Doe",
    "gender": "M",
    "phone": "44 00 22200000",
    "street": "221B Baker Street",
    "city": "London",
    "zip": "NW1 6XE",
    "country": "United Kingdom"
    }'
```

> The above command returns JSON structured like this:

```json
{
  "orderNumber": "1204912980",
  "patientId": 63427
}
```

This endpoint register a user purchase.

### HTTP Request

`POST https://api.getlivesmart.com/api/v2/purchase/register`

### Query Parameters

Parameter | Required | Example | Description
--------- | ------- | ----------- | ----------
sku | True | LSP3 |
collectionMethod | True | HomeKit|  Collection Method Selected (HomeKit, Lab, Visit)
email | True | username@domain.com |
birthDate | True | 2000-12-01 | Format is YYYY-MM-DD
firstName | True | John |
lastName | True | Doe |
gender | True | M | M for Male and F for Female
phone | True | 44 020 000 000 |
street | True | Street Address |
city | True | London |
zip | True | 4W1 1SNG |
country | True | United Kindgom |


<aside class="success">
Remember — a happy request is an authenticated request!
</aside>
