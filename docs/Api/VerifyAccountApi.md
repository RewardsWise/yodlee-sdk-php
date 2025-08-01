# OpenAPI\Client\VerifyAccountApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**initiateAccountVerification()**](VerifyAccountApi.md#initiateAccountVerification) | **POST** /verifyAccount/{providerAccountId} | Verify Accounts Using Transactions |


## `initiateAccountVerification()`

```php
initiateAccountVerification($provider_account_id, $verification_param): \OpenAPI\Client\Model\VerifyAccountResponse
```

Verify Accounts Using Transactions

The verify account service is used to verify the account's ownership by  matching the transaction details with the accounts aggregated for the user.<br><ul><li>If a match is identified, the service returns details of all the accounts along with the matched transaction's details.<li>If no transaction match is found, an empty response will be returned.<li>A maximum of 5 transactionCriteria can be passed in a request.<li>The baseType, date, and amount parameters should mandatorily be passed.<li>The optional dateVariance parameter cannot be more than 7 days. For example, +7, -4, or +/-2.<li>Pass the container or accountId parameters for better performance.<li>This service supports the localization feature and accepts locale as a header parameter.</li></ul>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\VerifyAccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$provider_account_id = 'provider_account_id_example'; // string | providerAccountId
$verification_param = new \OpenAPI\Client\Model\VerifyAccountRequest(); // \OpenAPI\Client\Model\VerifyAccountRequest | verificationParam

try {
    $result = $apiInstance->initiateAccountVerification($provider_account_id, $verification_param);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VerifyAccountApi->initiateAccountVerification: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **provider_account_id** | **string**| providerAccountId | |
| **verification_param** | [**\OpenAPI\Client\Model\VerifyAccountRequest**](../Model/VerifyAccountRequest.md)| verificationParam | |

### Return type

[**\OpenAPI\Client\Model\VerifyAccountResponse**](../Model/VerifyAccountResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
