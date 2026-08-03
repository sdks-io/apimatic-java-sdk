# Transformation

```java
TransformationController transformationController = client.getTransformationController();
```

## Class Name

`TransformationController`

## Methods

* [Transform via File](../../doc/controllers/transformation.md#transform-via-file)
* [Transform via URL](../../doc/controllers/transformation.md#transform-via-url)
* [Download Transformed File](../../doc/controllers/transformation.md#download-transformed-file)
* [Download Input File](../../doc/controllers/transformation.md#download-input-file)
* [List All Transformations](../../doc/controllers/transformation.md#list-all-transformations)
* [Get a Transformation](../../doc/controllers/transformation.md#get-a-transformation)
* [Delete Transformation](../../doc/controllers/transformation.md#delete-transformation)


# Transform via File

Transform an API into any of the supported API specification formats by uploading the API specification file.

This endpoint transforms and then uploads the transformed API specification to APIMatic's cloud storage. An ID for the transformation performed is returned as part of the response.

```java
CompletableFuture<ApiResponse<Transformation>> transformViaFileAsync(
    final ContentType contentType,
    final FileWrapper file,
    final ExportFormats exportFormat,
    final Map<String, Object> queryParameters)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `contentType` | [`ContentType`](../../doc/models/content-type.md) | Header, Required | - |
| `file` | `FileWrapper` | Form, Required | The API specification file.<br>The type of the specification file should be any of the [supported formats](https://docs.apimatic.io/api-transformer/overview-transformer#supported-input-formats). |
| `exportFormat` | [`ExportFormats`](../../doc/models/export-formats.md) | Form, Required | The structure contains API specification formats that Transformer can convert to. |
| `queryParameters` | `Map<String, Object>` | Optional | Pass additional query parameters. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`Transformation`](../../doc/models/transformation.md).

## Example Usage

```java
ContentType contentType = ContentType.ENUM_MULTIPARTFORMDATA;
FileWrapper file = new FileWrapper(new File("dummy_file"), "optional-content-type");
ExportFormats exportFormat = ExportFormats.WSDL;

Map<String, Object> queryParameters = new LinkedHashMap<String, Object>() {{
    put("key0", ApiHelper.deserialize("\"additionalQueryParams2\""));
}};

transformationController.transformViaFileAsync(contentType, file, exportFormat, queryParameters).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Transform via URL

Transform an API into any of the supported API specification formats by providing the URL of the API specification file.

This endpoint transforms and then uploads the transformed API specification to APIMatic's cloud storage. An ID for the transformation performed is returned as part of the response.

```java
CompletableFuture<ApiResponse<Transformation>> transformViaUrlAsync(
    final TransformViaUrlRequest body)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`TransformViaUrlRequest`](../../doc/models/transform-via-url-request.md) | Body, Required | Request Body |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`Transformation`](../../doc/models/transformation.md).

## Example Usage

```java
TransformViaUrlRequest body = new TransformViaUrlRequest.Builder(
    "https://petstore.swagger.io/v2/swagger.json",
    ExportFormats.APIMATIC
)
.build();

transformationController.transformViaUrlAsync(body).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Download Transformed File

Download the transformed API specification file transformed via the Transformation endpoints.

```java
CompletableFuture<ApiResponse<InputStream>> downloadTransformedFileAsync(
    final String transformationId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transformationId` | `String` | Template, Required | The ID of transformation received in the response of the [Transform Via File ](../../doc/controllers/transformation.md#transform-via-file) or [Transform Via URL  ](../../doc/controllers/transformation.md#transform-via-url) calls. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type `InputStream`.

## Example Usage

```java
String transformationId = "transformation_id6";

transformationController.downloadTransformedFileAsync(transformationId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Download Input File

Download the API Specification file used as input for a particular Transformation performed via the Transformation endpoints.

```java
CompletableFuture<ApiResponse<InputStream>> downloadInputFileAsync(
    final String transformationId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transformationId` | `String` | Template, Required | The ID of the transformation to download the API specification for. The transformation ID is received in the response of the [Transform Via File ](../../doc/controllers/transformation.md#transform-via-file) or [Transform Via URL](../../doc/controllers/transformation.md#transform-via-url) calls. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type `InputStream`.

## Example Usage

```java
String transformationId = "transformation_id6";

transformationController.downloadInputFileAsync(transformationId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# List All Transformations

Get a list of all API transformations performed.

```java
CompletableFuture<ApiResponse<List<Transformation>>> listAllTransformationsAsync()
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`List<Transformation>`](../../doc/models/transformation.md).

## Example Usage

```java
transformationController.listAllTransformationsAsync().thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Get a Transformation

Get details on a particular Transformation performed via the Transformation endpoints.

```java
CompletableFuture<ApiResponse<Transformation>> getATransformationAsync(
    final String transformationId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transformationId` | `String` | Template, Required | The ID of the transformation to fetch. The transformation ID is received in the response of the [Transform Via File ](../../doc/controllers/transformation.md#transform-via-file) or [Transform Via URL  ](../../doc/controllers/transformation.md#transform-via-url) calls. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`Transformation`](../../doc/models/transformation.md).

## Example Usage

```java
String transformationId = "transformation_id6";

transformationController.getATransformationAsync(transformationId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Delete Transformation

Delete a particular Transformation performed for an API via the Transformation endpoints.

```java
CompletableFuture<ApiResponse<Void>> deleteTransformationAsync(
    final String transformationId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transformationId` | `String` | Template, Required | The ID of the transformation to delete. The transformation ID is received in the response of the [Transform Via File ](../../doc/controllers/transformation.md#transform-via-file) or [Transform Via URL](../../doc/controllers/transformation.md#transform-via-url) calls. |

## Response Type

**200**

`void`

## Example Usage

```java
String transformationId = "transformation_id6";

transformationController.deleteTransformationAsync(transformationId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

