
# Author Identifiers

*This model accepts additional fields of type Object.*

## Structure

`AuthorIdentifiers`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Email` | `String` | Required | - | String getEmail() | setEmail(String email) |
| `UserName` | `String` | Required | - | String getUserName() | setUserName(String userName) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.AuthorIdentifiers;
import java.io.IOException;

AuthorIdentifiers authorIdentifiers = new AuthorIdentifiers.Builder(
    "shayanjalil@gmail.com",
    "shayanjalil"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

