
# Custom Header Signature



Documentation for accessing and setting credentials for Authorization.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| Authorization | `String` | Auth Header. Replace {x-auth-key} with your Auth Key. | `authorization` | `getAuthorization()` |



**Note:** Auth credentials can be set using `customHeaderAuthenticationCredentials` in the client builder and accessed through `getCustomHeaderAuthenticationCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```java
import io.apimatic.api.ApimaticApiClient;
import io.apimatic.api.authentication.CustomHeaderAuthenticationModel;

public class Program {
    public static void main(String[] args) {
        ApimaticApiClient client = new ApimaticApiClient.Builder()
            .customHeaderAuthenticationCredentials(new CustomHeaderAuthenticationModel.Builder(
                    "Authorization"
                )
                .build())
            .build();
    }
}
```


