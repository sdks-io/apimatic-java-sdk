
# Links

*This model accepts additional fields of type Object.*

## Structure

`Links`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Status` | `String` | Required | - | String getStatus() | setStatus(String status) |
| `Download` | `String` | Required | - | String getDownload() | setDownload(String download) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.Links;
import java.io.IOException;

Links links = new Links.Builder(
    "status6",
    "download8"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

