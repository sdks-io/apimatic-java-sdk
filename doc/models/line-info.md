
# Line Info

*This model accepts additional fields of type Object.*

## Structure

`LineInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `StartLineNumber` | `int` | Required | - | int getStartLineNumber() | setStartLineNumber(int startLineNumber) |
| `StartLinePosition` | `int` | Required | - | int getStartLinePosition() | setStartLinePosition(int startLinePosition) |
| `EndLineNumber` | `int` | Required | - | int getEndLineNumber() | setEndLineNumber(int endLineNumber) |
| `EndLinePosition` | `int` | Required | - | int getEndLinePosition() | setEndLinePosition(int endLinePosition) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.LineInfo;
import java.io.IOException;

LineInfo lineInfo = new LineInfo.Builder(
    162,
    6,
    142,
    74
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

