
# Sdk Generation Status Response

## Structure

`SdkGenerationStatusResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Status` | [`Status`](../../doc/models/status.md) | Required | - | Status getStatus() | setStatus(Status status) |
| `Errors` | `Map<String, Object>` | Optional | - | Map<String, Object> getErrors() | setErrors(Map<String, Object> errors) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.SdkGenerationStatusResponse;
import io.apimatic.api.models.Status;
import java.io.IOException;
import java.util.LinkedHashMap;

SdkGenerationStatusResponse sdkGenerationStatusResponse = new SdkGenerationStatusResponse.Builder(
    Status.INPROGRESS
)
.errors(new LinkedHashMap<String, Object>() {{
        put("key0", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"));
        put("key1", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"));
        put("key2", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"));
    }})
.build();
```

