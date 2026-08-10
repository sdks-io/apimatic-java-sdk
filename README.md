
# Getting Started with Apimatic API

## Introduction

This API gives you programmatic access to APIMatic's Code Generation, Docs Generation and Transformation Engine

## Install the Package

Install the SDK by adding the following dependency in your project's pom.xml file:

```xml
<dependency>
  <groupId>io.sdks</groupId>
  <artifactId>sdks-io-apimatic</artifactId>
  <version>3.0.1</version>
</dependency>
```

You can also view the package at:
https://central.sonatype.com/artifact/io.sdks/sdks-io-apimatic/3.0.1

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| userAgent | `String` |  |
| customUrl | `String` | The testing domain for the API<br>*Default*: `"https://localhost:44301/api"` |
| environment | [`Environment`](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| httpClientConfig | [`Consumer<HttpClientConfiguration.Builder>`](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/http-client-configuration-builder.md) | Set up Http Client Configuration instance. |
| loggingConfig | [`Consumer<ApiLoggingConfiguration.Builder>`](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/api-logging-configuration-builder.md) | Set up Logging Configuration instance. |
| customHeaderAuthenticationCredentials | [`CustomHeaderAuthenticationCredentials`](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/auth/custom-header-signature.md) | The Credentials Setter for Custom Header Signature |

The API client can be initialized as follows:

```java
import io.apimatic.api.ApimaticApiClient;
import io.apimatic.api.Environment;
import io.apimatic.api.authentication.CustomHeaderAuthenticationModel;
import io.apimatic.api.exceptions.ApiException;
import io.apimatic.api.http.response.ApiResponse;
import org.slf4j.event.Level;

public class Program {
    public static void main(String[] args) {
        ApimaticApiClient client = new ApimaticApiClient.Builder()
            .loggingConfig(builder -> builder
                    .level(Level.DEBUG)
                    .requestConfig(logConfigBuilder -> logConfigBuilder.body(true))
                    .responseConfig(logConfigBuilder -> logConfigBuilder.headers(true)))
            .httpClientConfig(configBuilder -> configBuilder
                    .timeout(0))
            .userAgent("user-agent")
            .customHeaderAuthenticationCredentials(new CustomHeaderAuthenticationModel.Builder(
                    "Authorization"
                )
                .build())
            .environment(Environment.PRODUCTION)
            .customUrl("https://localhost:44301/api")
            .build();

    }
}
```

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| PRODUCTION | **Default** |
| TESTING | - |

## Authorization

This API uses the following authentication schemes.

* [`Authorization (Custom Header Signature)`](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/auth/custom-header-signature.md)

## List of APIs

* [Code Generation-External APIs](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/controllers/code-generation-external-apis.md)
* [Docs Portal Management](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/controllers/docs-portal-management.md)
* [Docs Portal Generation-Async](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/controllers/docs-portal-generation-async.md)
* [API Validation-External APIs](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/controllers/api-validation-external-apis.md)
* [API Validation V2-External APIs](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/controllers/api-validation-v2-external-apis.md)
* [SDK Generation-Async](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/controllers/sdk-generation-async.md)
* [Transformation](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/controllers/transformation.md)

## SDK Infrastructure

### Configuration

* [ApiLoggingConfiguration](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/api-logging-configuration.md)
* [ApiLoggingConfiguration.Builder](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/api-logging-configuration-builder.md)
* [ApiRequestLoggingConfiguration.Builder](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/api-request-logging-configuration-builder.md)
* [ApiResponseLoggingConfiguration.Builder](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/api-response-logging-configuration-builder.md)
* [Configuration Interface](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/configuration-interface.md)
* [HttpClientConfiguration](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/http-client-configuration.md)
* [HttpClientConfiguration.Builder](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/http-client-configuration-builder.md)
* [HttpProxyConfiguration](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/http-proxy-configuration.md)
* [HttpProxyConfiguration.Builder](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/http-proxy-configuration-builder.md)

### HTTP

* [Headers](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/headers.md)
* [HttpCallback Interface](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/http-callback-interface.md)
* [HttpContext](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/http-context.md)
* [HttpBodyRequest](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/http-body-request.md)
* [HttpRequest](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/http-request.md)
* [HttpResponse](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/http-response.md)
* [HttpStringResponse](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/http-string-response.md)

### Utilities

* [ApiException](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/api-exception.md)
* [ApiResponse](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/api-response.md)
* [ApiHelper](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/api-helper.md)
* [FileWrapper](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/file-wrapper.md)
* [DateTimeHelper](https://www.github.com/sdks-io/apimatic-java-sdk/tree/3.0.1/doc/date-time-helper.md)

