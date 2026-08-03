
# Input Parameter

This structure helps specify details of an input parameter.

*This model accepts additional fields of type Object.*

## Structure

`InputParameter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `IsNull` | `boolean` | Required | If parameter is null | boolean getIsNull() | setIsNull(boolean isNull) |
| `EndpointInputPrameterId` | `String` | Required | Unique parameter identifier for each endpoint | String getEndpointInputPrameterId() | setEndpointInputPrameterId(String endpointInputPrameterId) |
| `Id` | `String` | Required | Unique parameter identifier | String getId() | setId(String id) |
| `Name` | `String` | Required | Parameter Name | String getName() | setName(String name) |
| `Value` | `String` | Required | Parameter Value | String getValue() | setValue(String value) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.InputParameter;
import java.io.IOException;

InputParameter inputParameter = new InputParameter.Builder(
    false,
    "5a4e8675b724bb198c289f7a",
    "5a4e8675b724bb198c289f7c",
    "body",
    "{\r\n  \"name\": \"Country\",\r\n  \"field\": \"NZ\"\r\n}"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

