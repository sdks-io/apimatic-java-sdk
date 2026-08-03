# Docs Portal Generation-Async

```java
DocsPortalGenerationAsyncController docsPortalGenerationAsyncController = client.getDocsPortalGenerationAsyncController();
```

## Class Name

`DocsPortalGenerationAsyncController`

## Methods

* [Generate on-Prem Portal via Build Input Async](../../doc/controllers/docs-portal-generation-async.md#generate-on-prem-portal-via-build-input-async)
* [Get Portal Generation Status](../../doc/controllers/docs-portal-generation-async.md#get-portal-generation-status)
* [Download Generated Portal](../../doc/controllers/docs-portal-generation-async.md#download-generated-portal)


# Generate on-Prem Portal via Build Input Async

Create an async On-premise Documentation Portal Generation request by providing a Portal Build Input

```java
CompletableFuture<ApiResponse<PortalGenerationAsyncResponse>> generateOnPremPortalViaBuildInputAsyncAsync(
    final ContentType contentType,
    final FileWrapper file,
    final String xApiMaticCallbackUrl)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `contentType` | [`ContentType`](../../doc/models/content-type.md) | Header, Required | - |
| `file` | `FileWrapper` | Form, Required | The input file to the Portal Generator. Must contain the build file. |
| `xApiMaticCallbackUrl` | `String` | Header, Optional | Optional header containing callback url. This url will be called by the server once the portal generation completes |

## Response Type

**202**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`PortalGenerationAsyncResponse`](../../doc/models/portal-generation-async-response.md).

## Example Usage

```java
ContentType contentType = ContentType.ENUM_MULTIPARTFORMDATA;
FileWrapper file = new FileWrapper(new File("dummy_file"), "optional-content-type");

docsPortalGenerationAsyncController.generateOnPremPortalViaBuildInputAsyncAsync(contentType, file, null).thenAccept(result -> {
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
    "status": "https://api.apimatic.io/portal/v2/0194d0da-8d75-7c04-b517-6a9342b114e8/status",
    "download": "https://api.apimatic.io/portal/v2/0194d0da-8d75-7c04-b517-6a9342b114e8/download"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ProblemDetailsException`](../../doc/models/problem-details-exception.md) |
| 401 | Unauthorized | [`UnauthorizedResponseException`](../../doc/models/unauthorized-response-exception.md) |
| 500 | Internal Server Error | [`InternalServerErrorResponseException`](../../doc/models/internal-server-error-response-exception.md) |


# Get Portal Generation Status

Get the status of a portal generation request

```java
CompletableFuture<ApiResponse<PortalGenerationStatusResponse>> getPortalGenerationStatusAsync(
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`PortalGenerationStatusResponse`](../../doc/models/portal-generation-status-response.md).

## Example Usage

```java
String id = "id0";

docsPortalGenerationAsyncController.getPortalGenerationStatusAsync(id).thenAccept(result -> {
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


# Download Generated Portal

Downloads the portal artifacts. The generated artifacts include:

1. SDKs

2. Docs

3. API Specification files

The endpoint returns a zip file that contains a static Site and can be hosted on any Web Server.

```java
CompletableFuture<ApiResponse<InputStream>> downloadGeneratedPortalAsync(
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

docsPortalGenerationAsyncController.downloadGeneratedPortalAsync(id).thenAccept(result -> {
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
| 422 | Unprocessable Entity - Contains error.zip for build issues | `ApiException` |
| 500 | Internal Server Error | [`InternalServerErrorResponseException`](../../doc/models/internal-server-error-response-exception.md) |

