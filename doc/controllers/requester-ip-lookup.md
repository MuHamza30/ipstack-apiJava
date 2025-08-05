# Requester IP Lookup

```java
RequesterIPLookupController requesterIPLookupController = client.getRequesterIPLookupController();
```

## Class Name

`RequesterIPLookupController`


# Get Requester IP Lookup

The ipstack API also offers a separate API endpoint capable of detecting the IP address which the current API request is coming from.
In order to use this endpoint, simply append `check` to the API's base URL and specify your preferred optional parameters.

Note: The Requester IP Lookup endpoint returns the details of the IP address from where the request is coming from.
For example, if you make a request from the Postman web app, it will show the details of the Postman server,
but if you make a request from the Postman client app, it will show the details of your computer.

```java
CompletableFuture<IPLocation> getRequesterIPLookupAsync(
    final String accessKey,
    final HostnameEnum hostname,
    final String callback,
    final Language1Enum language,
    final String fields,
    final OutputEnum output)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accessKey` | `String` | Query, Required | Your API access key |
| `hostname` | [`HostnameEnum`](../../doc/models/hostname-enum.md) | Query, Optional | Set to 1 to see the Hostname |
| `callback` | `String` | Query, Optional | Response will be wrapped inside this function name (JSONP) |
| `language` | [`Language1Enum`](../../doc/models/language-1-enum.md) | Query, Optional | Set to a 2-letter language code to change output language.<br>Supported languages: en (English/US), de (German), es (Spanish), fr (French),<br>ja (Japanese), pt-br (Portuguese Brazil), ru (Russian), zh (Chinese) |
| `fields` | `String` | Query, Optional | Set to your preferred output field(s) |
| `output` | [`OutputEnum`](../../doc/models/output-enum.md) | Query, Optional | Set to json or xml to choose between output formats |

## Response Type

[`IPLocation`](../../doc/models/ip-location.md)

## Example Usage

```java
String accessKey = "access_key8";

requesterIPLookupController.getRequesterIPLookupAsync(accessKey, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response *(as JSON)*

```json
{
  "ip": "137.59.240.169",
  "type": "ipv4",
  "continent_code": "AS",
  "continent_name": "Asia",
  "country_code": "IN",
  "country_name": "India",
  "region_code": "DL",
  "region_name": "Delhi",
  "city": "New Delhi",
  "zip": "110001",
  "latitude": 28.635299682617188,
  "longitude": 77.2249984741211,
  "location": {
    "geoname_id": 1261481,
    "capital": "New Delhi",
    "languages": [
      {
        "code": "hi",
        "name": "Hindi",
        "native": "हिन्दी"
      },
      {
        "code": "en",
        "name": "English",
        "native": "English"
      }
    ],
    "country_flag": "https://assets.ipstack.com/flags/in.svg",
    "country_flag_emoji": "🇮🇳",
    "country_flag_emoji_unicode": "U+1F1EE U+1F1F3",
    "calling_code": "91",
    "is_eu": false
  },
  "time_zone": {
    "id": "Asia/Kolkata",
    "current_time": "2024-02-26T23:36:15+05:30",
    "gmt_offset": 19800,
    "code": "IST",
    "is_daylight_saving": false
  },
  "currency": {
    "code": "INR",
    "name": "Indian Rupee",
    "plural": "Indian rupees",
    "symbol": "Rs",
    "symbol_native": "টকা"
  },
  "connection": {
    "asn": 133275,
    "isp": "Gigantic Infotel Pvt Ltd"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request | [`ErrorException`](../../doc/models/error-exception.md) |
| 401 | Unauthorized - Invalid API key | [`ErrorException`](../../doc/models/error-exception.md) |
| 429 | Too many requests | `ApiException` |
| 500 | Internal server error | `ApiException` |

