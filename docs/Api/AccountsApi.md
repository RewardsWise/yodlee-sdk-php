# OpenAPI\Client\AccountsApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createManualAccount()**](AccountsApi.md#createManualAccount) | **POST** /accounts | Add Manual Account |
| [**deleteAccount()**](AccountsApi.md#deleteAccount) | **DELETE** /accounts/{accountId} | Delete Account |
| [**evaluateAddress()**](AccountsApi.md#evaluateAddress) | **POST** /accounts/evaluateAddress | Evaluate Address |
| [**getAccount()**](AccountsApi.md#getAccount) | **GET** /accounts/{accountId} | Get Account Details |
| [**getAllAccounts()**](AccountsApi.md#getAllAccounts) | **GET** /accounts | Get Accounts |
| [**getAssociatedAccounts()**](AccountsApi.md#getAssociatedAccounts) | **GET** /accounts/associatedAccounts/{providerAccountId} | Associated Accounts |
| [**getHistoricalBalances()**](AccountsApi.md#getHistoricalBalances) | **GET** /accounts/historicalBalances | Get Historical Balances |
| [**getLatestBalances()**](AccountsApi.md#getLatestBalances) | **GET** /accounts/latestBalances | Get Latest Balances |
| [**migrateAccounts()**](AccountsApi.md#migrateAccounts) | **PUT** /accounts/migrateAccounts/{providerAccountId} | Migrate Accounts |
| [**updateAccount()**](AccountsApi.md#updateAccount) | **PUT** /accounts/{accountId} | Update Account |


## `createManualAccount()`

```php
createManualAccount($account_param): \OpenAPI\Client\Model\CreatedAccountResponse
```

Add Manual Account

The add account service is used to add manual accounts.<br>The response of add account service includes the account name , account number and Yodlee generated account id.<br>All manual accounts added will be included as part of networth calculation by default.<br>Add manual account support is available for bank, card, investment, insurance and loan container only.<br><br><b>Note:</b><ul> <li>A real estate account addition is only supported for SYSTEM and MANUAL valuation type.</li></ul>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_param = new \OpenAPI\Client\Model\CreateAccountRequest(); // \OpenAPI\Client\Model\CreateAccountRequest | accountParam

try {
    $result = $apiInstance->createManualAccount($account_param);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->createManualAccount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_param** | [**\OpenAPI\Client\Model\CreateAccountRequest**](../Model/CreateAccountRequest.md)| accountParam | |

### Return type

[**\OpenAPI\Client\Model\CreatedAccountResponse**](../Model/CreatedAccountResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteAccount()`

```php
deleteAccount($account_id)
```

Delete Account

The delete account service allows an account to be deleted.<br>This service does not return a response. The HTTP response code is 204 (Success with no content).<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_id = 56; // int | accountId

try {
    $apiInstance->deleteAccount($account_id);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->deleteAccount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **int**| accountId | |

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

## `evaluateAddress()`

```php
evaluateAddress($address_param): \OpenAPI\Client\Model\EvaluateAddressResponse
```

Evaluate Address

Use this service to validate the address before adding the real estate account.<br>If the address is valid, the service will return the complete address information.<br>The response will contain multiple addresses if the user-provided input matches with multiple entries in the vendor database.<br>In the case of multiple matches, the user can select the appropriate address from the list and then invoke the add account service with the complete address.<br><br><b>Note:</b> <ul><li>Yodlee recommends to use this service before adding the real estate account to avoid failures.</li></ul>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$address_param = new \OpenAPI\Client\Model\EvaluateAddressRequest(); // \OpenAPI\Client\Model\EvaluateAddressRequest | addressParam

try {
    $result = $apiInstance->evaluateAddress($address_param);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->evaluateAddress: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **address_param** | [**\OpenAPI\Client\Model\EvaluateAddressRequest**](../Model/EvaluateAddressRequest.md)| addressParam | |

### Return type

[**\OpenAPI\Client\Model\EvaluateAddressResponse**](../Model/EvaluateAddressResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAccount()`

```php
getAccount($account_id, $convert_to_currency, $include): \OpenAPI\Client\Model\AccountResponse
```

Get Account Details

The get account details service provides detailed information of an account.<br><br><b>Note:</b><li> fullAccountNumber is deprecated and is replaced with fullAccountNumberList in include parameter and response.</li>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_id = 56; // int | accountId
$convert_to_currency = 'convert_to_currency_example'; // string | On-demand currency conversion parameter
$include = 'include_example'; // string | profile, holder, fullAccountNumber, fullAccountNumberList, paymentProfile, autoRefresh<br><b>Note:</b>fullAccountNumber is deprecated and is replaced with fullAccountNumberList in include parameter and response.

try {
    $result = $apiInstance->getAccount($account_id, $convert_to_currency, $include);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->getAccount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **int**| accountId | |
| **convert_to_currency** | **string**| On-demand currency conversion parameter | [optional] |
| **include** | **string**| profile, holder, fullAccountNumber, fullAccountNumberList, paymentProfile, autoRefresh&lt;br&gt;&lt;b&gt;Note:&lt;/b&gt;fullAccountNumber is deprecated and is replaced with fullAccountNumberList in include parameter and response. | [optional] |

### Return type

[**\OpenAPI\Client\Model\AccountResponse**](../Model/AccountResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAllAccounts()`

```php
getAllAccounts($account_id, $container, $convert_to_currency, $include, $provider_account_id, $request_id, $status): \OpenAPI\Client\Model\AccountResponse
```

Get Accounts

The get accounts service provides information about accounts added by the user.<br>By default, this service returns information for active and to be closed accounts.<br>If requestId is provided, the accounts that are updated in the context of the requestId will be provided in the response.<br>Pagination is made available to the advisors to retrieve account data of all users assigned to them. The skip and top parameters are used for pagination. In the skip and top parameters pass the number of records to be skipped and retrieved, respectively. <br><br><b>Note:</b><br><ul><li>fullAccountNumber is deprecated and is replaced with fullAccountNumberList in include parameter and response.</li><li>fullAccountNumberList, PII (Personal Identifiable Information) and holder details are not available by default, as it is a premium feature that needs security approval. This will not be available for testing in Sandbox environment.</li></ul>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_id = 'account_id_example'; // string | Comma separated accountIds.
$container = 'container_example'; // string | bank/creditCard/investment/insurance/loan/reward/realEstate/otherAssets/otherLiabilities
$convert_to_currency = 'convert_to_currency_example'; // string | On-demand currency conversion parameter
$include = 'include_example'; // string | profile, holder, fullAccountNumber, fullAccountNumberList, paymentProfile, autoRefresh<br><b>Note:</b><br><li>fullAccountNumber is deprecated and is replaced with fullAccountNumberList in include parameter and response.</li><br><li>profile is deprecated, and to retrieve the profile information, call the GET /verification/holderProfile API instead.</li>
$provider_account_id = 'provider_account_id_example'; // string | Comma separated providerAccountIds.
$request_id = 'request_id_example'; // string | The unique identifier that returns contextual data
$status = 'status_example'; // string | ACTIVE,INACTIVE,TO_BE_CLOSED,CLOSED

try {
    $result = $apiInstance->getAllAccounts($account_id, $container, $convert_to_currency, $include, $provider_account_id, $request_id, $status);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->getAllAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**| Comma separated accountIds. | [optional] |
| **container** | **string**| bank/creditCard/investment/insurance/loan/reward/realEstate/otherAssets/otherLiabilities | [optional] |
| **convert_to_currency** | **string**| On-demand currency conversion parameter | [optional] |
| **include** | **string**| profile, holder, fullAccountNumber, fullAccountNumberList, paymentProfile, autoRefresh&lt;br&gt;&lt;b&gt;Note:&lt;/b&gt;&lt;br&gt;&lt;li&gt;fullAccountNumber is deprecated and is replaced with fullAccountNumberList in include parameter and response.&lt;/li&gt;&lt;br&gt;&lt;li&gt;profile is deprecated, and to retrieve the profile information, call the GET /verification/holderProfile API instead.&lt;/li&gt; | [optional] |
| **provider_account_id** | **string**| Comma separated providerAccountIds. | [optional] |
| **request_id** | **string**| The unique identifier that returns contextual data | [optional] |
| **status** | **string**| ACTIVE,INACTIVE,TO_BE_CLOSED,CLOSED | [optional] |

### Return type

[**\OpenAPI\Client\Model\AccountResponse**](../Model/AccountResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAssociatedAccounts()`

```php
getAssociatedAccounts($provider_account_id): \OpenAPI\Client\Model\AssociatedAccountsResponse
```

Associated Accounts

Yodlee classifies providers into credential-based aggregation and Open Banking (OB) providers.<br>This service is associated with the OB aggregation flow. As part of the OB solution, financial institutions may merge their subsidiaries and provide data as a single OB provider.<br>Before the OB solution, this data was aggregated with different provider IDs.<br>This service accepts the providerAccountId and returns all accounts of the associated providerAccounts that belong to the subsidiary of the financial institution.<br>This data should be displayed to the user to let them select the accounts that they wish to provide consent to share account data.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$provider_account_id = 56; // int | providerAccountId

try {
    $result = $apiInstance->getAssociatedAccounts($provider_account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->getAssociatedAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **provider_account_id** | **int**| providerAccountId | |

### Return type

[**\OpenAPI\Client\Model\AssociatedAccountsResponse**](../Model/AssociatedAccountsResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getHistoricalBalances()`

```php
getHistoricalBalances($account_id, $from_date, $include_cf, $interval, $skip, $to_date, $top): \OpenAPI\Client\Model\AccountHistoricalBalancesResponse
```

Get Historical Balances

The historical balances service is used to retrieve the historical balances for an account or a user.<br>Historical balances are daily (D), weekly (W), and monthly (M). <br>The interval input should be passed as D, W, and M to retrieve the desired historical balances. The default interval is daily (D). <br>When no account id is provided, historical balances of the accounts that are active, to be closed, and closed are provided in the response. <br>If the fromDate and toDate are not passed, the last 90 days of data will be provided. <br>The fromDate and toDate should be passed in the YYYY-MM-DD format. <br>The date field in the response denotes the date for which the balance is requested.<br>includeCF needs to be sent as true if the customer wants to return carried forward balances for a date when the data is not available. <br>asofDate field in the response denotes the date as of which the balance was updated for that account.<br>When there is no balance available for a requested date and if includeCF is sent as true, the previous date for which the balance is available is provided in the response. <br>When there is no previous balance available, no data will be sent. <br>By default, pagination is available for the historicalBalances entity in this API. The skip and top parameters are used for pagination. In the skip and top parameters, pass the number of records to be skipped and retrieved, respectively. The response header provides the links to retrieve the next and previous set of historical balances.<br> The API will only retrieve a maximum 500 records by default when values for skip and top parameters are not provided.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_id = 'account_id_example'; // string | accountId
$from_date = 'from_date_example'; // string | from date for balance retrieval (YYYY-MM-DD)
$include_cf = True; // bool | Consider carry forward logic for missing balances
$interval = 'interval_example'; // string | D-daily, W-weekly or M-monthly
$skip = 56; // int | skip (Min 0)
$to_date = 'to_date_example'; // string | toDate for balance retrieval (YYYY-MM-DD)
$top = 56; // int | top (Max 500)

try {
    $result = $apiInstance->getHistoricalBalances($account_id, $from_date, $include_cf, $interval, $skip, $to_date, $top);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->getHistoricalBalances: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**| accountId | [optional] |
| **from_date** | **string**| from date for balance retrieval (YYYY-MM-DD) | [optional] |
| **include_cf** | **bool**| Consider carry forward logic for missing balances | [optional] |
| **interval** | **string**| D-daily, W-weekly or M-monthly | [optional] |
| **skip** | **int**| skip (Min 0) | [optional] |
| **to_date** | **string**| toDate for balance retrieval (YYYY-MM-DD) | [optional] |
| **top** | **int**| top (Max 500) | [optional] |

### Return type

[**\OpenAPI\Client\Model\AccountHistoricalBalancesResponse**](../Model/AccountHistoricalBalancesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getLatestBalances()`

```php
getLatestBalances($account_id, $provider_account_id): \OpenAPI\Client\Model\AccountBalanceResponse
```

Get Latest Balances

The latest balances service provides the latest account balance by initiating a new balance refresh request

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_id = 'account_id_example'; // string | Comma separated accountIds.
$provider_account_id = 'provider_account_id_example'; // string | providerAccountId.

try {
    $result = $apiInstance->getLatestBalances($account_id, $provider_account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->getLatestBalances: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**| Comma separated accountIds. | |
| **provider_account_id** | **string**| providerAccountId. | |

### Return type

[**\OpenAPI\Client\Model\AccountBalanceResponse**](../Model/AccountBalanceResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `migrateAccounts()`

```php
migrateAccounts($provider_account_id): \OpenAPI\Client\Model\AccountMigrationResponse
```

Migrate Accounts

This service is associated with the open banking (OB) flow.<br>Before invoking this service, display all the associated accounts to the user by calling the GET /associatedAccounts API.<br>The migrate accounts API treats the user's consent acceptance to initiate account migration. Invoking this service indicates that the user has given the consent to access the associated account information from the financial institution.<br>If an existing provider supports bank, card, and loan accounts, and chose only to provide bank and card through OB APIs, a new providerAccountId for OB will be created.<br>The bank and card account information will be moved to the new providerAccountId. The loan account will be retained in the existing provider account.<br>This service returns the OB providerId and the OB providerAccountId. Note that, as part of this process, there is a possibility of one or more providerAccounts getting merged.<br>The update or delete actions will not be allowed for the providerAccounts involved in the migration process until the user completes the authorization on the OB provider.<br>The oauthMigrationEligibilityStatus attribute in the GET /accounts API response indicates the accounts included in the migration process.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$provider_account_id = 56; // int | providerAccountId

try {
    $result = $apiInstance->migrateAccounts($provider_account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->migrateAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **provider_account_id** | **int**| providerAccountId | |

### Return type

[**\OpenAPI\Client\Model\AccountMigrationResponse**](../Model/AccountMigrationResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateAccount()`

```php
updateAccount($account_id, $account_request)
```

Update Account

The update account service is used to update manual and aggregated accounts.<br>The HTTP response code is 204 (Success without content).<br>Update manual account support is available for bank, card, investment, insurance, loan, otherAssets, otherLiabilities and realEstate containers only.<br><br><b>Note:</b><li> A real estate account update is only supported for SYSTEM and MANUAL valuation type.</li> <li> A real estate account can be linked to a loan account by passing accountId of a loan account in linkedAccountIds .</li> <li> Attribute <b>isEbillEnrolled</b> is deprecated as it is applicable for bill accounts only.</li>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_id = 56; // int | accountId
$account_request = new \OpenAPI\Client\Model\UpdateAccountRequest(); // \OpenAPI\Client\Model\UpdateAccountRequest | accountRequest

try {
    $apiInstance->updateAccount($account_id, $account_request);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->updateAccount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **int**| accountId | |
| **account_request** | [**\OpenAPI\Client\Model\UpdateAccountRequest**](../Model/UpdateAccountRequest.md)| accountRequest | |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
