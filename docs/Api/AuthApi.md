# RewardsWise\Yodlee\OpenAPI\Client\AuthApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteApiKey()**](AuthApi.md#deleteApiKey) | **DELETE** /auth/apiKey/{key} | Delete API Key |
| [**deleteToken()**](AuthApi.md#deleteToken) | **DELETE** /auth/token | Delete Token |
| [**generateAccessToken()**](AuthApi.md#generateAccessToken) | **POST** /auth/token | Generate Access Token |
| [**generateApiKey()**](AuthApi.md#generateApiKey) | **POST** /auth/apiKey | Generate API Key |
| [**getApiKeys()**](AuthApi.md#getApiKeys) | **GET** /auth/apiKey | Get API Keys |


## `deleteApiKey()`

```php
deleteApiKey($key)
```

Delete API Key

This endpoint allows an existing API key to be deleted.<br>You can use one of the following authorization methods to access this API:<br><ol><li>cobsession</li><li>JWT token</li></ol> <b>Notes:</b> <li>This service is not available in developer sandbox environment and will be made availablefor testing in your dedicated environment.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$key = 'key_example'; // string | key

try {
    $apiInstance->deleteApiKey($key);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->deleteApiKey: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **key** | **string**| key | |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteToken()`

```php
deleteToken()
```

Delete Token

This endpoint revokes the token passed in the Authorization header. This service is applicable for JWT-based (and all API key-based) authentication and also client credential (clientId and secret) based authentication. This service does not return a response body. The HTTP response code is 204 (success with no content). <br>Tokens generally have limited lifetime of up to 30 minutes. You will call this service when you finish working with one user, and you want to delete the valid token rather than simply letting it expire.<br><br><b>Note:</b> <li>Revoking an access token (either type, admin or a user token) can take up to 2 minutes, as the tokens are stored on a distributed system.<br/>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->deleteToken();
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->deleteToken: ', $e->getMessage(), PHP_EOL;
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
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `generateAccessToken()`

```php
generateAccessToken($client_id, $secret): \RewardsWise\Yodlee\OpenAPI\Client\Model\ClientCredentialTokenResponse
```

Generate Access Token

<b>Generate Access Token using client credential authentication.</b><br>This service returns access tokens required to access Yodlee 1.1 APIs. These tokens are the simplest and easiest of several alternatives for authenticating with Yodlee servers.<br>The most commonly used services obtain data specific to an end user (your customer). For these services, you need a <b>user access token</b>. These are simply tokens created with the user name parameter (<b>loginName</b>) set to the id of your end user.  <i><br><br><b>Note:</b> You determine this id and you must ensure it's unique among all your customers.</i> <br><br>Each token issued has an associated user. The token passed in the http headers explicitly names the user referenced in that API call.<br><br>Some of the APIs do administrative work, and don't reference an end user. <br/>One example of administrative work is key management. Another example is registering a new user explicitly, with <b>POST /user/register</b> call or subscribe to webhook, with <b>POST /config/notifications/events/{eventName}</b>. <br/>To invoke these, you need an <b>admin access token</b>. Create this by passing in your admin user login name in place of a regular user name.<br><br>This service also allows for simplified registration of new users. Any time you pass in a user name not already in use, the system will automatically implicitly create a new user for you. <br>This user will naturally have very few associated details. You can later provide additional user information by calling the <b>PUT user/register service</b>.<br><br><b>Notes:</b><ul><li>The header <code>Authorization</code> does not apply to this service.</li><li>The content type has to be passed as application/x-www-form-urlencoded.<li>Upgrading to client credential authentication requires infrastructure reconfiguration. <li>Customers wishing to switch from another authentication scheme to client credential authentication, please contact Yodlee Client Services.</li><li>Default expiry time of user access token and admin access token is 30 minutes.</li></ul>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$client_id = 'client_id_example'; // string | clientId issued by Yodlee is used to generate the OAuth token for authentication.
$secret = 'secret_example'; // string | secret issued by Yodlee is used to generate the OAuth token for authentication.

try {
    $result = $apiInstance->generateAccessToken($client_id, $secret);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->generateAccessToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **client_id** | **string**| clientId issued by Yodlee is used to generate the OAuth token for authentication. | [optional] |
| **secret** | **string**| secret issued by Yodlee is used to generate the OAuth token for authentication. | [optional] |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\ClientCredentialTokenResponse**](../Model/ClientCredentialTokenResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/x-www-form-urlencoded`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `generateApiKey()`

```php
generateApiKey($api_key_request): \RewardsWise\Yodlee\OpenAPI\Client\Model\ApiKeyResponse
```

Generate API Key

This endpoint is used to generate an API key. The RSA public key you provide should be in 2048 bit PKCS#8 encoded format. <br>A public key is a mandatory input for generating the API key.<br/>The public key should be a unique key. The apiKeyId you get in the response is what you should use to generate the JWT token.<br> You can use one of the following authorization methods to access<br/>this API:<br><ol><li>cobsession</li><li>JWT token</li></ol> Alternatively, you can use base 64 encoded cobrandLogin and cobrandPassword in the Authorization header (Format: Authorization: Basic <encoded value of cobrandLogin: cobrandPassword>)<br><br><b>Note:</b><br><li>This service is not available in developer sandbox environment and will be made available for testing in your dedicated environment. The content type has to be passed as application/json for the body parameter.</li>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$api_key_request = new \RewardsWise\Yodlee\OpenAPI\Client\Model\ApiKeyRequest(); // \RewardsWise\Yodlee\OpenAPI\Client\Model\ApiKeyRequest | apiKeyRequest

try {
    $result = $apiInstance->generateApiKey($api_key_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->generateApiKey: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **api_key_request** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\ApiKeyRequest**](../Model/ApiKeyRequest.md)| apiKeyRequest | |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\ApiKeyResponse**](../Model/ApiKeyResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getApiKeys()`

```php
getApiKeys(): \RewardsWise\Yodlee\OpenAPI\Client\Model\ApiKeyResponse
```

Get API Keys

This endpoint provides the list of API keys that exist for a customer.<br>You can use one of the following authorization methods to access this API:<br><ol><li>cobsession</li><li>JWT token</li></ol><b>Notes:</b><li>This service is not available in developer sandbox environment and will be made available for testing in your dedicated environment.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\AuthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getApiKeys();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AuthApi->getApiKeys: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\ApiKeyResponse**](../Model/ApiKeyResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
