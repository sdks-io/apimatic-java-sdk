
# Server

The user can specify multiple servers within an environment. A server comprises of a name and a URL. The names of the hosts remain consistent over different environments but their values may vary. The URL values can contain any number of parameters defined.

*This model accepts additional fields of type Object.*

## Structure

`Server`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | Unique Server identifier | String getId() | setId(String id) |
| `Name` | `String` | Required | Server Name | String getName() | setName(String name) |
| `Url` | `String` | Required | Server URL | String getUrl() | setUrl(String url) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.Server;
import java.io.IOException;

Server server = new Server.Builder(
    "5be0a21a83b41d0d8cdcd831",
    "default",
    "{defaultServerUrl}"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

