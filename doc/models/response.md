
# Response

The structure encapsulates all details of a request response

*This model accepts additional fields of type Object.*

## Structure

`Response`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Optional` | `boolean` | Required | Specify if response is optional or not | boolean getOptional() | setOptional(boolean optional) |
| `Type` | `String` | Required | Specify response type | String getType() | setType(String type) |
| `Constant` | `boolean` | Required | Specify if response is constant | boolean getConstant() | setConstant(boolean constant) |
| `IsArray` | `boolean` | Required | Specify if response is array | boolean getIsArray() | setIsArray(boolean isArray) |
| `IsStream` | `boolean` | Required | Specify if response is stream | boolean getIsStream() | setIsStream(boolean isStream) |
| `IsAttribute` | `boolean` | Required | Specify  if response has attributes | boolean getIsAttribute() | setIsAttribute(boolean isAttribute) |
| `IsMap` | `boolean` | Required | Specify if response is collected as map | boolean getIsMap() | setIsMap(boolean isMap) |
| `Attributes` | [`Attributes`](../../doc/models/attributes.md) | Required | The structure contain attribute details of a parameter type. | Attributes getAttributes() | setAttributes(Attributes attributes) |
| `Nullable` | `boolean` | Required | Specify is response is nullable | boolean getNullable() | setNullable(boolean nullable) |
| `Id` | `String` | Required | Unique response identifier | String getId() | setId(String id) |
| `Name` | `String` | Required | Response name | String getName() | setName(String name) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.Attributes;
import io.apimatic.api.models.Response;
import java.io.IOException;

Response response = new Response.Builder(
    false,
    "ServerResponse",
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
    "5a4e8675b724bb198c289f79",
    "response"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

