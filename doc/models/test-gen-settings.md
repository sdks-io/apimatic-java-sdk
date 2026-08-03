
# Test Gen Settings

This structure helps specify additional test configurations which affects how test cases are generated.

*This model accepts additional fields of type Object.*

## Structure

`TestGenSettings`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `PrecisionDelta` | `double` | Required | Error margin for comparing values in decimal places | double getPrecisionDelta() | setPrecisionDelta(double precisionDelta) |
| `TestTimeout` | `int` | Required | Number of seconds after which if the endpoint is not returning any response, the test is forced to fail e.g. a timeout of 60 | int getTestTimeout() | setTestTimeout(int testTimeout) |
| `Configuration` | `Object` | Required | The parameters allows to provide values for configuration file for use in the test environment | Object getConfiguration() | setConfiguration(Object configuration) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.TestGenSettings;
import java.io.IOException;

TestGenSettings testGenSettings = new TestGenSettings.Builder(
    0.01D,
    30,
    ApiHelper.deserialize("{}")
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

