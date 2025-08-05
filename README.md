
# Getting Started with IPstack API

## Introduction

### **Quickstart Guide**

#### Step 1: Get your API Access Key

1. Go to the [IP Stack](https://ipstack.com/?utm_source=Postman&utm_medium=Referral) website and choose the right subscription plan for your particular project.
2. Get your personal API Access Key on the [Dashboard](https://ipstack.com/dashboard) to authenticate with the API. Keep it safe! You can reset it at any time in your Account Dashboard.

### Step 2: Make your first API call

IP Stack API contains all the three endpoint supported by IP Stack API.

1. Standard IP Lookup
2. Bulk IP Lookup
3. Requester Lookup

We recommend you to start with the Standard IP Lookup endpoint as it's primary endpoint. It is used to look up single IPv4 or IPv6 addresses. To call this endpoint, simply attach any IPv4 or IPv6 address to the API's base URL.

Check out all the widely used API calls with the necessary parameters in the Standard IP Lookup section.

## Install the Package

Install the SDK by adding the following dependency in your project's pom.xml file:

```xml
<dependency>
  <groupId>io.apimatic</groupId>
  <artifactId>ipstack-java-sdk</artifactId>
  <version>1.0.0</version>
</dependency>
```

You can also view the package at:
https://central.sonatype.com/artifact/io.apimatic/ipstack-java-sdk/1.0.0

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| httpClientConfig | [`Consumer<HttpClientConfiguration.Builder>`](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/http-client-configuration-builder.md) | Set up Http Client Configuration instance. |
| customQueryAuthenticationCredentials | [`CustomQueryAuthenticationCredentials`](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/auth/custom-query-parameter.md) | The Credentials Setter for Custom Query Parameter |

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

## Authorization

This API uses the following authentication schemes.

* [`apiKeyAuth (Custom Query Parameter)`](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/auth/custom-query-parameter.md)

## List of APIs

* [Standard IP Lookup](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/controllers/standard-ip-lookup.md)
* [Bulk IP Lookup](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/controllers/bulk-ip-lookup.md)
* [Requester IP Lookup](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/controllers/requester-ip-lookup.md)

## SDK Infrastructure

### Configuration

* [Configuration Interface](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/configuration-interface.md)
* [HttpClientConfiguration](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/http-client-configuration.md)
* [HttpClientConfiguration.Builder](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/http-client-configuration-builder.md)

### HTTP

* [Headers](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/headers.md)
* [HttpCallback Interface](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/http-callback-interface.md)
* [HttpContext](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/http-context.md)
* [HttpBodyRequest](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/http-body-request.md)
* [HttpRequest](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/http-request.md)
* [HttpResponse](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/http-response.md)
* [HttpStringResponse](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/http-string-response.md)

### Utilities

* [ApiException](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/api-exception.md)
* [ApiHelper](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/api-helper.md)
* [FileWrapper](https://www.github.com/MuHamza30/ipstack-apiJava/tree/1.0.0/doc/file-wrapper.md)

