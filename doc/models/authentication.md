
# Authentication

This Structure encapsulates all details of API authentication.

*This model accepts additional fields of type Object.*

## Structure

`Authentication`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | Auth Id | String getId() | setId(String id) |
| `AuthType` | `String` | Required | Auth Type | String getAuthType() | setAuthType(String authType) |
| `Scopes` | [`List<AuthScope>`](../../doc/models/auth-scope.md) | Required | Scope | List<AuthScope> getScopes() | setScopes(List<AuthScope> scopes) |
| `Parameters` | `List<String>` | Required | Auth Params | List<String> getParameters() | setParameters(List<String> parameters) |
| `AuthScopes` | `List<String>` | Required | Auth Scopes | List<String> getAuthScopes() | setAuthScopes(List<String> authScopes) |
| `AuthGrantTypes` | `List<String>` | Required | Auth Grant Types | List<String> getAuthGrantTypes() | setAuthGrantTypes(List<String> authGrantTypes) |
| `ParamFormats` | `Object` | Required | Paramater Formats | Object getParamFormats() | setParamFormats(Object paramFormats) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.Authentication;
import java.io.IOException;
import java.util.Arrays;

Authentication authentication = new Authentication.Builder(
    "5be0a21a83b41d0d8cdcd80f",
    "None",
    Arrays.asList(

    ),
    Arrays.asList(

    ),
    Arrays.asList(

    ),
    Arrays.asList(

    ),
    ApiHelper.deserialize("{}")
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

