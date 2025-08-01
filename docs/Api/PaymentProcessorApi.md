# RewardsWise\Yodlee\OpenAPI\Client\PaymentProcessorApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getVerifiedAccount()**](PaymentProcessorApi.md#getVerifiedAccount) | **GET** /partner/paymentProcessor/account | Get Account Details |
| [**getVerifiedAccountBalance()**](PaymentProcessorApi.md#getVerifiedAccountBalance) | **GET** /partner/paymentProcessor/account/balance | Get Account Balance |
| [**getVerifiedAccountHolder()**](PaymentProcessorApi.md#getVerifiedAccountHolder) | **GET** /partner/paymentProcessor/account/holder | Get Account Holder Details |


## `getVerifiedAccount()`

```php
getVerifiedAccount($processor_token): \RewardsWise\Yodlee\OpenAPI\Client\Model\PaymentAccountResponse
```

Get Account Details

The get account details service retrieves account information such as account name, type, status, balance, account number and transfer code (for example, routing number of the bank account in the US) of the verified account associated with the <code>processorToken</code>. The <code>lastUpdated</code> field indicates when the account information was last updated. We recommend using this service when looking for details related to the financial account, for instance, the full account number and bank transfer code for initiating a payment.<br><br><b>Note: </b>Remember to include the <code>Authorization</code> header.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\PaymentProcessorApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$processor_token = 'processor_token_example'; // string | Token shared by customer to access financial account information.

try {
    $result = $apiInstance->getVerifiedAccount($processor_token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PaymentProcessorApi->getVerifiedAccount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **processor_token** | **string**| Token shared by customer to access financial account information. | |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\PaymentAccountResponse**](../Model/PaymentAccountResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getVerifiedAccountBalance()`

```php
getVerifiedAccountBalance($processor_token): \RewardsWise\Yodlee\OpenAPI\Client\Model\PaymentAccountBalanceResponse
```

Get Account Balance

The get account balance service retrieves the account balance information of the verified account associated with the <code>processorToken</code>. The response returns additional account information including account names, type and status, along with the account balance information. <br>This service forces an update of the account balances. While other services also return the account balances, this service attempts to refresh the account balances in real-time rather than return a cached value. Refer to the <code>lastUpdated</code> field to determine when the account balances were refreshed. We recommend using this service when looking for the latest balance for the account.<br>While posting a debit against an account, it is generally advisable to check the available balance field to verify the availability of sufficient funds. This service returns both available and current balances: <ul><li><b>Available Balance</b> is the amount in the account that is available for spending. The value is aggregated from the FI. For checking accounts with overdrafts, the available balance amount may include the overdraft amount if the FI adds the overdraft balance to the available balance.</li><li><b>Current Balance</b> is the total amount of money in the account, aggregated from the FI.</li></ul><br><b>Note: </b>Remember to include the <code>Authorization</code> header.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\PaymentProcessorApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$processor_token = 'processor_token_example'; // string | Token shared by customer to access financial account information.

try {
    $result = $apiInstance->getVerifiedAccountBalance($processor_token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PaymentProcessorApi->getVerifiedAccountBalance: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **processor_token** | **string**| Token shared by customer to access financial account information. | |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\PaymentAccountBalanceResponse**](../Model/PaymentAccountBalanceResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getVerifiedAccountHolder()`

```php
getVerifiedAccountHolder($processor_token): \RewardsWise\Yodlee\OpenAPI\Client\Model\PaymentAccountHolderResponse
```

Get Account Holder Details

The get account holder details service retrieves the account holder information such as name, email, phone number, address, etc. of the verified financial account associated with the <code>processorToken</code>. The <code>lastUpdated</code> field indicates when the account information was last updated. We recommend using this service when looking for information related to the account holder(s), for instance, to confirm the account holder's name. <br><br><b>Note: </b>Remember to include the <code>Authorization</code> header.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\PaymentProcessorApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$processor_token = 'processor_token_example'; // string | Token shared by customer to access financial account information.

try {
    $result = $apiInstance->getVerifiedAccountHolder($processor_token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PaymentProcessorApi->getVerifiedAccountHolder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **processor_token** | **string**| Token shared by customer to access financial account information. | |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\PaymentAccountHolderResponse**](../Model/PaymentAccountHolderResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
