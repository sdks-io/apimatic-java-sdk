
# Bad Request Response Sdk Exception

Standard JSON error response for bad requests

*This model accepts additional fields of type Object.*

## Structure

`BadRequestResponseSdkException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Message` | `String` | Optional | Error message describing the bad request | String getMessageField() | setMessageField(String messageField) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
try {
    // make the API call
} catch (BadRequestResponseSdkException e) {
    e.printStackTrace();
} catch (ApiException e) {
    e.printStackTrace();
}
```

