# APIs Management

```java
ApisManagementController apisManagementController = client.getApisManagementController();
```

## Class Name

`ApisManagementController`

## Methods

* [Import API via File](../../doc/controllers/apis-management.md#import-api-via-file)
* [Import API via URL](../../doc/controllers/apis-management.md#import-api-via-url)
* [Import New API Version via File](../../doc/controllers/apis-management.md#import-new-api-version-via-file)
* [Import New API Version via URL](../../doc/controllers/apis-management.md#import-new-api-version-via-url)
* [Inplace API Import via File](../../doc/controllers/apis-management.md#inplace-api-import-via-file)
* [Inplace API Import via URL](../../doc/controllers/apis-management.md#inplace-api-import-via-url)
* [Fetch API Entity](../../doc/controllers/apis-management.md#fetch-api-entity)
* [Download API Specification](../../doc/controllers/apis-management.md#download-api-specification)


# Import API via File

Import an API into the APIMatic Dashboard by uploading the API specification file.

You can also specify [API Metadata](https://docs.apimatic.io/manage-apis/apimatic-metadata) while importing the API using this endpoint. When specifying Metadata, the uploaded file will be a zip file containing the API specification file and the `APIMATIC-META` json file.

```java
CompletableFuture<ApiResponse<ApiEntity>> importApiViaFileAsync(
    final ContentType contentType,
    final FileWrapper file)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `contentType` | [`ContentType`](../../doc/models/content-type.md) | Header, Required | - |
| `file` | `FileWrapper` | Form, Required | The API specification file.<br>The type of the specification file should be any of the [supported formats](https://docs.apimatic.io/api-transformer/overview-transformer#supported-input-formats). |

## Response Type

**201**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ApiEntity`](../../doc/models/api-entity.md).

## Example Usage

```java
ContentType contentType = ContentType.ENUM_MULTIPARTFORMDATA;
FileWrapper file = new FileWrapper(new File("dummy_file"), "optional-content-type");

apisManagementController.importApiViaFileAsync(contentType, file).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 412 | Precondition Failed | `ApiException` |
| 422 | Unprocessable Entity | `ApiException` |
| 500 | Internal Server Error | `ApiException` |


# Import API via URL

Import an API into the APIMatic Dashboard by providing the URL of the API specification file.

You can also specify [API Metadata](https://docs.apimatic.io/manage-apis/apimatic-metadata) while importing the API using this endpoint. When specifying Metadata, the URL provided will be that of a zip file containing the API specification file and the `APIMATIC-META` json file.

```java
CompletableFuture<ApiResponse<ApiEntity>> importApiViaUrlAsync(
    final ImportApiViaUrlRequest body)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ImportApiViaUrlRequest`](../../doc/models/import-api-via-url-request.md) | Body, Required | Request Body |

## Response Type

**201**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ApiEntity`](../../doc/models/api-entity.md).

## Example Usage

```java
ImportApiViaUrlRequest body = new ImportApiViaUrlRequest.Builder(
    "https://petstore.swagger.io/v2/swagger.json"
)
.build();

apisManagementController.importApiViaUrlAsync(body).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 412 | Precondition Failed | `ApiException` |
| 422 | Unprocessable Entity | `ApiException` |
| 500 | Internal Server Error | `ApiException` |


# Import New API Version via File

Import a new version for an API, against an existing API Group, by uploading the API specification file.

You can also specify [API Metadata](https://docs.apimatic.io/manage-apis/apimatic-metadata) while importing the API version using this endpoint. When specifying Metadata, the uploaded file will be a zip file containing the API specification file and the `APIMATIC-META` json file.

```java
CompletableFuture<ApiResponse<ApiEntity>> importNewApiVersionViaFileAsync(
    final String apiGroupId,
    final Accept accept,
    final String versionOverride,
    final FileWrapper file)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiGroupId` | `String` | Template, Required | The ID of the API Group for which to import a new API version. |
| `accept` | [`Accept`](../../doc/models/accept.md) | Header, Required | - |
| `versionOverride` | `String` | Form, Required | The version number with which the new API version will be imported. This version number will override the version specified in the API specification file.<br>APIMatic recommends versioning the API with the [versioning scheme](https://docs.apimatic.io/define-apis/basic-settings/#version) documented in the docs. |
| `file` | `FileWrapper` | Form, Required | The API specification file.<br>The type of the specification file should be any of the [supported formats](https://docs.apimatic.io/api-transformer/overview-transformer#supported-input-formats). |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ApiEntity`](../../doc/models/api-entity.md).

## Example Usage

```java
String apiGroupId = "api_group_id6";
Accept accept = Accept.ENUM_APPLICATIONJSON;
String versionOverride = "version_override2";
FileWrapper file = new FileWrapper(new File("dummy_file"), "optional-content-type");

apisManagementController.importNewApiVersionViaFileAsync(apiGroupId, accept, versionOverride, file).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Import New API Version via URL

Import a new version for an API, against an existing API Group, by providing the URL of the API specification file.

You can also specify [API Metadata](https://docs.apimatic.io/manage-apis/apimatic-metadata) while importing the API version using this endpoint. When specifying Metadata, the URL provided will be that of a zip file containing the API specification file and the `APIMATIC-META` json file.

```java
CompletableFuture<ApiResponse<ApiEntity>> importNewApiVersionViaUrlAsync(
    final String apiGroupId,
    final Accept accept,
    final ImportApiVersionViaUrlRequest body)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiGroupId` | `String` | Template, Required | The ID of the API Group for which to import a new API version. |
| `accept` | [`Accept`](../../doc/models/accept.md) | Header, Required | - |
| `body` | [`ImportApiVersionViaUrlRequest`](../../doc/models/import-api-version-via-url-request.md) | Body, Required | Request Body |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ApiEntity`](../../doc/models/api-entity.md).

## Example Usage

```java
String apiGroupId = "5c9de181dc6209221416f250";
Accept accept = Accept.ENUM_APPLICATIONJSON;
ImportApiVersionViaUrlRequest body = new ImportApiVersionViaUrlRequest.Builder(
    "1.2.3",
    "https://petstore.swagger.io/v2/swagger.json"
)
.build();

apisManagementController.importNewApiVersionViaUrlAsync(apiGroupId, accept, body).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Inplace API Import via File

Replace an API version of an API Group, by uploading the API specification file that will replace the current version.

You can also specify [API Metadata](https://docs.apimatic.io/manage-apis/apimatic-metadata) while importing the API version using this endpoint. When specifying Metadata, the uploaded file will be a zip file containing the API specification file and the `APIMATIC-META` json file.

```java
CompletableFuture<ApiResponse<Void>> inplaceApiImportViaFileAsync(
    final String apiEntityId,
    final Accept2 accept,
    final FileWrapper file)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiEntityId` | `String` | Template, Required | The ID of the API Entity to replace. |
| `accept` | [`Accept2`](../../doc/models/accept-2.md) | Header, Required | - |
| `file` | `FileWrapper` | Form, Required | The API specification file.<br>The type of the specification file should be any of the [supported formats](https://docs.apimatic.io/api-transformer/overview-transformer#supported-input-formats). |

## Response Type

**200**

`void`

## Example Usage

```java
String apiEntityId = "api_entity_id4";
Accept2 accept = Accept2.ENUM_APPLICATIONVNDAPIMATICAPIENTITYFULLV1JSON;
FileWrapper file = new FileWrapper(new File("dummy_file"), "optional-content-type");

apisManagementController.inplaceApiImportViaFileAsync(apiEntityId, accept, file).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Inplace API Import via URL

Replace an API version of an API Group, by providing the URL of the API specification file that will replace the current version.

You can also specify [API Metadata](https://docs.apimatic.io/manage-apis/apimatic-metadata) while importing the API version using this endpoint. When specifying Metadata, the URL provided will be that of a zip file containing the API specification file and the `APIMATIC-META` json file.

```java
CompletableFuture<ApiResponse<Void>> inplaceApiImportViaUrlAsync(
    final String apiEntityId,
    final InplaceImportApiViaUrlRequest body)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiEntityId` | `String` | Template, Required | The ID of the API Entity to replace. |
| `body` | [`InplaceImportApiViaUrlRequest`](../../doc/models/inplace-import-api-via-url-request.md) | Body, Required | Request Body |

## Response Type

**200**

`void`

## Example Usage

```java
String apiEntityId = "api_entity_id4";
InplaceImportApiViaUrlRequest body = new InplaceImportApiViaUrlRequest.Builder(
    "https://petstore.swagger.io/v2/swagger.json"
)
.build();

apisManagementController.inplaceApiImportViaUrlAsync(apiEntityId, body).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Fetch API Entity

Fetch an API Entity.

```java
CompletableFuture<ApiResponse<ApiEntity>> fetchApiEntityAsync(
    final String apiEntityId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiEntityId` | `String` | Template, Required | The ID of the API Entity to fetch. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ApiEntity`](../../doc/models/api-entity.md).

## Example Usage

```java
String apiEntityId = "api_entity_id4";

apisManagementController.fetchApiEntityAsync(apiEntityId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Download API Specification

Download the API Specification file for a an API Version in any of the API Specification formats supported by APIMatic.

```java
CompletableFuture<ApiResponse<InputStream>> downloadApiSpecificationAsync(
    final String apiEntityId,
    final ExportFormats format)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiEntityId` | `String` | Template, Required | The ID of the API Entity to download. |
| `format` | [`ExportFormats`](../../doc/models/export-formats.md) | Query, Required | The format in which to download the API.<br>The format can be any of the [supported formats](https://docs.apimatic.io/api-transformer/overview-transformer#supported-input-formats). |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type `InputStream`.

## Example Usage

```java
String apiEntityId = "api_entity_id4";
ExportFormats format = ExportFormats.APIMATIC;

apisManagementController.downloadApiSpecificationAsync(apiEntityId, format).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

