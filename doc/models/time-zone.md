
# Time Zone

## Structure

`TimeZone`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Optional | The timezone ID | String getId() | setId(String id) |
| `CurrentTime` | `String` | Optional | The current time in the timezone | String getCurrentTime() | setCurrentTime(String currentTime) |
| `GmtOffset` | `Integer` | Optional | The GMT offset in seconds | Integer getGmtOffset() | setGmtOffset(Integer gmtOffset) |
| `Code` | `String` | Optional | The timezone code | String getCode() | setCode(String code) |
| `IsDaylightSaving` | `Boolean` | Optional | Whether daylight saving is active | Boolean getIsDaylightSaving() | setIsDaylightSaving(Boolean isDaylightSaving) |

## Example (as JSON)

```json
{
  "id": "America/Los_Angeles",
  "current_time": "02/15/2024 13:07:34",
  "gmt_offset": -28800,
  "code": "PST",
  "is_daylight_saving": false
}
```

