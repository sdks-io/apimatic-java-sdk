
# Test Case

APIMatic lets you define test cases for endpoints using the API Editor. The test cases are automatically generated for each language. This structure encapsulates all details of a Test Case.  To find out more about defining Test Cases visit: https://docs.apimatic.io/testing/defining-your-first-test-case/

*This model accepts additional fields of type Object.*

## Structure

`TestCase`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | Unique Test Case identifier | String getId() | setId(String id) |
| `EndpointId` | `String` | Required | The Endpoint, test case is associated with | String getEndpointId() | setEndpointId(String endpointId) |
| `ApiId` | `String` | Required | The API Entity, test case is associated with | String getApiId() | setApiId(String apiId) |
| `Name` | `String` | Required | The Test Case name | String getName() | setName(String name) |
| `Enabled` | `boolean` | Required | Enable/Disable a Test Case | boolean getEnabled() | setEnabled(boolean enabled) |
| `ShouldPass` | `boolean` | Required | - | boolean getShouldPass() | setShouldPass(boolean shouldPass) |
| `InputParameters` | [`List<InputParameter>`](../../doc/models/input-parameter.md) | Required | Test case parameters | List<InputParameter> getInputParameters() | setInputParameters(List<InputParameter> inputParameters) |
| `ExpectedStatus` | `String` | Required | Expected response status. We expect the status code to be 200 if the operation is successful, hence we input the value 200. | String getExpectedStatus() | setExpectedStatus(String expectedStatus) |
| `ExpectedHeaders` | `List<String>` | Required | Expected Headers | List<String> getExpectedHeaders() | setExpectedHeaders(List<String> expectedHeaders) |
| `ExpectedHeadersAllowExtra` | `boolean` | Required | If this flag is disabled, it will cause the test case to fail if the response contains other headers than those listed in the expected headers list. | boolean getExpectedHeadersAllowExtra() | setExpectedHeadersAllowExtra(boolean expectedHeadersAllowExtra) |
| `ExpectedBody` | `String` | Required | Expected response goes in the expected body | String getExpectedBody() | setExpectedBody(String expectedBody) |
| `ExpectedBodyMatchMode` | `String` | Required | Specifies what to match | String getExpectedBodyMatchMode() | setExpectedBodyMatchMode(String expectedBodyMatchMode) |
| `ExpectedArrayOrderedMatching` | `boolean` | Required | If enabled, this will involve ensuring that the response body contains the array elements in the same order as the expected body. | boolean getExpectedArrayOrderedMatching() | setExpectedArrayOrderedMatching(boolean expectedArrayOrderedMatching) |
| `ExpectedArrayCheckCount` | `boolean` | Required | If enabled, this will ensure that the response body contains the same number of elements in the array as does the expected body. | boolean getExpectedArrayCheckCount() | setExpectedArrayCheckCount(boolean expectedArrayCheckCount) |
| `ResponseMatchSchema` | `boolean` | Required | - | boolean getResponseMatchSchema() | setResponseMatchSchema(boolean responseMatchSchema) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.InputParameter;
import io.apimatic.api.models.TestCase;
import java.io.IOException;
import java.util.Arrays;

TestCase testCase = new TestCase.Builder(
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
.build();
```

