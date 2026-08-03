
# Update Templates Package Deployment Information

This structure helps update package deployment details.

*This model accepts additional fields of type Object.*

## Structure

`UpdateTemplatesPackageDeploymentInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `CsNetStandardLib` | [`Csnetstandardlib`](../../doc/models/csnetstandardlib.md) | Required | This structure contains all details that goes into package deployment. | Csnetstandardlib getCsNetStandardLib() | setCsNetStandardLib(Csnetstandardlib csNetStandardLib) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.Csnetstandardlib;
import io.apimatic.api.models.Id;
import io.apimatic.api.models.Link;
import io.apimatic.api.models.UpdateTemplatesPackageDeploymentInformation;
import java.io.IOException;

UpdateTemplatesPackageDeploymentInformation updateTemplatesPackageDeploymentInformation = new UpdateTemplatesPackageDeploymentInformation.Builder(
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
.build();
```

