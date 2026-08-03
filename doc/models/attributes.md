
# Attributes

The structure contain attribute details of a parameter type.

*This model accepts additional fields of type Object.*

## Structure

`Attributes`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | Unique Attribute Identifier | String getId() | setId(String id) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.Attributes;
import java.io.IOException;

Attributes attributes = new Attributes.Builder(
    "5be1603083b41d0b50110551"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

