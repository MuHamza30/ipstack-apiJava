
# Custom Query Parameter



Documentation for accessing and setting credentials for apiKeyAuth.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| access_key | `String` | You can get your API key by signing up at https://ipstack.com | `accessKey` | `getAccessKey()` |



**Note:** Auth credentials can be set using `customQueryAuthenticationCredentials` in the client builder and accessed through `getCustomQueryAuthenticationCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```java
import com.ipstack.api.IPstackAPIClient;
import com.ipstack.api.authentication.CustomQueryAuthenticationModel;

IPstackAPIClient client = new IPstackAPIClient.Builder()
    .customQueryAuthenticationCredentials(new CustomQueryAuthenticationModel.Builder(
            "access_key"
        )
        .build())
    .build();
```


