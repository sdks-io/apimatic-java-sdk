# Docs Portal Management

```java
DocsPortalManagementController docsPortalManagementController = client.getDocsPortalManagementController();
```

## Class Name

`DocsPortalManagementController`


# Generate on-Prem Portal via Build Input

Generate an On-premise Documentation Portal by uploading a Portal Build Input. This endpoint generates all artifacts for the Portal and packages them together into a zip file along with the required HTML, CSS and JS files. The generated artifacts include:

1. SDKs
2. Docs
3. API Specification files

The endpoint returns a zip file that contains a static Site and can be hosted on any Web Server.

```java
CompletableFuture<ApiResponse<InputStream>> generateOnPremPortalViaBuildInputAsync(
    final ContentType contentType,
    final FileWrapper file,
    final Map<String, Object> queryParameters)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `contentType` | [`ContentType`](../../doc/models/content-type.md) | Header, Required | - |
| `file` | `FileWrapper` | Form, Required | The input file to the Portal Generator. Must contain the build file. |
| `queryParameters` | `Map<String, Object>` | Optional | Pass additional query parameters. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type `InputStream`.

## Example Usage

```java
ContentType contentType = ContentType.ENUM_MULTIPARTFORMDATA;
FileWrapper file = new FileWrapper(new File("dummy_file"), "optional-content-type");

Map<String, Object> queryParameters = new LinkedHashMap<String, Object>() {{
    put("key0", ApiHelper.deserialize("\"additionalQueryParams2\""));
}};

docsPortalManagementController.generateOnPremPortalViaBuildInputAsync(contentType, file, queryParameters).thenAccept(result -> {
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
| 403 | Subscription Issue | [`ProblemDetailsException`](../../doc/models/problem-details-exception.md) |
| 422 | Unprocessable Entity - Contains error.zip for build issues | `ApiException` |
| 500 | Internal Server Error | [`InternalServerErrorResponseException`](../../doc/models/internal-server-error-response-exception.md) |

