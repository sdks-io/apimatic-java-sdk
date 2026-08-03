
# Published Package

*This model accepts additional fields of type Object.*

## Structure

`PublishedPackage`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | - | String getId() | setId(String id) |
| `CreatedOn` | `String` | Required | - | String getCreatedOn() | setCreatedOn(String createdOn) |
| `ApiEntityId` | `String` | Required | - | String getApiEntityId() | setApiEntityId(String apiEntityId) |
| `PackageRepository` | `String` | Required | - | String getPackageRepository() | setPackageRepository(String packageRepository) |
| `Template` | `String` | Required | - | String getTemplate() | setTemplate(String template) |
| `PackageName` | `String` | Required | - | String getPackageName() | setPackageName(String packageName) |
| `Version` | `String` | Required | - | String getVersion() | setVersion(String version) |
| `AdditionalDeploymentInformation` | `Object` | Required | - | Object getAdditionalDeploymentInformation() | setAdditionalDeploymentInformation(Object additionalDeploymentInformation) |
| `AuthorIdentifiers` | [`AuthorIdentifiers`](../../doc/models/author-identifiers.md) | Required | - | AuthorIdentifiers getAuthorIdentifiers() | setAuthorIdentifiers(AuthorIdentifiers authorIdentifiers) |
| `Link` | `String` | Required | - | String getLink() | setLink(String link) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.AuthorIdentifiers;
import io.apimatic.api.models.PublishedPackage;
import java.io.IOException;

PublishedPackage publishedPackage = new PublishedPackage.Builder(
    "5e8602472ac3db42ec7f097f",
    "2020-04-02T15:18:03.931Z",
    "5e8217662ac3ed0b20b0dece",
    "Npm",
    "NODE_JAVASCRIPT_LIB",
    "apimaticcalculatortest",
    "1.0.0",
    ApiHelper.deserialize("{}"),
    new AuthorIdentifiers.Builder(
        "shayanjalil@gmail.com",
        "shayanjalil"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build(),
    "https://www.npmjs.com/package/apimaticcalculatortest/v/1.0.0"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

