
# Currency

## Structure

`Currency`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Code` | `String` | Optional | The currency code | String getCode() | setCode(String code) |
| `Name` | `String` | Optional | The currency name | String getName() | setName(String name) |
| `Plural` | `String` | Optional | The currency plural form | String getPlural() | setPlural(String plural) |
| `Symbol` | `String` | Optional | The currency symbol | String getSymbol() | setSymbol(String symbol) |
| `SymbolNative` | `String` | Optional | The native currency symbol | String getSymbolNative() | setSymbolNative(String symbolNative) |

## Example (as JSON)

```json
{
  "code": "USD",
  "name": "US Dollar",
  "plural": "US dollars",
  "symbol": "$",
  "symbol_native": "$"
}
```

