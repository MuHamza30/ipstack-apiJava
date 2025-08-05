
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| httpClientConfig | [`Consumer<HttpClientConfiguration.Builder>`](../doc/http-client-configuration-builder.md) | Set up Http Client Configuration instance. |
| customQueryAuthenticationCredentials | [`CustomQueryAuthenticationCredentials`](auth/custom-query-parameter.md) | The Credentials Setter for Custom Query Parameter |

The API client can be initialized as follows:

```java
import com.ipstack.api.IPstackAPIClient;
import com.ipstack.api.authentication.CustomQueryAuthenticationModel;
import com.ipstack.api.exceptions.ApiException;
import java.io.IOException;

IPstackAPIClient client = new IPstackAPIClient.Builder()
    .httpClientConfig(configBuilder -> configBuilder
            .timeout(0))
    .customQueryAuthenticationCredentials(new CustomQueryAuthenticationModel.Builder(
            "access_key"
        )
        .build())
    .build();
```

## IPstack APIClient Class

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

### Controllers

| Name | Description | Return Type |
|  --- | --- | --- |
| `getStandardIPLookupController()` | Provides access to StandardIPLookup controller. | `StandardIPLookupController` |
| `getBulkIPLookupController()` | Provides access to BulkIPLookup controller. | `BulkIPLookupController` |
| `getRequesterIPLookupController()` | Provides access to RequesterIPLookup controller. | `RequesterIPLookupController` |

### Methods

| Name | Description | Return Type |
|  --- | --- | --- |
| `shutdown()` | Shutdown the underlying HttpClient instance. | `void` |
| `getEnvironment()` | Current API environment. | `Environment` |
| `getHttpClient()` | The HTTP Client instance to use for making HTTP requests. | `HttpClient` |
| `getHttpClientConfig()` | Http Client Configuration instance. | [`ReadonlyHttpClientConfiguration`](../doc/http-client-configuration.md) |
| `getCustomQueryAuthenticationCredentials()` | The credentials to use with CustomQueryAuthentication. | [`CustomQueryAuthenticationCredentials`](auth/custom-query-parameter.md) |
| `getBaseUri(Server server)` | Get base URI by current environment | `String` |
| `getBaseUri()` | Get base URI by current environment | `String` |

