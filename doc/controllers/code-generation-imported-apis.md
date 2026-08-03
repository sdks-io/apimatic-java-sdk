# Code Generation-Imported APIs

```java
CodeGenerationImportedApisController codeGenerationImportedApisController = client.getCodeGenerationImportedApisController();
```

## Class Name

`CodeGenerationImportedApisController`

## Methods

* [Generate SDK](../../doc/controllers/code-generation-imported-apis.md#generate-sdk)
* [Download SDK](../../doc/controllers/code-generation-imported-apis.md#download-sdk)
* [List All Code Generations](../../doc/controllers/code-generation-imported-apis.md#list-all-code-generations)
* [Get a Code Generation](../../doc/controllers/code-generation-imported-apis.md#get-a-code-generation)
* [Delete Code Generation](../../doc/controllers/code-generation-imported-apis.md#delete-code-generation)


# Generate SDK

Generate an SDK for an API Version.

This endpoint generates and then uploads the generated SDK to APIMatic's cloud storage. An ID for the generation performed is returned as part of the response.

```java
CompletableFuture<ApiResponse<ApiEntityCodeGeneration>> generateSdkAsync(
    final String apiEntityId,
    final Platforms template)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiEntityId` | `String` | Template, Required | The ID of the API Entity to generate the SDK for. |
| `template` | [`Platforms`](../../doc/models/platforms.md) | Form, Required | The structure contains platforms that APIMatic CodeGen can generate SDKs and Docs in. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ApiEntityCodeGeneration`](../../doc/models/api-entity-code-generation.md).

## Example Usage

```java
String apiEntityId = "api_entity_id4";
Platforms template = Platforms.CS_NET_STANDARD_LIB;

codeGenerationImportedApisController.generateSdkAsync(apiEntityId, template).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Download SDK

Download the SDK generated via the Generate SDK endpoint.

```java
CompletableFuture<ApiResponse<InputStream>> downloadSdkAsync(
    final String apiEntityId,
    final String codegenId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiEntityId` | `String` | Template, Required | The ID of the API Entity for which the SDK was generated. |
| `codegenId` | `String` | Template, Required | The ID of code generation received in the response of the [SDK generation call](../../doc/controllers/code-generation-imported-apis.md#generate-sdk). |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type `InputStream`.

## Example Usage

```java
String apiEntityId = "api_entity_id4";
String codegenId = "codegen_id6";

codeGenerationImportedApisController.downloadSdkAsync(apiEntityId, codegenId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# List All Code Generations

Get a list of all SDK generations done against an API Version via the Generate SDK endpoint.

```java
CompletableFuture<ApiResponse<List<ApiEntityCodeGeneration>>> listAllCodeGenerationsAsync(
    final String apiEntityId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiEntityId` | `String` | Template, Required | The ID of the API Entity for which to list code generations. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`List<ApiEntityCodeGeneration>`](../../doc/models/api-entity-code-generation.md).

## Example Usage

```java
String apiEntityId = "api_entity_id4";

codeGenerationImportedApisController.listAllCodeGenerationsAsync(apiEntityId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Get a Code Generation

Get details on an SDK generation performed via the Generate SDK endpoint.

```java
CompletableFuture<ApiResponse<ApiEntityCodeGeneration>> getACodeGenerationAsync(
    final String apiEntityId,
    final String codegenId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiEntityId` | `String` | Template, Required | The ID of the API Entity to fetch the code generation for. |
| `codegenId` | `String` | Template, Required | The ID of the code generation to fetch. The code generation ID is received in the response of the [SDK generation call](../../doc/controllers/code-generation-imported-apis.md#generate-sdk). |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ApiEntityCodeGeneration`](../../doc/models/api-entity-code-generation.md).

## Example Usage

```java
String apiEntityId = "api_entity_id4";
String codegenId = "codegen_id6";

codeGenerationImportedApisController.getACodeGenerationAsync(apiEntityId, codegenId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Delete Code Generation

Delete an SDK generation performed for an API Version via the Generate SDK endpoint.

```java
CompletableFuture<ApiResponse<Void>> deleteCodeGenerationAsync(
    final String apiEntityId,
    final String codegenId)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `apiEntityId` | `String` | Template, Required | The ID of the API Entity to delete the code generation for. |
| `codegenId` | `String` | Template, Required | The ID of the code generation to delete. The code generation ID is received in the response of the [SDK generation call](../../doc/controllers/code-generation-imported-apis.md#generate-sdk). |

## Response Type

**200**

`void`

## Example Usage

```java
String apiEntityId = "api_entity_id4";
String codegenId = "codegen_id6";

codeGenerationImportedApisController.deleteCodeGenerationAsync(apiEntityId, codegenId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

