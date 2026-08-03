
# Csnetstandardlib

This structure contains all details that goes into package deployment.

*This model accepts additional fields of type Object.*

## Structure

`Csnetstandardlib`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | [`Id`](../../doc/models/id.md) | Optional | Unique package identifier<br><br>**Default**: `Id.ENUM_5DCD2B5893C3E31A206F30C4` | Id getId() | setId(Id id) |
| `PackageRepository` | `String` | Required | Package Repository as per platform | String getPackageRepository() | setPackageRepository(String packageRepository) |
| `PackageName` | `String` | Required | Package Name | String getPackageName() | setPackageName(String packageName) |
| `Version` | `String` | Required | - | String getVersion() | setVersion(String version) |
| `AdditionalDeploymentInformation` | `Object` | Required | Any additional platform specific deployment detail | Object getAdditionalDeploymentInformation() | setAdditionalDeploymentInformation(Object additionalDeploymentInformation) |
| `Link` | [`Link`](../../doc/models/link.md) | Optional | Link of deployed package<br><br>**Default**: `Link.ENUM_HTTPSWWWNUGETORGPACKAGESMYPACKAGE111` | Link getLink() | setLink(Link link) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.Csnetstandardlib;
import io.apimatic.api.models.Id;
import io.apimatic.api.models.Link;
import java.io.IOException;

Csnetstandardlib csnetstandardlib = new Csnetstandardlib.Builder(
    "NuGet",
    "myPackage",
    "1.1.1",
    ApiHelper.deserialize("{}")
)
.id(Id.ENUM_5DCD2B5893C3E31A206F30C4)
.link(Link.ENUM_HTTPSWWWNUGETORGPACKAGESMYPACKAGE111)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

