
# Endpoint

This structure encapsulates all the attributes of an API Endpoint.

*This model accepts additional fields of type Object.*

## Structure

`Endpoint`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | Unique Endpoint Identifier | String getId() | setId(String id) |
| `ApiId` | `String` | Required | Unique API Identifier | String getApiId() | setApiId(String apiId) |
| `Name` | `String` | Required | Endpoint Name | String getName() | setName(String name) |
| `HttpMethod` | `String` | Required | Endpoint Method | String getHttpMethod() | setHttpMethod(String httpMethod) |
| `Group` | `String` | Required | The Group Endpoint belongs to | String getGroup() | setGroup(String group) |
| `SkipAuthentication` | `boolean` | Required | If Endpoint warrants authentication or not | boolean getSkipAuthentication() | setSkipAuthentication(boolean skipAuthentication) |
| `Route` | `String` | Required | The Endpoint route | String getRoute() | setRoute(String route) |
| `Response` | [`Response`](../../doc/models/response.md) | Required | The structure encapsulates all details of a request response | Response getResponse() | setResponse(Response response) |
| `HasOptionalQueryParams` | `boolean` | Required | Enabling this option allows optional query parameters | boolean getHasOptionalQueryParams() | setHasOptionalQueryParams(boolean hasOptionalQueryParams) |
| `HasOptionalFieldParams` | `boolean` | Required | Enabling this option allows optional field parameters | boolean getHasOptionalFieldParams() | setHasOptionalFieldParams(boolean hasOptionalFieldParams) |
| `CollectParameters` | `boolean` | Required | Enabling this option collects API endpoint parameters as collections | boolean getCollectParameters() | setCollectParameters(boolean collectParameters) |
| `WrapBodyInObject` | `boolean` | Required | Enabling this option allows wrapping of body in objects | boolean getWrapBodyInObject() | setWrapBodyInObject(boolean wrapBodyInObject) |
| `RequiredScopes` | `List<String>` | Required | What scopes apply to an Endpoint | List<String> getRequiredScopes() | setRequiredScopes(List<String> requiredScopes) |
| `Parameters` | [`List<Parameter>`](../../doc/models/parameter.md) | Required | Endpoint Paramaters | List<Parameter> getParameters() | setParameters(List<Parameter> parameters) |
| `Errors` | `List<Object>` | Required | Errors that Endpoint may output | List<Object> getErrors() | setErrors(List<Object> errors) |
| `TestCases` | [`List<TestCase>`](../../doc/models/test-case.md) | Required | Test Cases associated with Endpoint | List<TestCase> getTestCases() | setTestCases(List<TestCase> testCases) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.Attributes;
import io.apimatic.api.models.Endpoint;
import io.apimatic.api.models.InputParameter;
import io.apimatic.api.models.Parameter;
import io.apimatic.api.models.Response;
import io.apimatic.api.models.TestCase;
import java.io.IOException;
import java.util.Arrays;

Endpoint endpoint = new Endpoint.Builder(
    "5a4e8675b724bb198c28a06a",
    "5a4e8675b724bb198c289fe9",
    "Send String in body with \\r\\n",
    "POST",
    "BodyParams",
    false,
    "/body/stringEncoding",
    new Response.Builder(
        false,
        "ServerResponse",
        false,
        false,
        false,
        false,
        false,
        new Attributes.Builder(
            "5be1603083b41d0b50110551"
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build(),
        false,
        "5a4e8675b724bb198c289f79",
        "response"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build(),
    false,
    false,
    false,
    false,
    Arrays.asList(

    ),
    Arrays.asList(
        new Parameter.Builder(
            false,
            "test\\r\\nstringEncoding",
            false,
            false,
            false,
            false,
            false,
            new Attributes.Builder(
                "5be1603083b41d0b50110551"
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
            false,
            "5a4e8675b724bb198c289f7a",
            "body",
            "description4",
            "defaultValue2",
            "Body"
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ),
    Arrays.asList(

    ),
    Arrays.asList(
        new TestCase.Builder(
            "5a4e8675b724bb198c289f7b",
            "5a4e8675b724bb198c28a06a",
            "5a4e8675b724bb198c289fe9",
            "send string in body with \\r\\n1",
            true,
            true,
            Arrays.asList(
                new InputParameter.Builder(
                    false,
                    "5a4e8675b724bb198c289f7a",
                    "5a4e8675b724bb198c289f7c",
                    "body",
                    "{\"name\":\"farhan\",\"field\":\"QA\"}"
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build()
            ),
            "200",
            Arrays.asList(

            ),
            true,
            "{\r\n  \"passed\": true\r\n}",
            "KEYSANDVALUES",
            false,
            false,
            true
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

