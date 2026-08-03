# Code Generation-External APIs

```java
CodeGenerationExternalApisController codeGenerationExternalApisController = client.getCodeGenerationExternalApisController();
```

## Class Name

`CodeGenerationExternalApisController`

## Methods

* [Generate SDK via File](../../doc/controllers/code-generation-external-apis.md#generate-sdk-via-file)
* [Generate SDK via URL](../../doc/controllers/code-generation-external-apis.md#generate-sdk-via-url)
* [Download SDK](../../doc/controllers/code-generation-external-apis.md#download-sdk)
* [List All Code Generations](../../doc/controllers/code-generation-external-apis.md#list-all-code-generations)
* [Download Input File](../../doc/controllers/code-generation-external-apis.md#download-input-file)
* [Get a Code Generation](../../doc/controllers/code-generation-external-apis.md#get-a-code-generation)
* [Delete Code Generation for External APIs](../../doc/controllers/code-generation-external-apis.md#delete-code-generation-for-external-apis)


# Generate SDK via File

Generate an SDK for an API by by uploading the API specification file.

This endpoint generates and then uploads the generated SDK to APIMatic's cloud storage. An ID for the generation performed is returned as part of the response.

This endpoint does not import an API into APIMatic.

```java
CompletableFuture<ApiResponse<UserCodeGeneration>> generateSdkViaFileAsync(
    final Accept accept,
    final FileWrapper file,
    final Platforms template,
    final Map<String, Object> queryParameters)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accept` | [`Accept`](../../doc/models/accept.md) | Header, Required | Must be set to 'application/json' to ensure JSON response format |
| `file` | `FileWrapper` | Form, Required | The API specification file.<br>The type of the specification file should be any of the [supported formats](https://docs.apimatic.io/api-transformer/overview-transformer#supported-input-formats). |
| `template` | [`Platforms`](../../doc/models/platforms.md) | Form, Required | The structure contains platforms that APIMatic CodeGen can generate SDKs and Docs in. |
| `queryParameters` | `Map<String, Object>` | Optional | Pass additional query parameters. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UserCodeGeneration`](../../doc/models/user-code-generation.md).

## Example Usage

```java
Accept accept = Accept.ENUM_APPLICATIONJSON;
FileWrapper file = new FileWrapper(new File("dummy_file"), "optional-content-type");
Platforms template = Platforms.CS_NET_STANDARD_LIB;

Map<String, Object> queryParameters = new LinkedHashMap<String, Object>() {{
    put("key0", ApiHelper.deserialize("\"additionalQueryParams2\""));
}};

codeGenerationExternalApisController.generateSdkViaFileAsync(accept, file, template, queryParameters).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof BadRequestResponseSdkException) {
        BadRequestResponseSdkException badRequestResponseSdkException = (BadRequestResponseSdkException) cause;
        badRequestResponseSdkException.printStackTrace();
    } else if (cause instanceof UnauthorizedResponseException) {
        UnauthorizedResponseException unauthorizedResponseException = (UnauthorizedResponseException) cause;
        unauthorizedResponseException.printStackTrace();
    } else if (cause instanceof ProblemDetailsException) {
        ProblemDetailsException problemDetailsException = (ProblemDetailsException) cause;
        problemDetailsException.printStackTrace();
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
| 400 | Bad Request | [`BadRequestResponseSdkException`](../../doc/models/bad-request-response-sdk-exception.md) |
| 401 | Unauthorized | [`UnauthorizedResponseException`](../../doc/models/unauthorized-response-exception.md) |
| 403 | Subscription Issue | [`ProblemDetailsException`](../../doc/models/problem-details-exception.md) |


# Generate SDK via URL

Generate an SDK for an API by providing the URL of the API specification file.

This endpoint generates and then uploads the generated SDK to APIMatic's cloud storage. An ID for the generation performed is returned as part of the response.

This endpoint does not import an API into APIMatic.

```java
CompletableFuture<ApiResponse<UserCodeGeneration>> generateSdkViaUrlAsync(
    final GenerateSdkViaUrlRequest body)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`GenerateSdkViaUrlRequest`](../../doc/models/generate-sdk-via-url-request.md) | Body, Required | Request Body |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UserCodeGeneration`](../../doc/models/user-code-generation.md).

## Example Usage

```java
GenerateSdkViaUrlRequest body = new GenerateSdkViaUrlRequest.Builder(
    "http://petstore.swagger.io/v2/swagger.json",
    Platforms.CS_NET_STANDARD_LIB
)
.build();

codeGenerationExternalApisController.generateSdkViaUrlAsync(body).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Download SDK

Download the SDK generated via the Generate SDK endpoints.

```java
CompletableFuture<ApiResponse<InputStream>> downloadSdkAsync(
    final String codegenId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `codegenId` | `String` | Template, Required | The ID of code generation received in the response of the [Generate SDK Via File](../../doc/controllers/code-generation-external-apis.md#generate-sdk-via-file) or [Generate SDK Via URL ](../../doc/controllers/code-generation-external-apis.md#generate-sdk-via-url) calls. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type `InputStream`.

## Example Usage

```java
String codegenId = "codegen_id6";

codeGenerationExternalApisController.downloadSdkAsync(codegenId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# List All Code Generations

Get a list of all SDK generations performed with external APIs via the Generate SDK endpoints.

```java
CompletableFuture<ApiResponse<List<UserCodeGeneration>>> listAllCodeGenerationsAsync()
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`List<UserCodeGeneration>`](../../doc/models/user-code-generation.md).

## Example Usage

```java
codeGenerationExternalApisController.listAllCodeGenerationsAsync().thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Download Input File

Download the API Specification file used as input for a specific SDK generation performed via the Generate SDK endpoints.

```java
CompletableFuture<ApiResponse<InputStream>> downloadInputFileAsync(
    final String codegenId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `codegenId` | `String` | Template, Required | The ID of the code generation to download the API specification for. The code generation ID is received in the response of the [Generate SDK Via File](../../doc/controllers/code-generation-external-apis.md#generate-sdk-via-file) or [Generate SDK Via URL ](../../doc/controllers/code-generation-external-apis.md#generate-sdk-via-url) calls |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type `InputStream`.

## Example Usage

```java
String codegenId = "codegen_id6";

codeGenerationExternalApisController.downloadInputFileAsync(codegenId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Get a Code Generation

Get details on an SDK generation performed for an external API via the Generate SDK endpoints.

```java
CompletableFuture<ApiResponse<UserCodeGeneration>> getACodeGenerationAsync(
    final String codegenId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `codegenId` | `String` | Template, Required | The ID of the code generation to fetch. The code generation ID is received in the response of the [Generate SDK Via File](../../doc/controllers/code-generation-external-apis.md#generate-sdk-via-file) or [Generate SDK Via URL ](../../doc/controllers/code-generation-external-apis.md#generate-sdk-via-url) calls. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UserCodeGeneration`](../../doc/models/user-code-generation.md).

## Example Usage

```java
String codegenId = "codegen_id6";

codeGenerationExternalApisController.getACodeGenerationAsync(codegenId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Delete Code Generation for External APIs

Delete an SDK generation performed for an API via the Generate SDK endpoints.

```java
CompletableFuture<ApiResponse<Void>> deleteCodeGenerationForExternalApisAsync(
    final String codegenId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `codegenId` | `String` | Template, Required | The ID of the code generation to delete. The code generation ID is received in the response of the [Generate SDK Via File](../../doc/controllers/code-generation-external-apis.md#generate-sdk-via-file) or [Generate SDK Via URL ](../../doc/controllers/code-generation-external-apis.md#generate-sdk-via-url) calls. |

## Response Type

**200**

`void`

## Example Usage

```java
String codegenId = "codegen_id6";

codeGenerationExternalApisController.deleteCodeGenerationForExternalApisAsync(codegenId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

