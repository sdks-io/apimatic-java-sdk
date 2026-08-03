
# Portal Generation Status Response

## Structure

`PortalGenerationStatusResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Status` | [`Status`](../../doc/models/status.md) | Required | - | Status getStatus() | setStatus(Status status) |
| `Errors` | `Map<String, Object>` | Optional | - | Map<String, Object> getErrors() | setErrors(Map<String, Object> errors) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.PortalGenerationStatusResponse;
import io.apimatic.api.models.Status;
import java.io.IOException;
import java.util.LinkedHashMap;

PortalGenerationStatusResponse portalGenerationStatusResponse = new PortalGenerationStatusResponse.Builder(
    Status.INPROGRESS
)
.errors(new LinkedHashMap<String, Object>() {{
        put("key0", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"));
    }})
.build();
```

