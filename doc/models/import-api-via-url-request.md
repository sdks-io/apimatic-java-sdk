
# Import Api via Url Request

Contains a url field to allow Apis to be imported via url

*This model accepts additional fields of type Object.*

## Structure

`ImportApiViaUrlRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Url` | `String` | Required | The URL for the API specification file.<br><br>**Note:** This URL should be publicly accessible. | String getUrl() | setUrl(String url) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.ImportApiViaUrlRequest;
import java.io.IOException;

ImportApiViaUrlRequest importApiViaUrlRequest = new ImportApiViaUrlRequest.Builder(
    "https://petstore.swagger.io/v2/swagger.json"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

