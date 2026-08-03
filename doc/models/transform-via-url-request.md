
# Transform via Url Request

This structure puts together the URL of the file to be transformed, along with the desired export format.

*This model accepts additional fields of type Object.*

## Structure

`TransformViaUrlRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Url` | `String` | Required | The URL for the API specification file.<br><br>**Note:** This URL should be publicly accessible. | String getUrl() | setUrl(String url) |
| `ExportFormat` | [`ExportFormats`](../../doc/models/export-formats.md) | Required | The structure contains API specification formats that Transformer can convert to. | ExportFormats getExportFormat() | setExportFormat(ExportFormats exportFormat) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.ExportFormats;
import io.apimatic.api.models.TransformViaUrlRequest;
import java.io.IOException;

TransformViaUrlRequest transformViaUrlRequest = new TransformViaUrlRequest.Builder(
    "https://petstore.swagger.io/v2/swagger.json",
    ExportFormats.APIMATIC
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

