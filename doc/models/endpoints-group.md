
# Endpoints Group

This structure encapsulates all the attributes of an API Endpoints Group.

*This model accepts additional fields of type Object.*

## Structure

`EndpointsGroup`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Name` | `String` | Required | - | String getName() | setName(String name) |
| `Description` | `String` | Required | - | String getDescription() | setDescription(String description) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.EndpointsGroup;
import java.io.IOException;

EndpointsGroup endpointsGroup = new EndpointsGroup.Builder(
    "Petstore",
    "Everything about your pets"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

