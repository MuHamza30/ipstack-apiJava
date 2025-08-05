
# IP Location

## Structure

`IPLocation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Ip` | `String` | Optional | The IP address | String getIp() | setIp(String ip) |
| `Type` | `String` | Optional | The type of IP address (ipv4 or ipv6) | String getType() | setType(String type) |
| `ContinentCode` | `String` | Optional | The continent code | String getContinentCode() | setContinentCode(String continentCode) |
| `ContinentName` | `String` | Optional | The continent name | String getContinentName() | setContinentName(String continentName) |
| `CountryCode` | `String` | Optional | The country code | String getCountryCode() | setCountryCode(String countryCode) |
| `CountryName` | `String` | Optional | The country name | String getCountryName() | setCountryName(String countryName) |
| `RegionCode` | `String` | Optional | The region code | String getRegionCode() | setRegionCode(String regionCode) |
| `RegionName` | `String` | Optional | The region name | String getRegionName() | setRegionName(String regionName) |
| `City` | `String` | Optional | The city name | String getCity() | setCity(String city) |
| `Zip` | `String` | Optional | The ZIP code | String getZip() | setZip(String zip) |
| `Latitude` | `Double` | Optional | The latitude | Double getLatitude() | setLatitude(Double latitude) |
| `Longitude` | `Double` | Optional | The longitude | Double getLongitude() | setLongitude(Double longitude) |
| `Location` | [`Location`](../../doc/models/location.md) | Optional | - | Location getLocation() | setLocation(Location location) |
| `TimeZone` | [`TimeZone`](../../doc/models/time-zone.md) | Optional | - | TimeZone getTimeZone() | setTimeZone(TimeZone timeZone) |
| `Currency` | [`Currency`](../../doc/models/currency.md) | Optional | - | Currency getCurrency() | setCurrency(Currency currency) |
| `Connection` | [`Connection`](../../doc/models/connection.md) | Optional | - | Connection getConnection() | setConnection(Connection connection) |
| `Hostname` | `String` | Optional | The hostname (when hostname=1 parameter is used) | String getHostname() | setHostname(String hostname) |

## Example (as JSON)

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
  "longitude": -118.240539550781,
  "hostname": "160.39.144.19"
}
```

