# Bulk IP Lookup

```java
BulkIPLookupController bulkIPLookupController = client.getBulkIPLookupController();
```

## Class Name

`BulkIPLookupController`


# Get Bulk IP Lookup

The ipstack API offers the ability to request data for multiple IPv4 or IPv6 addresses at the same time.
In order to process IP addresses in bulk, simply append multiple comma-separated IP addresses to the API's base URL.

Note: Bulk IP Lookup Endpoint is only available to users who are on the Professional plan or above.

```java
CompletableFuture<List<IPLocation>> getBulkIPLookupAsync(
    final String ips,
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
| `ips` | `String` | Template, Required | Comma-separated list of IP addresses to lookup |
| `accessKey` | `String` | Query, Required | Your API access key |
| `hostname` | [`HostnameEnum`](../../doc/models/hostname-enum.md) | Query, Optional | Set to 1 to see the Hostname |
| `callback` | `String` | Query, Optional | Response will be wrapped inside this function name (JSONP) |
| `language` | [`Language1Enum`](../../doc/models/language-1-enum.md) | Query, Optional | Set to a 2-letter language code to change output language.<br>Supported languages: en (English/US), de (German), es (Spanish), fr (French),<br>ja (Japanese), pt-br (Portuguese Brazil), ru (Russian), zh (Chinese) |
| `fields` | `String` | Query, Optional | Set to your preferred output field(s) |
| `output` | [`OutputEnum`](../../doc/models/output-enum.md) | Query, Optional | Set to json or xml to choose between output formats |

## Response Type

[`List<IPLocation>`](../../doc/models/ip-location.md)

## Example Usage

```java
String ips = "72.229.28.185,110.174.165.78";
String accessKey = "access_key8";

bulkIPLookupController.getBulkIPLookupAsync(ips, accessKey, null, null, null, null, null).thenAccept(result -> {
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
[
  {
    "ip": "72.229.28.185",
    "hostname": "072-229-028-185.res.spectrum.com",
    "type": "ipv4",
    "continent_code": "NA",
    "continent_name": "North America",
    "country_code": "US",
    "country_name": "United States",
    "region_code": "NY",
    "region_name": "New York",
    "city": "Manhattan",
    "zip": "10020",
    "latitude": 40.7589111328125,
    "longitude": -73.97901916503906,
    "location": {
      "geoname_id": 5125771,
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
      "id": "America/New_York",
      "current_time": "2024-02-26T12:38:37-05:00",
      "gmt_offset": -18000,
      "code": "EST",
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
      "asn": 12271,
      "isp": "Charter Communications Inc"
    }
  },
  {
    "ip": "110.174.165.78",
    "hostname": "110-174-165-78.static.tpgi.com.au",
    "type": "ipv4",
    "continent_code": "OC",
    "continent_name": "Oceania",
    "country_code": "AU",
    "country_name": "Australia",
    "region_code": "NSW",
    "region_name": "New South Wales",
    "city": "Sydney",
    "zip": "1210",
    "latitude": -33.87070083618164,
    "longitude": 151.20680236816406,
    "location": {
      "geoname_id": 2147714,
      "capital": "Canberra",
      "languages": [
        {
          "code": "en",
          "name": "English",
          "native": "English"
        }
      ],
      "country_flag": "https://assets.ipstack.com/flags/au.svg",
      "country_flag_emoji": "🇦🇺",
      "country_flag_emoji_unicode": "U+1F1E6 U+1F1FA",
      "calling_code": "61",
      "is_eu": false
    },
    "time_zone": {
      "id": "Australia/Sydney",
      "current_time": "2024-02-27T04:38:37+11:00",
      "gmt_offset": 39600,
      "code": "AEDT",
      "is_daylight_saving": true
    },
    "currency": {
      "code": "AUD",
      "name": "Australian Dollar",
      "plural": "Australian dollars",
      "symbol": "AU$",
      "symbol_native": "$"
    },
    "connection": {
      "asn": 7545,
      "isp": "Tpg Telecom Limited"
    }
  }
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request | [`ErrorException`](../../doc/models/error-exception.md) |
| 401 | Unauthorized - Invalid API key | [`ErrorException`](../../doc/models/error-exception.md) |
| 429 | Too many requests | `ApiException` |
| 500 | Internal server error | `ApiException` |

