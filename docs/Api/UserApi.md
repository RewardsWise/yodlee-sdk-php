# OpenAPI\Client\UserApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getAccessTokens()**](UserApi.md#getAccessTokens) | **GET** /user/accessTokens | Get Access Tokens |
| [**getUser()**](UserApi.md#getUser) | **GET** /user | Get User Details |
| [**registerUser()**](UserApi.md#registerUser) | **POST** /user/register | Register User |
| [**samlLogin()**](UserApi.md#samlLogin) | **POST** /user/samlLogin | Saml Login |
| [**unregister()**](UserApi.md#unregister) | **DELETE** /user/unregister | Delete User |
| [**updateUser()**](UserApi.md#updateUser) | **PUT** /user | Update User Details |
| [**userLogout()**](UserApi.md#userLogout) | **POST** /user/logout | User Logout |


## `getAccessTokens()`

```php
getAccessTokens($app_ids): \OpenAPI\Client\Model\UserAccessTokensResponse
```

Get Access Tokens

The Get Access Tokens service is used to retrieve the access tokens for the application id(s) provided.<br>URL in the response can be used to launch the application for which token is requested.<br><br><b>Note:</b> <li>This endpoint is deprecated for customers using the API Key-based authentication and is applicable only to customers who use the SAML-based authentication.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\UserApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$app_ids = 'app_ids_example'; // string | appIds

try {
    $result = $apiInstance->getAccessTokens($app_ids);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UserApi->getAccessTokens: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **app_ids** | **string**| appIds | |

### Return type

[**\OpenAPI\Client\Model\UserAccessTokensResponse**](../Model/UserAccessTokensResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getUser()`

```php
getUser(): \OpenAPI\Client\Model\UserDetailResponse
```

Get User Details

The get user details service is used to get the user profile information and the application preferences set at the time of user registration.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\UserApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getUser();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UserApi->getUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\OpenAPI\Client\Model\UserDetailResponse**](../Model/UserDetailResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `registerUser()`

```php
registerUser($user_request): \OpenAPI\Client\Model\UserResponse
```

Register User

The register user service is used to register a user in Yodlee.<br>The loginName cannot include spaces and must be between 3 and 150 characters.<br>locale passed must be one of the supported locales for the customer. <br>Currency provided in the input will be respected in the derived services and the amount fields in the response will be provided in the preferred currency.<br>userParam is accepted as a body parameter. <br><br><b>Note:</b> <li>The content type has to be passed as application/json for the body parameter.</li> <li>We recommend you to not use special characters in loginName other than \"@\", \"#\", \"_\" & \"-\"</li>.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\UserApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$user_request = new \OpenAPI\Client\Model\UserRequest(); // \OpenAPI\Client\Model\UserRequest | userRequest

try {
    $result = $apiInstance->registerUser($user_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UserApi->registerUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_request** | [**\OpenAPI\Client\Model\UserRequest**](../Model/UserRequest.md)| userRequest | |

### Return type

[**\OpenAPI\Client\Model\UserResponse**](../Model/UserResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `samlLogin()`

```php
samlLogin($issuer, $saml_response, $source): \OpenAPI\Client\Model\UserResponse
```

Saml Login

The SAML login service is used to authenticate system users with a SAML response.<br>A new user will be created with the input provided if that user isn't already in the system.<br>For existing users, the system will make updates based on changes or new information.<br>When authentication is successful, a user session token is returned.<br><br><b>Note:</b> <li>The content type has to be passed as application/x-www-form-urlencoded. <li>issuer, source and samlResponse should be passed as body parameters.</li>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\UserApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$issuer = 'issuer_example'; // string | issuer
$saml_response = 'saml_response_example'; // string | samlResponse
$source = 'source_example'; // string | source

try {
    $result = $apiInstance->samlLogin($issuer, $saml_response, $source);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UserApi->samlLogin: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **issuer** | **string**| issuer | |
| **saml_response** | **string**| samlResponse | |
| **source** | **string**| source | [optional] |

### Return type

[**\OpenAPI\Client\Model\UserResponse**](../Model/UserResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `unregister()`

```php
unregister()
```

Delete User

The delete user service is used to delete or unregister a user from Yodlee. <br>Once deleted, the information related to the users cannot be retrieved. <br>The HTTP response code is 204 (Success without content)<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\UserApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->unregister();
} catch (Exception $e) {
    echo 'Exception when calling UserApi->unregister: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateUser()`

```php
updateUser($user_request)
```

Update User Details

The update user details service is used to update user details like name, address, currency preference, etc.<br>Currency provided in the input will be respected in the derived services and the amount fields in the response will be provided in the preferred currency.<br>The HTTP response code is 204 (Success without content). <br><br> <b>Login Name Change Feature:</b> loginName can be passed to update the user's login name. Once the loginName is updated, to access the user's data, a token with the changed loginName must be created. This feature is supported only Client Credentials authentication methods.<br><b>Note:</b> <li>We strongly recommend to immediately delete the old access token once the user's loginName is successfully changed to avoid misuse.</li> <li>After updating the login name, the already sent data extract events with the old login name will no more be functional. Replace the loginName with new loginName or try polling method to retrieve the data.</li><br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\UserApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$user_request = new \OpenAPI\Client\Model\UpdateUserRequest(); // \OpenAPI\Client\Model\UpdateUserRequest | userRequest

try {
    $apiInstance->updateUser($user_request);
} catch (Exception $e) {
    echo 'Exception when calling UserApi->updateUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_request** | [**\OpenAPI\Client\Model\UpdateUserRequest**](../Model/UpdateUserRequest.md)| userRequest | |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `userLogout()`

```php
userLogout()
```

User Logout

<b>Deprecated</b>: This endpoint is deprecated for API Key-based authentication. The user logout service allows the user to log out of the application.<br>The service does not return a response body. The HTTP response code is 204 (Success with no content).<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\UserApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->userLogout();
} catch (Exception $e) {
    echo 'Exception when calling UserApi->userLogout: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
