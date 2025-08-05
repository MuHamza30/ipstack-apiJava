# Standard IP Lookup

```java
StandardIPLookupController standardIPLookupController = client.getStandardIPLookupController();
```

## Class Name

`StandardIPLookupController`


# Get Standard IP Lookup

This is the prime endpoint of IPstack API and used to look up single IPv4 or IPv6 addresses.
To call this endpoint, simply attach any IPv4 or IPv6 address to the API's base URL.

```java
CompletableFuture<IPLocation> getStandardIPLookupAsync(
    final String ip,
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
| `ip` | `String` | Template, Required | The IP address to lookup (IPv4 or IPv6) |
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
String ip = "134.201.250.155";
String accessKey = "access_key8";

standardIPLookupController.getStandardIPLookupAsync(ip, accessKey, null, null, null, null, null).thenAccept(result -> {
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
  "ip": "134.201.250.155",
  "type": "ipv4",
  "continent_code": "NA",
  "continent_name": "North America",
  "country_code": "US",
  "country_name": "United States",
  "region_code": "CA",
  "region_name": "California",
  "city": "Los Angeles",
  "zip": "90012",
  "latitude": 34.0655517578125,
  "longitude": -118.24053955078125,
  "location": {
    "geoname_id": 5368361,
    "capital": "Washington D.C.",
    "languages": [
      {
        "code": "en",
        "name": "English",
        "native": "English"
      }
    ],
    "country_flag": "https://assets.ipstack.com/flags/us.svg",
    "country_flag_emoji": "🇺🇸",
    "country_flag_emoji_unicode": "U+1F1FA U+1F1F8",
    "calling_code": "1",
    "is_eu": false
  },
  "time_zone": {
    "id": "America/Los_Angeles",
    "current_time": "2024-02-15T05:07:34-08:00",
    "gmt_offset": -28800,
    "code": "PST",
    "is_daylight_saving": false
  },
  "currency": {
    "code": "USD",
    "name": "US Dollar",
    "plural": "US dollars",
    "symbol": "$",
    "symbol_native": "$"
  },
  "connection": {
    "asn": 25876,
    "isp": "Los Angeles Department of Water & Power"
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

