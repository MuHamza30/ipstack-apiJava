
# Location

## Structure

`Location`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `GeonameId` | `Integer` | Optional | The geoname ID | Integer getGeonameId() | setGeonameId(Integer geonameId) |
| `Capital` | `String` | Optional | The capital city | String getCapital() | setCapital(String capital) |
| `Languages` | [`List<Language>`](../../doc/models/language.md) | Optional | - | List<Language> getLanguages() | setLanguages(List<Language> languages) |
| `CountryFlag` | `String` | Optional | URL to the country flag | String getCountryFlag() | setCountryFlag(String countryFlag) |
| `CountryFlagEmoji` | `String` | Optional | The country flag emoji | String getCountryFlagEmoji() | setCountryFlagEmoji(String countryFlagEmoji) |
| `CountryFlagEmojiUnicode` | `String` | Optional | The country flag emoji unicode | String getCountryFlagEmojiUnicode() | setCountryFlagEmojiUnicode(String countryFlagEmojiUnicode) |
| `CallingCode` | `String` | Optional | The calling code | String getCallingCode() | setCallingCode(String callingCode) |
| `IsEu` | `Boolean` | Optional | Whether the country is in the EU | Boolean getIsEu() | setIsEu(Boolean isEu) |

## Example (as JSON)

```json
{
  "geoname_id": 5368361,
  "capital": "Washington D.C.",
  "country_flag": "https://assets.ipstack.com/flags/us.svg",
  "country_flag_emoji": "🇺🇸",
  "country_flag_emoji_unicode": "U+1F1FA U+1F1F8",
  "calling_code": "1",
  "is_eu": false,
  "languages": [
    {
      "code": "code0",
      "name": "name2",
      "native": "native6"
    },
    {
      "code": "code0",
      "name": "name2",
      "native": "native6"
    },
    {
      "code": "code0",
      "name": "name2",
      "native": "native6"
    }
  ]
}
```

