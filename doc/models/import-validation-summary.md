
# Import Validation Summary

*This model accepts additional fields of type Object.*

## Structure

`ImportValidationSummary`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Success` | `boolean` | Required | - | boolean getSuccess() | setSuccess(boolean success) |
| `Errors` | `List<String>` | Required | - | List<String> getErrors() | setErrors(List<String> errors) |
| `Warnings` | `List<String>` | Required | - | List<String> getWarnings() | setWarnings(List<String> warnings) |
| `Messages` | `List<String>` | Required | - | List<String> getMessages() | setMessages(List<String> messages) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.ImportValidationSummary;
import java.io.IOException;
import java.util.Arrays;

ImportValidationSummary importValidationSummary = new ImportValidationSummary.Builder(
    true,
    Arrays.asList(

    ),
    Arrays.asList(

    ),
    Arrays.asList(
        "One or more elements in the API specification has a missing description field."
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

