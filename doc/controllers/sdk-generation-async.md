# SDK Generation-Async

```java
SdkGenerationAsyncController sdkGenerationAsyncController = client.getSdkGenerationAsyncController();
```

## Class Name

`SdkGenerationAsyncController`

## Methods

* [Generate SDK via Build Input Async](../../doc/controllers/sdk-generation-async.md#generate-sdk-via-build-input-async)
* [Get SDK Generation Status](../../doc/controllers/sdk-generation-async.md#get-sdk-generation-status)
* [Download Generated SDK](../../doc/controllers/sdk-generation-async.md#download-generated-sdk)


# Generate SDK via Build Input Async

Create an async SDK Generation request by providing a Build Input

```java
CompletableFuture<ApiResponse<SdkGenerationAsyncResponse>> generateSdkViaBuildInputAsyncAsync(
    final ContentType contentType,
    final FileWrapper file,
    final SdkLanguages language,
    final String xApiMaticCallbackUrl)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `contentType` | [`ContentType`](../../doc/models/content-type.md) | Header, Required | - |
| `file` | `FileWrapper` | Form, Required | The input file to the SDK Generator. Must contain the build file or a spec folder containing the API Specification. |
| `language` | [`SdkLanguages`](../../doc/models/sdk-languages.md) | Form, Required | Languages for which SDKs can be generated. |
| `xApiMaticCallbackUrl` | `String` | Header, Optional | Optional header containing callback url. This url will be called by the server once the SDK generation completes |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`SdkGenerationAsyncResponse`](../../doc/models/sdk-generation-async-response.md).

## Example Usage

```java
ContentType contentType = ContentType.ENUM_MULTIPARTFORMDATA;
FileWrapper file = new FileWrapper(new File("dummy_file"), "optional-content-type");
SdkLanguages language = SdkLanguages.CSHARP;

sdkGenerationAsyncController.generateSdkViaBuildInputAsyncAsync(contentType, file, language, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ProblemDetailsException) {
        ProblemDetailsException problemDetailsException = (ProblemDetailsException) cause;
        problemDetailsException.printStackTrace();
    } else if (cause instanceof UnauthorizedResponseException) {
        UnauthorizedResponseException unauthorizedResponseException = (UnauthorizedResponseException) cause;
        unauthorizedResponseException.printStackTrace();
    } else if (cause instanceof InternalServerErrorResponseException) {
        InternalServerErrorResponseException internalServerErrorResponseException = (InternalServerErrorResponseException) cause;
        internalServerErrorResponseException.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Example Response *(as JSON)*

```json
{
  "id": "0194d0da-8d75-7c04-b517-6a9342b114e8",
  "links": {
    "status": "https://api.apimatic.io/sdk/0194d0da-8d75-7c04-b517-6a9342b114e8/status",
    "download": "https://api.apimatic.io/sdk/0194d0da-8d75-7c04-b517-6a9342b114e8/download"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ProblemDetailsException`](../../doc/models/problem-details-exception.md) |
| 401 | Unauthorized | [`UnauthorizedResponseException`](../../doc/models/unauthorized-response-exception.md) |
| 500 | Internal Server Error | [`InternalServerErrorResponseException`](../../doc/models/internal-server-error-response-exception.md) |


# Get SDK Generation Status

Get the status of an SDK generation request

```java
CompletableFuture<ApiResponse<SdkGenerationStatusResponse>> getSdkGenerationStatusAsync(
    final String id)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | - |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`SdkGenerationStatusResponse`](../../doc/models/sdk-generation-status-response.md).

## Example Usage

```java
String id = "id0";

sdkGenerationAsyncController.getSdkGenerationStatusAsync(id).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ProblemDetailsException) {
        ProblemDetailsException problemDetailsException = (ProblemDetailsException) cause;
        problemDetailsException.printStackTrace();
    } else if (cause instanceof UnauthorizedResponseException) {
        UnauthorizedResponseException unauthorizedResponseException = (UnauthorizedResponseException) cause;
        unauthorizedResponseException.printStackTrace();
    } else if (cause instanceof InternalServerErrorResponseException) {
        InternalServerErrorResponseException internalServerErrorResponseException = (InternalServerErrorResponseException) cause;
        internalServerErrorResponseException.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Example Response *(as JSON)*

```json
{
  "status": "InProgress"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ProblemDetailsException`](../../doc/models/problem-details-exception.md) |
| 401 | Unauthorized | [`UnauthorizedResponseException`](../../doc/models/unauthorized-response-exception.md) |
| 500 | Internal Server Error | [`InternalServerErrorResponseException`](../../doc/models/internal-server-error-response-exception.md) |


# Download Generated SDK

Downloads the SDK artifacts. The endpoint returns a zip file containing the generated SDK.

```java
CompletableFuture<ApiResponse<InputStream>> downloadGeneratedSdkAsync(
    final String id)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | - |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type `InputStream`.

## Example Usage

```java
String id = "id0";

sdkGenerationAsyncController.downloadGeneratedSdkAsync(id).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ProblemDetailsException) {
        ProblemDetailsException problemDetailsException = (ProblemDetailsException) cause;
        problemDetailsException.printStackTrace();
    } else if (cause instanceof UnauthorizedResponseException) {
        UnauthorizedResponseException unauthorizedResponseException = (UnauthorizedResponseException) cause;
        unauthorizedResponseException.printStackTrace();
    } else if (cause instanceof InternalServerErrorResponseException) {
        InternalServerErrorResponseException internalServerErrorResponseException = (InternalServerErrorResponseException) cause;
        internalServerErrorResponseException.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ProblemDetailsException`](../../doc/models/problem-details-exception.md) |
| 401 | Unauthorized | [`UnauthorizedResponseException`](../../doc/models/unauthorized-response-exception.md) |
| 500 | Internal Server Error | [`InternalServerErrorResponseException`](../../doc/models/internal-server-error-response-exception.md) |

