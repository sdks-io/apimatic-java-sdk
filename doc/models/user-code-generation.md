
# User Code Generation

The Code Generation structure encapsulates all the  the details of an SDK generation performed by a user.

*This model accepts additional fields of type Object.*

## Structure

`UserCodeGeneration`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | Unique Code Generation Identifier | String getId() | setId(String id) |
| `Template` | [`Platforms`](../../doc/models/platforms.md) | Required | The structure contains platforms that APIMatic CodeGen can generate SDKs and Docs in.<br><br>**Default**: `Platforms.CS_NET_STANDARD_LIB` | Platforms getTemplate() | setTemplate(Platforms template) |
| `GeneratedFile` | `String` | Required | The generated SDK | String getGeneratedFile() | setGeneratedFile(String generatedFile) |
| `GeneratedOn` | `LocalDateTime` | Required | Generation Date and Time | LocalDateTime getGeneratedOn() | setGeneratedOn(LocalDateTime generatedOn) |
| `HashCode` | `String` | Required | The md5 hash of the API Description | String getHashCode() | setHashCode(String hashCode) |
| `CodeGenerationSource` | `String` | Required | Generation Source | String getCodeGenerationSource() | setCodeGenerationSource(String codeGenerationSource) |
| `CodeGenVersion` | `String` | Required | Generation Version | String getCodeGenVersion() | setCodeGenVersion(String codeGenVersion) |
| `Success` | `boolean` | Required | Generation Status | boolean getSuccess() | setSuccess(boolean success) |
| `UserId` | `String` | Required | Unique User Identifier | String getUserId() | setUserId(String userId) |
| `InputFile` | `String` | Required | API Specification file in a supported format | String getInputFile() | setInputFile(String inputFile) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.DateTimeHelper;
import io.apimatic.api.models.Platforms;
import io.apimatic.api.models.UserCodeGeneration;
import java.io.IOException;

UserCodeGeneration userCodeGeneration = new UserCodeGeneration.Builder(
    "5be08b2d83b41d0d8cdb3289",
    Platforms.CS_NET_STANDARD_LIB,
    "https://api.apimatic.io/code-generations/5be08b2d83b41d0d8cdb3289/generated-sdk",
    DateTimeHelper.fromRfc8601DateTime("2018-11-05T18:25:46Z"),
    "77BDA4F625EF512B336D0A77CE2BB2B6",
    "Api",
    "1",
    true,
    "5afc60380b9949253c6b7776",
    "https://api.apimatic.io/code-generations/5be08d7b83b41d0d8cdb3958/input-file"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

