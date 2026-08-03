
# Validation Exception

Validation exception contains information, warnings, messages and errors.

*This model accepts additional fields of type Object.*

## Structure

`ValidationException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Reason` | `String` | Required | - | String getReason() | setReason(String reason) |
| `Summary` | `String` | Optional | Validation Summary of the API in case validation failed | String getSummary() | setSummary(String summary) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.ValidationException;
import java.io.IOException;

ValidationException validationException = new ValidationException.Builder(
    "Import Failed"
)
.summary("summary2")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

