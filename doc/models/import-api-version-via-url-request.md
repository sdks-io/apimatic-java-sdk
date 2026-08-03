
# Import Api Version via Url Request

This structure contains details of importing a new API Version

*This model accepts additional fields of type Object.*

## Structure

`ImportApiVersionViaUrlRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `VersionOverride` | `String` | Required | The version number with which the new API version will be imported. This version number will override the version specified in the API specification file.<br>APIMatic recommends versioning the API with the [versioning scheme](https://docs.apimatic.io/define-apis/basic-settings/#version) documented in the docs. | String getVersionOverride() | setVersionOverride(String versionOverride) |
| `Url` | `String` | Required | The URL for the API specification file.<br><br>**Note:** This URL should be publicly accessible. | String getUrl() | setUrl(String url) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.ImportApiVersionViaUrlRequest;
import java.io.IOException;

ImportApiVersionViaUrlRequest importApiVersionViaUrlRequest = new ImportApiVersionViaUrlRequest.Builder(
    "1.2.3",
    "https://petstore.swagger.io/v2/swagger.json"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

