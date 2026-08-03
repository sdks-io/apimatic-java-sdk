
# Validate Api Result

*This model accepts additional fields of type Object.*

## Structure

`ValidateApiResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Validation` | [`ValidationSummary`](../../doc/models/validation-summary.md) | Required | - | ValidationSummary getValidation() | setValidation(ValidationSummary validation) |
| `Linting` | [`ValidationSummary`](../../doc/models/validation-summary.md) | Required | - | ValidationSummary getLinting() | setLinting(ValidationSummary linting) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.LineInfo;
import io.apimatic.api.models.ValidateApiResult;
import io.apimatic.api.models.ValidationEntry;
import io.apimatic.api.models.ValidationSummary;
import java.io.IOException;
import java.util.Arrays;
import java.util.LinkedHashMap;

ValidateApiResult validateApiResult = new ValidateApiResult.Builder(
    new ValidationSummary.Builder(
        false,
        Arrays.asList(
            new ValidationEntry.Builder(
                "message4"
            )
            .lineInfo(new LineInfo.Builder(
                    162,
                    6,
                    142,
                    74
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
            .jsonReferencePath("jsonReferencePath0")
            .fileReference("fileReference2")
            .metadata(new LinkedHashMap<String, String>() {{
                    put("key0", "metadata9");
                    put("key1", "metadata0");
                    put("key2", "metadata1");
                }})
            .ruleDocumentationReference("ruleDocumentationReference4")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        ),
        Arrays.asList(
            new ValidationEntry.Builder(
                "message0"
            )
            .lineInfo(new LineInfo.Builder(
                    162,
                    6,
                    142,
                    74
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
            .jsonReferencePath("jsonReferencePath6")
            .fileReference("fileReference8")
            .metadata(new LinkedHashMap<String, String>() {{
                    put("key0", "metadata3");
                }})
            .ruleDocumentationReference("ruleDocumentationReference0")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        ),
        Arrays.asList(
            new ValidationEntry.Builder(
                "message4"
            )
            .lineInfo(new LineInfo.Builder(
                    162,
                    6,
                    142,
                    74
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
            .jsonReferencePath("jsonReferencePath0")
            .fileReference("fileReference2")
            .metadata(new LinkedHashMap<String, String>() {{
                    put("key0", "metadata1");
                    put("key1", "metadata0");
                    put("key2", "metadata9");
                }})
            .ruleDocumentationReference("ruleDocumentationReference4")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        ),
        Arrays.asList(
            new ValidationEntry.Builder(
                "message4"
            )
            .lineInfo(new LineInfo.Builder(
                    162,
                    6,
                    142,
                    74
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
            .jsonReferencePath("jsonReferencePath0")
            .fileReference("fileReference2")
            .metadata(new LinkedHashMap<String, String>() {{
                    put("key0", "metadata9");
                }})
            .ruleDocumentationReference("ruleDocumentationReference4")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        )
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build(),
    new ValidationSummary.Builder(
        false,
        Arrays.asList(
            new ValidationEntry.Builder(
                "message4"
            )
            .lineInfo(new LineInfo.Builder(
                    162,
                    6,
                    142,
                    74
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
            .jsonReferencePath("jsonReferencePath0")
            .fileReference("fileReference2")
            .metadata(new LinkedHashMap<String, String>() {{
                    put("key0", "metadata9");
                    put("key1", "metadata0");
                    put("key2", "metadata1");
                }})
            .ruleDocumentationReference("ruleDocumentationReference4")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        ),
        Arrays.asList(
            new ValidationEntry.Builder(
                "message0"
            )
            .lineInfo(new LineInfo.Builder(
                    162,
                    6,
                    142,
                    74
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
            .jsonReferencePath("jsonReferencePath6")
            .fileReference("fileReference8")
            .metadata(new LinkedHashMap<String, String>() {{
                    put("key0", "metadata3");
                }})
            .ruleDocumentationReference("ruleDocumentationReference0")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        ),
        Arrays.asList(
            new ValidationEntry.Builder(
                "message4"
            )
            .lineInfo(new LineInfo.Builder(
                    162,
                    6,
                    142,
                    74
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
            .jsonReferencePath("jsonReferencePath0")
            .fileReference("fileReference2")
            .metadata(new LinkedHashMap<String, String>() {{
                    put("key0", "metadata1");
                    put("key1", "metadata0");
                    put("key2", "metadata9");
                }})
            .ruleDocumentationReference("ruleDocumentationReference4")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        ),
        Arrays.asList(
            new ValidationEntry.Builder(
                "message4"
            )
            .lineInfo(new LineInfo.Builder(
                    162,
                    6,
                    142,
                    74
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
            .jsonReferencePath("jsonReferencePath0")
            .fileReference("fileReference2")
            .metadata(new LinkedHashMap<String, String>() {{
                    put("key0", "metadata9");
                }})
            .ruleDocumentationReference("ruleDocumentationReference4")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        )
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build()
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

