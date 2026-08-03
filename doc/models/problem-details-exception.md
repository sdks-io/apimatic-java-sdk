
# Problem Details Exception

*This model accepts additional fields of type Object.*

## Structure

`ProblemDetailsException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Type` | `String` | Optional | - | String getType() | setType(String type) |
| `Title` | `String` | Optional | - | String getTitle() | setTitle(String title) |
| `Status` | `Integer` | Optional | - | Integer getStatus() | setStatus(Integer status) |
| `Detail` | `String` | Optional | - | String getDetail() | setDetail(String detail) |
| `Instance` | `String` | Optional | - | String getInstance() | setInstance(String instance) |
| `Errors` | `Map<String, Object>` | Optional | - | Map<String, Object> getErrors() | setErrors(Map<String, Object> errors) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
try {
    // make the API call
} catch (ProblemDetailsException e) {
    e.printStackTrace();
} catch (ApiException e) {
    e.printStackTrace();
}
```

