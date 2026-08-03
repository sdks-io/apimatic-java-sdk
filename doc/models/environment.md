
# Environment

An environment consists of a set of servers with base URL values. The environment can be changed programatically allowing rapid switching between different environments. For example the user can specify a Production and Testing Environment and switch between them in the generated SDK.

*This model accepts additional fields of type Object.*

## Structure

`Environment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | Unique Environment Identifier | String getId() | setId(String id) |
| `Name` | `String` | Required | Environment Name | String getName() | setName(String name) |
| `Servers` | [`List<Server>`](../../doc/models/server.md) | Required | The user can specify multiple servers within an environment. A server comprises of a name and a url. | List<Server> getServers() | setServers(List<Server> servers) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.Environment;
import io.apimatic.api.models.Server;
import java.io.IOException;
import java.util.Arrays;

Environment environment = new Environment.Builder(
    "5be0a21a83b41d0d8cdcd832",
    "production",
    Arrays.asList(
        new Server.Builder(
            "5be0a21a83b41d0d8cdcd831",
            "default",
            "{defaultServerUrl}"
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

