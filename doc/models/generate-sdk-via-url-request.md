
# Generate Sdk via Url Request

*This model accepts additional fields of type Object.*

## Structure

`GenerateSdkViaUrlRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Url` | `String` | Required | The URL for the API specification file.<br><br>**Note:** This URL should be publicly accessible. | String getUrl() | setUrl(String url) |
| `Template` | [`Platforms`](../../doc/models/platforms.md) | Required | The structure contains platforms that APIMatic CodeGen can generate SDKs and Docs in.<br><br>**Default**: `Platforms.CS_NET_STANDARD_LIB` | Platforms getTemplate() | setTemplate(Platforms template) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.GenerateSdkViaUrlRequest;
import io.apimatic.api.models.Platforms;
import java.io.IOException;

GenerateSdkViaUrlRequest generateSdkViaUrlRequest = new GenerateSdkViaUrlRequest.Builder(
    "http://petstore.swagger.io/v2/swagger.json",
    Platforms.CS_NET_STANDARD_LIB
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

