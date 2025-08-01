# RewardsWise\Yodlee\OpenAPI\Client\DerivedApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getHoldingSummary()**](DerivedApi.md#getHoldingSummary) | **GET** /derived/holdingSummary | Get Holding Summary |
| [**getNetworth()**](DerivedApi.md#getNetworth) | **GET** /derived/networth | Get Networth Summary |
| [**getTransactionSummary()**](DerivedApi.md#getTransactionSummary) | **GET** /derived/transactionSummary | Get Transaction Summary |


## `getHoldingSummary()`

```php
getHoldingSummary($account_ids, $classification_type, $include): \RewardsWise\Yodlee\OpenAPI\Client\Model\DerivedHoldingSummaryResponse
```

Get Holding Summary

The get holding summary service is used to get the summary of asset classifications for the user.<br>By default, accounts with status as ACTIVE and TO BE CLOSED will be considered.<br>If the include parameter value is passed as details then a summary with holdings and account information is returned.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\DerivedApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_ids = 'account_ids_example'; // string | Comma separated accountIds
$classification_type = 'classification_type_example'; // string | e.g. Country, Sector, etc.
$include = 'include_example'; // string | details

try {
    $result = $apiInstance->getHoldingSummary($account_ids, $classification_type, $include);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DerivedApi->getHoldingSummary: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_ids** | **string**| Comma separated accountIds | [optional] |
| **classification_type** | **string**| e.g. Country, Sector, etc. | [optional] |
| **include** | **string**| details | [optional] |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\DerivedHoldingSummaryResponse**](../Model/DerivedHoldingSummaryResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getNetworth()`

```php
getNetworth($account_ids, $container, $from_date, $include, $interval, $skip, $to_date, $top): \RewardsWise\Yodlee\OpenAPI\Client\Model\DerivedNetworthResponse
```

Get Networth Summary

The get networth service is used to get the networth for the user.<br>If the include parameter value is passed as details then networth with historical balances is returned. <br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\DerivedApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_ids = 'account_ids_example'; // string | comma separated accountIds
$container = 'container_example'; // string | bank/creditCard/investment/insurance/loan/realEstate/otherAssets/otherLiabilities
$from_date = 'from_date_example'; // string | from date for balance retrieval (YYYY-MM-DD)
$include = 'include_example'; // string | details
$interval = 'interval_example'; // string | D-daily, W-weekly or M-monthly
$skip = 56; // int | skip (Min 0)
$to_date = 'to_date_example'; // string | toDate for balance retrieval (YYYY-MM-DD)
$top = 56; // int | top (Max 500)

try {
    $result = $apiInstance->getNetworth($account_ids, $container, $from_date, $include, $interval, $skip, $to_date, $top);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DerivedApi->getNetworth: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_ids** | **string**| comma separated accountIds | [optional] |
| **container** | **string**| bank/creditCard/investment/insurance/loan/realEstate/otherAssets/otherLiabilities | [optional] |
| **from_date** | **string**| from date for balance retrieval (YYYY-MM-DD) | [optional] |
| **include** | **string**| details | [optional] |
| **interval** | **string**| D-daily, W-weekly or M-monthly | [optional] |
| **skip** | **int**| skip (Min 0) | [optional] |
| **to_date** | **string**| toDate for balance retrieval (YYYY-MM-DD) | [optional] |
| **top** | **int**| top (Max 500) | [optional] |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\DerivedNetworthResponse**](../Model/DerivedNetworthResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTransactionSummary()`

```php
getTransactionSummary($group_by, $account_id, $category_id, $category_type, $from_date, $include, $include_user_category, $interval, $to_date): \RewardsWise\Yodlee\OpenAPI\Client\Model\DerivedTransactionSummaryResponse
```

Get Transaction Summary

The transaction summary service provides the summary values of transactions for the given date range by category type, high-level categories, or system-defined categories.<br><br>Yodlee has the transaction data stored for a day, month, year and week per category as per the availability of user's data. If the include parameter value is passed as details, then summary details will be returned depending on the interval passed-monthly is the default.<br><br><b>Notes:</b><ol> <li> Details can be requested for only one system-defined category<li>Passing categoryType is mandatory except when the groupBy value is CATEGORY_TYPE<li>Dates will not be respected for monthly, yearly, and weekly details<li>When monthly details are requested, only the fromDate and toDate month will be respected<li>When yearly details are requested, only the fromDate and toDate year will be respected<li>For weekly data points, details will be provided for every Sunday date available within the fromDate and toDate<li>This service supports the localization feature and accepts locale as a header parameter</li></ol>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\DerivedApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$group_by = 'group_by_example'; // string | CATEGORY_TYPE, HIGH_LEVEL_CATEGORY or CATEGORY
$account_id = 'account_id_example'; // string | comma separated account Ids
$category_id = 'category_id_example'; // string | comma separated categoryIds
$category_type = 'category_type_example'; // string | LOAN, INCOME, EXPENSE, TRANSFER, UNCATEGORIZE or DEFERRED_COMPENSATION
$from_date = 'from_date_example'; // string | YYYY-MM-DD format
$include = 'include_example'; // string | details
$include_user_category = True; // bool | TRUE/FALSE
$interval = 'interval_example'; // string | D-daily, W-weekly, M-mothly or Y-yearly
$to_date = 'to_date_example'; // string | YYYY-MM-DD format

try {
    $result = $apiInstance->getTransactionSummary($group_by, $account_id, $category_id, $category_type, $from_date, $include, $include_user_category, $interval, $to_date);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DerivedApi->getTransactionSummary: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **group_by** | **string**| CATEGORY_TYPE, HIGH_LEVEL_CATEGORY or CATEGORY | |
| **account_id** | **string**| comma separated account Ids | [optional] |
| **category_id** | **string**| comma separated categoryIds | [optional] |
| **category_type** | **string**| LOAN, INCOME, EXPENSE, TRANSFER, UNCATEGORIZE or DEFERRED_COMPENSATION | [optional] |
| **from_date** | **string**| YYYY-MM-DD format | [optional] |
| **include** | **string**| details | [optional] |
| **include_user_category** | **bool**| TRUE/FALSE | [optional] |
| **interval** | **string**| D-daily, W-weekly, M-mothly or Y-yearly | [optional] |
| **to_date** | **string**| YYYY-MM-DD format | [optional] |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\DerivedTransactionSummaryResponse**](../Model/DerivedTransactionSummaryResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
