# API Validation V2-External APIs

```java
ApiValidationV2ExternalApisController apiValidationV2ExternalApisController = client.getApiValidationV2ExternalApisController();
```

## Class Name

`ApiValidationV2ExternalApisController`

## Methods

* [Validate API via File - V2](../../doc/controllers/api-validation-v2-external-apis.md#validate-api-via-file---v2)
* [Validate API via URL - V2](../../doc/controllers/api-validation-v2-external-apis.md#validate-api-via-url---v2)


# Validate API via File - V2

Validate an API by uploading the API specification file.

You can also specify [API Metadata](https://docs.apimatic.io/manage-apis/apimatic-metadata) while validating the API using this endpoint. When specifying Metadata, the uploaded file will be a zip file containing the API specification file and the `APIMATIC-META` json file.

```java
CompletableFuture<ApiResponse<ValidateApiResult>> validateApiViaFileV2Async(
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

## Server

`Server.ENUM_DEFAULT`

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ValidateApiResult`](../../doc/models/validate-api-result.md).

## Example Usage

```java
ContentType contentType = ContentType.ENUM_MULTIPARTFORMDATA;
FileWrapper file = new FileWrapper(new File("dummy_file"), "optional-content-type");

apiValidationV2ExternalApisController.validateApiViaFileV2Async(contentType, file).thenAccept(result -> {
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
  "validation": {
    "isSuccess": true,
    "blocking": [],
    "errors": [],
    "warnings": [],
    "information": []
  },
  "linting": {
    "isSuccess": false,
    "blocking": [],
    "errors": [
      {
        "message": "The 'x-extension-ver' property is required in the 'info' object.",
        "lineInfo": {
          "startLineNumber": 3,
          "startLinePosition": 3,
          "endLineNumber": 3,
          "endLinePosition": 4
        },
        "jsonReferencePath": "#/info",
        "fileReference": "openapi.yaml",
        "metadata": {
          "missing Property": "x-extension-ver",
          "target": "$.info"
        },
        "ruleDocumentationReference": "https://docs.apimatic.io/rulesets/custom-rules-linting/required-property-exists/"
      }
    ],
    "warnings": [
      {
        "message": "Unsupported extension detected.",
        "lineInfo": {
          "startLineNumber": 10,
          "startLinePosition": 3,
          "endLineNumber": 10,
          "endLinePosition": 11
        },
        "jsonReferencePath": "#/info",
        "fileReference": "openapi.yaml",
        "metadata": {
          "unsupported Extension": "x-api-id"
        },
        "ruleDocumentationReference": "https://docs.apimatic.io/rulesets/openapi-v3-apimatic-linting/supported-vendor-extension/"
      }
    ],
    "information": [
      {
        "message": "Schema object description is missing.",
        "lineInfo": {
          "startLineNumber": 81,
          "startLinePosition": 11,
          "endLineNumber": 81,
          "endLinePosition": 12
        },
        "jsonReferencePath": "#/components/schemas/ProblemResponse/properties/type",
        "fileReference": "openapi.yaml",
        "metadata": {},
        "ruleDocumentationReference": "https://docs.apimatic.io/rulesets/openapi-v3-docsgen-linting/schema-description-exists/",
        "additionalReferences": [
          "https://github.com/OAI/OpenAPI-Specification/blob/main/versions/3.0.3.md#specification-extensions"
        ]
      }
    ]
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ProblemDetailsException`](../../doc/models/problem-details-exception.md) |
| 401 | Unauthorized | [`UnauthorizedResponseException`](../../doc/models/unauthorized-response-exception.md) |
| 403 | Subscription Issue | [`ProblemDetailsException`](../../doc/models/problem-details-exception.md) |
| 500 | Internal Server Error | [`InternalServerErrorResponseException`](../../doc/models/internal-server-error-response-exception.md) |


# Validate API via URL - V2

Validate an API by providing the URL of the API specification file.

You can also specify [API Metadata](https://docs.apimatic.io/manage-apis/apimatic-metadata) while validating the API using this endpoint. When specifying Metadata, the URL provided will be that of a zip file containing the API specification file and the `APIMATIC-META` json file.

```java
CompletableFuture<ApiResponse<ValidateApiResult>> validateApiViaUrlV2Async(
    final String url)
```

## Authentication

This endpoint requires [Authorization](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `url` | `String` | Query, Required | The URL for the API specification file.<br><br>**Note:** This URL should be publicly accessible. |

## Server

`Server.ENUM_DEFAULT`

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ValidateApiResult`](../../doc/models/validate-api-result.md).

## Example Usage

```java
String url = "https://petstore.swagger.io/v2/swagger.json";

apiValidationV2ExternalApisController.validateApiViaUrlV2Async(url).thenAccept(result -> {
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
  "validation": {
    "isSuccess": true,
    "blocking": [],
    "errors": [],
    "warnings": [],
    "information": []
  },
  "linting": {
    "isSuccess": false,
    "blocking": [],
    "errors": [
      {
        "message": "The 'x-extension-ver' property is required in the 'info' object.",
        "lineInfo": {
          "startLineNumber": 3,
          "startLinePosition": 3,
          "endLineNumber": 3,
          "endLinePosition": 4
        },
        "jsonReferencePath": "#/info",
        "fileReference": "openapi.yaml",
        "metadata": {
          "missing Property": "x-extension-ver",
          "target": "$.info"
        },
        "ruleDocumentationReference": "https://docs.apimatic.io/rulesets/custom-rules-linting/required-property-exists/"
      }
    ],
    "warnings": [
      {
        "message": "Unsupported extension detected.",
        "lineInfo": {
          "startLineNumber": 10,
          "startLinePosition": 3,
          "endLineNumber": 10,
          "endLinePosition": 11
        },
        "jsonReferencePath": "#/info",
        "fileReference": "openapi.yaml",
        "metadata": {
          "unsupported Extension": "x-api-id"
        },
        "ruleDocumentationReference": "https://docs.apimatic.io/rulesets/openapi-v3-apimatic-linting/supported-vendor-extension/"
      }
    ],
    "information": [
      {
        "message": "Schema object description is missing.",
        "lineInfo": {
          "startLineNumber": 81,
          "startLinePosition": 11,
          "endLineNumber": 81,
          "endLinePosition": 12
        },
        "jsonReferencePath": "#/components/schemas/ProblemResponse/properties/type",
        "fileReference": "openapi.yaml",
        "metadata": {},
        "ruleDocumentationReference": "https://docs.apimatic.io/rulesets/openapi-v3-docsgen-linting/schema-description-exists/"
      }
    ]
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ProblemDetailsException`](../../doc/models/problem-details-exception.md) |
| 401 | Unauthorized | [`UnauthorizedResponseException`](../../doc/models/unauthorized-response-exception.md) |
| 403 | Subscription Issue | [`ProblemDetailsException`](../../doc/models/problem-details-exception.md) |
| 500 | Internal Server Error | [`InternalServerErrorResponseException`](../../doc/models/internal-server-error-response-exception.md) |

