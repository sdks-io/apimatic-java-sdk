
# Field

This structure encapsulates all details of a parameter.

*This model accepts additional fields of type Object.*

## Structure

`Field`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Optional` | `boolean` | Required | If parameter is optional | boolean getOptional() | setOptional(boolean optional) |
| `Type` | `String` | Required | Type of Parameter | String getType() | setType(String type) |
| `Constant` | `boolean` | Required | IF Parameter is constant | boolean getConstant() | setConstant(boolean constant) |
| `IsArray` | `boolean` | Required | If Param is collected as array | boolean getIsArray() | setIsArray(boolean isArray) |
| `IsStream` | `boolean` | Required | - | boolean getIsStream() | setIsStream(boolean isStream) |
| `IsAttribute` | `boolean` | Required | - | boolean getIsAttribute() | setIsAttribute(boolean isAttribute) |
| `IsMap` | `boolean` | Required | - | boolean getIsMap() | setIsMap(boolean isMap) |
| `Attributes` | [`Attributes`](../../doc/models/attributes.md) | Required | The structure contain attribute details of a parameter type. | Attributes getAttributes() | setAttributes(Attributes attributes) |
| `Nullable` | `boolean` | Required | If Parameter is nullable | boolean getNullable() | setNullable(boolean nullable) |
| `Id` | `String` | Required | Unique Parameter identifier | String getId() | setId(String id) |
| `Name` | `String` | Required | Parameter Name | String getName() | setName(String name) |
| `Description` | `String` | Required | Parameter Description | String getDescription() | setDescription(String description) |
| `DefaultValue` | `String` | Required | Default Values of a Parameter | String getDefaultValue() | setDefaultValue(String defaultValue) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.Attributes;
import io.apimatic.api.models.Field;
import java.io.IOException;

Field field = new Field.Builder(
    false,
    "test\\r\\nstringEncoding",
    false,
    false,
    false,
    false,
    false,
    new Attributes.Builder(
        "5be1603083b41d0b50110551"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build(),
    false,
    "5a4e8675b724bb198c289f7a",
    "body",
    "description4",
    "defaultValue0"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

