
# Update Package Deployment Information

This structure is used to update package deployment details.

*This model accepts additional fields of type Object.*

## Structure

`UpdatePackageDeploymentInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `TemplatesPackageDeploymentInformation` | [`UpdateTemplatesPackageDeploymentInformation`](../../doc/models/update-templates-package-deployment-information.md) | Required | This structure helps update package deployment details. | UpdateTemplatesPackageDeploymentInformation getTemplatesPackageDeploymentInformation() | setTemplatesPackageDeploymentInformation(UpdateTemplatesPackageDeploymentInformation templatesPackageDeploymentInformation) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.Csnetstandardlib;
import io.apimatic.api.models.Id;
import io.apimatic.api.models.Link;
import io.apimatic.api.models.UpdatePackageDeploymentInformation;
import io.apimatic.api.models.UpdateTemplatesPackageDeploymentInformation;
import java.io.IOException;

UpdatePackageDeploymentInformation updatePackageDeploymentInformation = new UpdatePackageDeploymentInformation.Builder(
    new UpdateTemplatesPackageDeploymentInformation.Builder(
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

