# Docs Portal Management

```java
DocsPortalManagementController docsPortalManagementController = client.getDocsPortalManagementController();
```

## Class Name

`DocsPortalManagementController`

## Methods

* [Publish Hosted Portal](../../doc/controllers/docs-portal-management.md#publish-hosted-portal)
* [Publish Embedded Portal](../../doc/controllers/docs-portal-management.md#publish-embedded-portal)
* [Generate on-Prem Portal via API Entity](../../doc/controllers/docs-portal-management.md#generate-on-prem-portal-via-api-entity)
* [Generate on-Prem Portal via Build Input](../../doc/controllers/docs-portal-management.md#generate-on-prem-portal-via-build-input)
* [Generate Build Input for Unpublished Portal](../../doc/controllers/docs-portal-management.md#generate-build-input-for-unpublished-portal)
* [Generate Build Input for Published Portal](../../doc/controllers/docs-portal-management.md#generate-build-input-for-published-portal)
* [Unpublish Portal](../../doc/controllers/docs-portal-management.md#unpublish-portal)


# Publish Hosted Portal

Publish artifacts for a Hosted Portal.

This endpoint regenerates all the artifacts for a hosted portal and uploads them to APIMatic's cloud storage, from where the Portal fetches them. These artifacts include:

1. SDKs
2. Docs
3. API Specification files

Call this endpoint to update your Hosted Portal after you update an API Entity via any of the Import API Endpoints.

__**Note: If you have an embedded portal against the same API Entity, artifacts for that portal will get updated as well.**__

```java
CompletableFuture<ApiResponse<Void>> publishHostedPortalAsync(
    final String apiEntityId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiEntityId` | `String` | Template, Required | The ID of the API Entity to update the portal artifacts for. |

## Response Type

**200**

`void`

## Example Usage

```java
String apiEntityId = "5f87f8ab9615d38a2eb990ca";

docsPortalManagementController.publishHostedPortalAsync(apiEntityId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Publish Embedded Portal

Publish artifacts for an Embedded Portal and get the Portal Embed script.

This endpoint regenerates all the artifacts for an embedded portal and uploads them to APIMatic's cloud storage, from where the Portal fetches them. These artifacts include:

1. SDKs
2. Docs
3. API Specification files

Call this endpoint to update your Embedded Portal after you update an API Entity via any of the Import API Endpoints. This endpoint returns the Portal Embed script in the response.

__**Note: If you have a hosted portal against the same API Entity, artifacts for that portal will get updated as well.**__

```java
CompletableFuture<ApiResponse<Void>> publishEmbeddedPortalAsync(
    final String apiEntityId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiEntityId` | `String` | Template, Required | The ID of the API Entity to update the portal artifacts for. |

## Response Type

**200**

`void`

## Example Usage

```java
String apiEntityId = "5f87f8ab9615d38a2eb990ca";

docsPortalManagementController.publishEmbeddedPortalAsync(apiEntityId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Generate on-Prem Portal via API Entity

Generate an On-premise Documentation Portal for an API Entity. This endpoint generates all artifacts for the Portal and packages them together into a zip file along with the required HTML, CSS and JS files. The generated artifacts include:

1. SDKs
2. Docs
3. API Specification files

The endpoint returns a zip file that contains a static Site and can be hosted on any Web Server.

```java
CompletableFuture<ApiResponse<Void>> generateOnPremPortalViaApiEntityAsync(
    final String apiEntityId,
    final Accept4 accept)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiEntityId` | `String` | Template, Required | The ID of the API Entity to generate the Portal for. |
| `accept` | [`Accept4`](../../doc/models/accept-4.md) | Header, Required | - |

## Response Type

**200**

`void`

## Example Usage

```java
String apiEntityId = "5f87f8ab9615d38a2eb990ca";
Accept4 accept = Accept4.ENUM_APPLICATIONZIP;

docsPortalManagementController.generateOnPremPortalViaApiEntityAsync(apiEntityId, accept).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


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


# Generate Build Input for Unpublished Portal

Generate Build Input for a Portal created using the UI workflow.  The Build Input will correspond to the draft version of the Portal i.e. unpublished changes will also be included.
This can be used to create a backup of your Portal or to migrate from the UI workflow to the docs as code workflow.

```java
CompletableFuture<ApiResponse<Object>> generateBuildInputForUnpublishedPortalAsync(
    final String apiGroupId,
    final List<String> apiEntities)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiGroupId` | `String` | Template, Required | - |
| `apiEntities` | `List<String>` | Query, Optional | - |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type `Object`.

## Example Usage

```java
String apiGroupId = "apiGroupId8";
docsPortalManagementController.generateBuildInputForUnpublishedPortalAsync(apiGroupId, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Generate Build Input for Published Portal

Generate Build Input for a Portal created using the UI workflow.  The Build Input will correspond to the published version of the Portal i.e. unpublished changes will not be inlcuded.
This can be used to create a backup of your Portal or to migrate from the UI workflow to the docs as code workflow.

```java
CompletableFuture<ApiResponse<Object>> generateBuildInputForPublishedPortalAsync(
    final String apiGroupId,
    final List<String> apiEntities)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiGroupId` | `String` | Template, Required | - |
| `apiEntities` | `List<String>` | Query, Optional | - |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type `Object`.

## Example Usage

```java
String apiGroupId = "apiGroupId8";
docsPortalManagementController.generateBuildInputForPublishedPortalAsync(apiGroupId, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Unpublish Portal

Unpublish a Hosted or Embedded Portal published for an API Entity. Calling this endpoint deletes all the published artifacts for a Portal from APIMatic's cloud storage.

In case of a Hosted Portal, to completely remove the Portal, this endpoint needs to be called against all API versions that the Portal hosts.

In case of an Embedded Portal, to completely remove the Portal, the user needs to manually remove the Portal Embed script from the embedding site.

```java
CompletableFuture<ApiResponse<Void>> unpublishPortalAsync(
    final String apiEntityId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiEntityId` | `String` | Template, Required | The ID of the API Entity to unpublish the Portal artifacts for. |

## Response Type

**200**

`void`

## Example Usage

```java
String apiEntityId = "5f87f8ab9615d38a2eb990ca";

docsPortalManagementController.unpublishPortalAsync(apiEntityId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

