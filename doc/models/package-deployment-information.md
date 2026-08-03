
# Package Deployment Information

The structure contains Package Deployment Information along with Id.

*This model accepts additional fields of type Object.*

## Structure

`PackageDeploymentInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | Package Deployment Identifier | String getId() | setId(String id) |
| `TemplatesPackageDeploymentInformation` | [`TemplatesPackageDeploymentInformation`](../../doc/models/templates-package-deployment-information.md) | Required | This structure encapsulates all package deployment details. | TemplatesPackageDeploymentInformation getTemplatesPackageDeploymentInformation() | setTemplatesPackageDeploymentInformation(TemplatesPackageDeploymentInformation templatesPackageDeploymentInformation) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.Csnetstandardlib;
import io.apimatic.api.models.Id;
import io.apimatic.api.models.Link;
import io.apimatic.api.models.PackageDeploymentInformation;
import io.apimatic.api.models.TemplatesPackageDeploymentInformation;
import java.io.IOException;

PackageDeploymentInformation packageDeploymentInformation = new PackageDeploymentInformation.Builder(
    "5dcc0560dfe543169893ca01",
    new TemplatesPackageDeploymentInformation.Builder(
        new Csnetstandardlib.Builder(
            "NuGet",
            "myPackage",
            "1.1.1",
            ApiHelper.deserialize("{}")
        )
        .id(Id.ENUM_5DCD2B5893C3E31A206F30C4)
        .link(Link.ENUM_HTTPSWWWNUGETORGPACKAGESMYPACKAGE111)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build()
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

