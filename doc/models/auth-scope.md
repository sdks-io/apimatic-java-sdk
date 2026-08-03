
# Auth Scope

*This model accepts additional fields of type Object.*

## Structure

`AuthScope`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | Scope Id | String getId() | setId(String id) |
| `Name` | `String` | Required | Scope Name | String getName() | setName(String name) |
| `Value` | `String` | Required | Scope Value | String getValue() | setValue(String value) |
| `Description` | `String` | Required | Scope Description | String getDescription() | setDescription(String description) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.AuthScope;
import java.io.IOException;

AuthScope authScope = new AuthScope.Builder(
    "5be0a21a83b41d0d8cdcd81d",
    "readpets",
    "read:pets",
    "read your pets"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

