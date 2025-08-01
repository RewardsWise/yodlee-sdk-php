# OpenAPI\Client\AccountTokenApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**generatePaymentProcessorToken()**](AccountTokenApi.md#generatePaymentProcessorToken) | **POST** /paymentProcessor/token | Create Account Token |
| [**revokePaymentProcessorToken()**](AccountTokenApi.md#revokePaymentProcessorToken) | **DELETE** /paymentProcessor/token | Delete Account Token |


## `generatePaymentProcessorToken()`

```php
generatePaymentProcessorToken($token_request): \OpenAPI\Client\Model\PaymentProcessorTokenResponse
```

Create Account Token

The create account token service allows you to create a secure <code>processorToken</code> for a user's verified financial account. This <code>processorToken</code> can then be shared with one of our payment processor partners.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\AccountTokenApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$token_request = new \OpenAPI\Client\Model\PaymentProcessorTokenRequest(); // \OpenAPI\Client\Model\PaymentProcessorTokenRequest | account information

try {
    $result = $apiInstance->generatePaymentProcessorToken($token_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountTokenApi->generatePaymentProcessorToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **token_request** | [**\OpenAPI\Client\Model\PaymentProcessorTokenRequest**](../Model/PaymentProcessorTokenRequest.md)| account information | |

### Return type

[**\OpenAPI\Client\Model\PaymentProcessorTokenResponse**](../Model/PaymentProcessorTokenResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `revokePaymentProcessorToken()`

```php
revokePaymentProcessorToken($processor_token)
```

Delete Account Token

The delete account token service allows you to revoke a previously generated <code>processorToken</code>. It is recommended to use this service when you want to disallow further access to the user's financial account, for instance when a user removes their account from your application.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\AccountTokenApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$processor_token = 'processor_token_example'; // string | The token that you want to delete.

try {
    $apiInstance->revokePaymentProcessorToken($processor_token);
} catch (Exception $e) {
    echo 'Exception when calling AccountTokenApi->revokePaymentProcessorToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **processor_token** | **string**| The token that you want to delete. | |

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
