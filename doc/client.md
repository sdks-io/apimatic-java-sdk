
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| userAgent | `String` |  |
| customUrl | `String` | The testing domain for the API<br>*Default*: `"https://localhost:44301/api"` |
| environment | [`Environment`](../README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| httpClientConfig | [`Consumer<HttpClientConfiguration.Builder>`](../doc/http-client-configuration-builder.md) | Set up Http Client Configuration instance. |
| loggingConfig | [`Consumer<ApiLoggingConfiguration.Builder>`](../doc/api-logging-configuration-builder.md) | Set up Logging Configuration instance. |
| customHeaderAuthenticationCredentials | [`CustomHeaderAuthenticationCredentials`](auth/custom-header-signature.md) | The Credentials Setter for Custom Header Signature |

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

## Apimatic APIClient Class

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

### Controllers

| Name | Description | Return Type |
|  --- | --- | --- |
| `getCodeGenerationExternalApisController()` | Provides access to CodeGenerationExternalApis controller. | `CodeGenerationExternalApisController` |
| `getTransformationController()` | Provides access to Transformation controller. | `TransformationController` |
| `getDocsPortalManagementController()` | Provides access to DocsPortalManagement controller. | `DocsPortalManagementController` |
| `getDocsPortalGenerationAsyncController()` | Provides access to DocsPortalGenerationAsync controller. | `DocsPortalGenerationAsyncController` |
| `getApiValidationExternalApisController()` | Provides access to ApiValidationExternalApis controller. | `ApiValidationExternalApisController` |
| `getApiValidationV2ExternalApisController()` | Provides access to ApiValidationV2ExternalApis controller. | `ApiValidationV2ExternalApisController` |
| `getSdkGenerationAsyncController()` | Provides access to SdkGenerationAsync controller. | `SdkGenerationAsyncController` |

### Methods

| Name | Description | Return Type |
|  --- | --- | --- |
| `shutdown()` | Shutdown the underlying HttpClient instance. | `void` |
| `getEnvironment()` | Current API environment. | `Environment` |
| `getCustomUrl()` | The testing domain for the API | `String` |
| `getUserAgent()` | . | `String` |
| `getHttpClient()` | The HTTP Client instance to use for making HTTP requests. | `HttpClient` |
| `getHttpClientConfig()` | Http Client Configuration instance. | [`ReadonlyHttpClientConfiguration`](../doc/http-client-configuration.md) |
| `getLoggingConfig()` | Logging Configuration instance. | [`ReadonlyLoggingConfiguration`](../doc/api-logging-configuration.md) |
| `getCustomHeaderAuthenticationCredentials()` | The credentials to use with CustomHeaderAuthentication. | [`CustomHeaderAuthenticationCredentials`](auth/custom-header-signature.md) |
| `getBaseUri(Server server)` | Get base URI by current environment | `String` |
| `getBaseUri()` | Get base URI by current environment | `String` |

