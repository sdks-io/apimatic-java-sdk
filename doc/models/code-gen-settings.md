
# Code Gen Settings

APIMatic’s code generation engine has various code generation configurations to customise the behaviour and outlook across the generated SDKS. This structure encapsulates all settings for CodeGeneration.

*This model accepts additional fields of type Object.*

## Structure

`CodeGenSettings`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `IsAsync` | `boolean` | Required | Generate asynchronous code for API Calls and deserialization | boolean getIsAsync() | setIsAsync(boolean isAsync) |
| `UseHttpMethodPrefix` | `boolean` | Required | Use HTTP Method prefixes for endpoint wrappers | boolean getUseHttpMethodPrefix() | setUseHttpMethodPrefix(boolean useHttpMethodPrefix) |
| `UseModelPrefix` | `boolean` | Required | Use "Model" postfixes for generated class names | boolean getUseModelPrefix() | setUseModelPrefix(boolean useModelPrefix) |
| `UseEnumPrefix` | `boolean` | Required | Use "Enum" postfixes for enumerated types | boolean getUseEnumPrefix() | setUseEnumPrefix(boolean useEnumPrefix) |
| `UseConstructorsForConfig` | `boolean` | Required | - | boolean getUseConstructorsForConfig() | setUseConstructorsForConfig(boolean useConstructorsForConfig) |
| `UseCommonSdkLibrary` | `boolean` | Required | Use common SDK library to reduce code duplication | boolean getUseCommonSdkLibrary() | setUseCommonSdkLibrary(boolean useCommonSdkLibrary) |
| `GenerateInterfaces` | `boolean` | Required | Generates interfaces for controller classes in the generated SDKs | boolean getGenerateInterfaces() | setGenerateInterfaces(boolean generateInterfaces) |
| `GenerateAppveyorConfig` | `boolean` | Required | Generate Appveyor configuration file | boolean getGenerateAppveyorConfig() | setGenerateAppveyorConfig(boolean generateAppveyorConfig) |
| `GenerateCircleConfig` | `boolean` | Required | Generate CircleCI configuration file | boolean getGenerateCircleConfig() | setGenerateCircleConfig(boolean generateCircleConfig) |
| `GenerateJenkinsConfig` | `boolean` | Required | Generate Jenkins configuration file | boolean getGenerateJenkinsConfig() | setGenerateJenkinsConfig(boolean generateJenkinsConfig) |
| `GenerateTravisConfig` | `boolean` | Required | Generate Travis CI configuration file | boolean getGenerateTravisConfig() | setGenerateTravisConfig(boolean generateTravisConfig) |
| `AndroidUseAppManifest` | `boolean` | Required | Use "AndroidManifest.xml" for config variables in Android | boolean getAndroidUseAppManifest() | setAndroidUseAppManifest(boolean androidUseAppManifest) |
| `IosUseAppInfoPlist` | `boolean` | Required | Use "App-Info.plist" file for config variables in iOS | boolean getIosUseAppInfoPlist() | setIosUseAppInfoPlist(boolean iosUseAppInfoPlist) |
| `IosGenerateCoreData` | `boolean` | Required | Generate "CoreData" schema and entity classes in iOS? | boolean getIosGenerateCoreData() | setIosGenerateCoreData(boolean iosGenerateCoreData) |
| `RunscopeEnabled` | `boolean` | Required | Enable runscope | boolean getRunscopeEnabled() | setRunscopeEnabled(boolean runscopeEnabled) |
| `CollapseParamsToArray` | `boolean` | Required | Collect Parameters as arrays | boolean getCollapseParamsToArray() | setCollapseParamsToArray(boolean collapseParamsToArray) |
| `PreserveParameterOrder` | `boolean` | Required | Attempts to preserve parameter order for endpoints | boolean getPreserveParameterOrder() | setPreserveParameterOrder(boolean preserveParameterOrder) |
| `AppendContentHeaders` | `boolean` | Required | Append JSON/XML accept and content-type headers | boolean getAppendContentHeaders() | setAppendContentHeaders(boolean appendContentHeaders) |
| `ModelSerializationIsJson` | `boolean` | Required | - | boolean getModelSerializationIsJson() | setModelSerializationIsJson(boolean modelSerializationIsJson) |
| `Nullify404` | `boolean` | Required | Return a null value on HTTP 404 | boolean getNullify404() | setNullify404(boolean nullify404) |
| `ValidateRequiredParameters` | `boolean` | Required | Validate required parameters to be Not Null | boolean getValidateRequiredParameters() | setValidateRequiredParameters(boolean validateRequiredParameters) |
| `EnableAdditionalModelProperties` | `boolean` | Required | Allow models to have additional runtime properties | boolean getEnableAdditionalModelProperties() | setEnableAdditionalModelProperties(boolean enableAdditionalModelProperties) |
| `JavaUsePropertiesConfig` | `boolean` | Required | - | boolean getJavaUsePropertiesConfig() | setJavaUsePropertiesConfig(boolean javaUsePropertiesConfig) |
| `UseControllerPrefix` | `boolean` | Required | Use "Controller" postfixes for generated controller classes | boolean getUseControllerPrefix() | setUseControllerPrefix(boolean useControllerPrefix) |
| `UseExceptionPrefix` | `boolean` | Required | Use Exception Prefixes | boolean getUseExceptionPrefix() | setUseExceptionPrefix(boolean useExceptionPrefix) |
| `ParameterArrayFormat` | `String` | Required | Parameter Array format with index or without | String getParameterArrayFormat() | setParameterArrayFormat(String parameterArrayFormat) |
| `ObjCHttpClient` | `String` | Required | Configure the HTTP client for Objective C | String getObjCHttpClient() | setObjCHttpClient(String objCHttpClient) |
| `CSharpHttpClient` | `String` | Required | Configure the HTTP client for C# | String getCSharpHttpClient() | setCSharpHttpClient(String cSharpHttpClient) |
| `AndroidHttpClient` | `String` | Required | Configure the HTTP client for  Android | String getAndroidHttpClient() | setAndroidHttpClient(String androidHttpClient) |
| `NodeHttpClient` | `String` | Required | Configure the HTTP client for node | String getNodeHttpClient() | setNodeHttpClient(String nodeHttpClient) |
| `PhpHttpClient` | `String` | Required | Configure the HTTP client for PHP | String getPhpHttpClient() | setPhpHttpClient(String phpHttpClient) |
| `BodySerialization` | `int` | Required | - | int getBodySerialization() | setBodySerialization(int bodySerialization) |
| `ArraySerialization` | `String` | Required | Specify type of array serialisation | String getArraySerialization() | setArraySerialization(String arraySerialization) |
| `Timeout` | `int` | Required | This option specifies the duration (in seconds) after which requests would timeout | int getTimeout() | setTimeout(int timeout) |
| `EnableLogging` | `boolean` | Required | Enabling this generates code in the SDKs for logging events in the API cycle using a library. | boolean getEnableLogging() | setEnableLogging(boolean enableLogging) |
| `EnableHttpCache` | `boolean` | Required | Enabling caching of responses (not available in all languages) | boolean getEnableHttpCache() | setEnableHttpCache(boolean enableHttpCache) |
| `Retries` | `int` | Required | Specify number of retries | int getRetries() | setRetries(int retries) |
| `RetryInterval` | `int` | Required | Specify retry interval in case of failures | int getRetryInterval() | setRetryInterval(int retryInterval) |
| `GenerateAdvancedDocs` | `boolean` | Required | Generate advanced read me files | boolean getGenerateAdvancedDocs() | setGenerateAdvancedDocs(boolean generateAdvancedDocs) |
| `StoreTimezoneInformation` | `boolean` | Required | Store Timezone information for the generation | boolean getStoreTimezoneInformation() | setStoreTimezoneInformation(boolean storeTimezoneInformation) |
| `EnablePhpComposerVersionString` | `boolean` | Required | Use "Controller" postfixes for generated controller classes | boolean getEnablePhpComposerVersionString() | setEnablePhpComposerVersionString(boolean enablePhpComposerVersionString) |
| `SecurityProtocols` | `List<String>` | Required | Specify Security Protocols | List<String> getSecurityProtocols() | setSecurityProtocols(List<String> securityProtocols) |
| `UnderscoreNumbers` | `boolean` | Required | Use underscores before and after numbers for underscore case | boolean getUnderscoreNumbers() | setUnderscoreNumbers(boolean underscoreNumbers) |
| `UseSingletonPattern` | `boolean` | Required | Allow usage of a Singleton Pattern | boolean getUseSingletonPattern() | setUseSingletonPattern(boolean useSingletonPattern) |
| `DisableLinting` | `boolean` | Required | Files/dependencies used for linting are not generated if this option is enabled | boolean getDisableLinting() | setDisableLinting(boolean disableLinting) |
| `AllowSkippingSslCertVerification` | `boolean` | Required | Create a configuration option in SDKs to optionally skip certificate verification when establishing HTTPS connections. | boolean getAllowSkippingSslCertVerification() | setAllowSkippingSslCertVerification(boolean allowSkippingSslCertVerification) |
| `ApplyCustomizations` | `List<String>` | Required | Apply Customisations | List<String> getApplyCustomizations() | setApplyCustomizations(List<String> applyCustomizations) |
| `DoNotSplitWords` | `List<String>` | Required | Enabling this will stop splitting of words when converting identifiers from API specification to language-specific identifiers. | List<String> getDoNotSplitWords() | setDoNotSplitWords(List<String> doNotSplitWords) |
| `SortResources` | `boolean` | Required | Sorts resources such as endpoints, endpoint groups and models in generated documentation | boolean getSortResources() | setSortResources(boolean sortResources) |
| `EnableGlobalUserAgent` | `boolean` | Required | Enable a global user agent | boolean getEnableGlobalUserAgent() | setEnableGlobalUserAgent(boolean enableGlobalUserAgent) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import io.apimatic.api.ApiHelper;
import io.apimatic.api.models.CodeGenSettings;
import java.io.IOException;
import java.util.Arrays;

CodeGenSettings codeGenSettings = new CodeGenSettings.Builder(
    true,
    true,
    false,
    true,
    false,
    false,
    false,
    false,
    false,
    false,
    false,
    false,
    false,
    false,
    false,
    false,
    true,
    true,
    true,
    false,
    false,
    false,
    false,
    true,
    true,
    "ParamArrayWithIndex",
    "UNIREST",
    "UNIREST",
    "ANDROID_OK",
    "NODE_REQUEST",
    "UNIREST",
    0,
    "Indexed",
    0,
    false,
    false,
    0,
    1,
    true,
    false,
    false,
    Arrays.asList(
        "Ssl3",
        "Tls"
    ),
    true,
    true,
    false,
    false,
    Arrays.asList(

    ),
    Arrays.asList(

    ),
    false,
    true
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

