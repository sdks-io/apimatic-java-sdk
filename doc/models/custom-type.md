
# Custom Type

This structure helps creates a new complex model type.

*This model accepts additional fields of type Object.*

## Structure

`CustomType`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | Unique Type Identifier | String getId() | setId(String id) |
| `ApiId` | `String` | Required | Unique  API Entity identifier | String getApiId() | setApiId(String apiId) |
| `Name` | `String` | Required | Custom Type Name | String getName() | setName(String name) |
| `BaseType` | `String` | Required | Data Format | String getBaseType() | setBaseType(String baseType) |
| `ImplementationType` | [`ImplementationType`](../../doc/models/implementation-type.md) | Required | The structure helps describes the nature of implementation of a  custom model. A model can be of 3 types. | ImplementationType getImplementationType() | setImplementationType(ImplementationType implementationType) |
| `Fields` | [`List<Field>`](../../doc/models/field.md) | Required | Type Fields | List<Field> getFields() | setFields(List<Field> fields) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.CustomType;
import io.apimatic.api.models.ImplementationType;
import java.io.IOException;
import java.util.Arrays;

CustomType customType = new CustomType.Builder(
    "5a4e8675b724bb198c289ff6",
    "5a4e8675b724bb198c289fe9",
    "Job",
    "baseType8",
    ImplementationType.STRUCTURE,
    Arrays.asList(

    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

