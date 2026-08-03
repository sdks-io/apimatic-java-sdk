
# Server Configuration

Server configurations can be used to create multiple environments, multiple servers that can be used with specific endpoints and server URLs with template paramters.

*This model accepts additional fields of type Object.*

## Structure

`ServerConfiguration`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | Server Config Identifier | String getId() | setId(String id) |
| `DefaultEnvironment` | `String` | Required | Default Environment | String getDefaultEnvironment() | setDefaultEnvironment(String defaultEnvironment) |
| `DefaultServer` | `String` | Required | Default Server | String getDefaultServer() | setDefaultServer(String defaultServer) |
| `Environments` | [`List<Environment>`](../../doc/models/environment.md) | Required | Environment Identifier and Name | List<Environment> getEnvironments() | setEnvironments(List<Environment> environments) |
| `Parameters` | [`List<Parameter>`](../../doc/models/parameter.md) | Required | Parameter Attributes | List<Parameter> getParameters() | setParameters(List<Parameter> parameters) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.Attributes;
import io.apimatic.api.models.Environment;
import io.apimatic.api.models.Parameter;
import io.apimatic.api.models.Server;
import io.apimatic.api.models.ServerConfiguration;
import java.io.IOException;
import java.util.Arrays;

ServerConfiguration serverConfiguration = new ServerConfiguration.Builder(
    "5be0a21a83b41d0d8cdcd835",
    "production",
    "default",
    Arrays.asList(
        new Environment.Builder(
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
        .build()
    ),
    Arrays.asList(
        new Parameter.Builder(
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
            "defaultValue2",
            "Body"
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

