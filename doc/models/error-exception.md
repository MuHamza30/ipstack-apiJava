
# Error Exception

## Structure

`ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Success` | `Boolean` | Optional | - | Boolean getSuccess() | setSuccess(Boolean success) |
| `Error` | [`Error1`](../../doc/models/error-1.md) | Optional | - | Error1 getError() | setError(Error1 error) |

## Example (as JSON)

```json
{
  "success": false,
  "error": {
    "code": 24,
    "type": "type6",
    "info": "info4"
  }
}
```

