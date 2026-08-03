
# Unauthorized Response Exception

*This model accepts additional fields of type Object.*

## Structure

`UnauthorizedResponseException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Message` | `String` | Optional | - | String getMessageField() | setMessageField(String messageField) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
try {
    // make the API call
} catch (UnauthorizedResponseException e) {
    e.printStackTrace();
} catch (ApiException e) {
    e.printStackTrace();
}
```

