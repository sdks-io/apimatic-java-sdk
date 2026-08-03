
# Publish Package Input

*This model accepts additional fields of type Object.*

## Structure

`PublishPackageInput`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `PackageRepository` | [`PackageRepositories`](../../doc/models/package-repositories.md) | Required | - | PackageRepositories getPackageRepository() | setPackageRepository(PackageRepositories packageRepository) |
| `Template` | [`Platforms`](../../doc/models/platforms.md) | Required | The structure contains platforms that APIMatic CodeGen can generate SDKs and Docs in.<br><br>**Default**: `Platforms.CS_NET_STANDARD_LIB` | Platforms getTemplate() | setTemplate(Platforms template) |
| `PackageName` | `String` | Required | - | String getPackageName() | setPackageName(String packageName) |
| `Version` | `String` | Required | - | String getVersion() | setVersion(String version) |
| `AdditionalDeploymentInformation` | `Object` | Required | - | Object getAdditionalDeploymentInformation() | setAdditionalDeploymentInformation(Object additionalDeploymentInformation) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.PackageRepositories;
import io.apimatic.api.models.Platforms;
import io.apimatic.api.models.PublishPackageInput;
import java.io.IOException;

PublishPackageInput publishPackageInput = new PublishPackageInput.Builder(
    PackageRepositories.NPM,
    Platforms.CS_NET_STANDARD_LIB,
    "apimaticcalculatortest",
    "1.0.0",
    ApiHelper.deserialize("{}")
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

