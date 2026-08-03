
# Validation Entry

*This model accepts additional fields of type Object.*

## Structure

`ValidationEntry`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Message` | `String` | Required | - | String getMessage() | setMessage(String message) |
| `LineInfo` | [`LineInfo`](../../doc/models/line-info.md) | Optional | - | LineInfo getLineInfo() | setLineInfo(LineInfo lineInfo) |
| `JsonReferencePath` | `String` | Optional | - | String getJsonReferencePath() | setJsonReferencePath(String jsonReferencePath) |
| `FileReference` | `String` | Optional | - | String getFileReference() | setFileReference(String fileReference) |
| `Metadata` | `Map<String, String>` | Optional | - | Map<String, String> getMetadata() | setMetadata(Map<String, String> metadata) |
| `RuleDocumentationReference` | `String` | Optional | - | String getRuleDocumentationReference() | setRuleDocumentationReference(String ruleDocumentationReference) |
| `AdditionalReferences` | `List<String>` | Optional | - | List<String> getAdditionalReferences() | setAdditionalReferences(List<String> additionalReferences) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.LineInfo;
import io.apimatic.api.models.ValidationEntry;
import java.io.IOException;
import java.util.LinkedHashMap;

ValidationEntry validationEntry = new ValidationEntry.Builder(
    "message2"
)
.lineInfo(new LineInfo.Builder(
        162,
        6,
        142,
        74
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.jsonReferencePath("jsonReferencePath8")
.fileReference("fileReference0")
.metadata(new LinkedHashMap<String, String>() {{
        put("key0", "metadata9");
    }})
.ruleDocumentationReference("ruleDocumentationReference2")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

