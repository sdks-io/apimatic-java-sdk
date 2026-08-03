
# Portal Generation Async Response

## Structure

`PortalGenerationAsyncResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `UUID` | Required | - | UUID getId() | setId(UUID id) |
| `Links` | [`Links`](../../doc/models/links.md) | Required | - | Links getLinks() | setLinks(Links links) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.Links;
import io.apimatic.api.models.PortalGenerationAsyncResponse;
import java.io.IOException;
import java.util.UUID;

PortalGenerationAsyncResponse portalGenerationAsyncResponse = new PortalGenerationAsyncResponse.Builder(
    UUID.fromString("0194d0da-8d75-7c04-b517-6a9342b114e8"),
    new Links.Builder(
        "https://api.apimatic.io/portal/v2/0194d0da-8d75-7c04-b517-6a9342b114e8/status",
        "https://api.apimatic.io/portal/v2/0194d0da-8d75-7c04-b517-6a9342b114e8/download"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build()
)
.build();
```

