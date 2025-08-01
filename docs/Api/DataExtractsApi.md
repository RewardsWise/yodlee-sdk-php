# RewardsWise\Yodlee\OpenAPI\Client\DataExtractsApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getDataExtractsEvents()**](DataExtractsApi.md#getDataExtractsEvents) | **GET** /dataExtracts/events | Get Events |
| [**getDataExtractsUserData()**](DataExtractsApi.md#getDataExtractsUserData) | **GET** /dataExtracts/userData | Get userData |


## `getDataExtractsEvents()`

```php
getDataExtractsEvents($event_name, $from_date, $to_date): \RewardsWise\Yodlee\OpenAPI\Client\Model\DataExtractsEventResponse
```

Get Events

The get extracts events service is used to learn about occurrences of data extract related events. This service currently supports only the DATA_UPDATES event.<br>Passing the event name as DATA_UPDATES provides information about users for whom data has been modified in the system for the specified time range. To learn more, please refer to the <a href=\"https://developer.yodlee.com/resources/yodlee/data-extracts/docs/overview\">Data Extracts</a> page.<br>You can retrieve data in increments of no more than 60 minutes over the period of the last 7 days from today's date.<br>This service is only invoked with either admin access token or a cobrand session.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\DataExtractsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$event_name = 'event_name_example'; // string | Event Name
$from_date = 'from_date_example'; // string | From DateTime (YYYY-MM-DDThh:mm:ssZ)
$to_date = 'to_date_example'; // string | To DateTime (YYYY-MM-DDThh:mm:ssZ)

try {
    $result = $apiInstance->getDataExtractsEvents($event_name, $from_date, $to_date);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DataExtractsApi->getDataExtractsEvents: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **event_name** | **string**| Event Name | |
| **from_date** | **string**| From DateTime (YYYY-MM-DDThh:mm:ssZ) | |
| **to_date** | **string**| To DateTime (YYYY-MM-DDThh:mm:ssZ) | |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\DataExtractsEventResponse**](../Model/DataExtractsEventResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getDataExtractsUserData()`

```php
getDataExtractsUserData($from_date, $login_name, $to_date): \RewardsWise\Yodlee\OpenAPI\Client\Model\DataExtractsUserDataResponse
```

Get userData

The get user data service is used to get a user's modified data for a particular period of time for accounts, transactions, holdings, and provider account information.<br>The time difference between fromDate and toDate fields cannot be more than 60 minutes.<br>By default, pagination is available for the transaction entity in this API. In the first response, the API will retrieve 500 transactions along with other data. The response header will provide a link to retrieve the next set of transactions.<br>In the response body of the first API response, totalTransactionsCount indicates the total number of transactions the API will retrieve for the user.<br>This service is only invoked with either admin access token or a cobrand session.<br/>Refer to <a href=\"https://developer.yodlee.com/resources/yodlee/data-extracts/docs/overview\">dataExtracts</a> page for more information.<br><br><b>Note:</b><li>This service supports the localization feature and accepts locale as a header parameter.</li>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\DataExtractsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$from_date = 'from_date_example'; // string | From DateTime (YYYY-MM-DDThh:mm:ssZ)
$login_name = 'login_name_example'; // string | Login Name
$to_date = 'to_date_example'; // string | To DateTime (YYYY-MM-DDThh:mm:ssZ)

try {
    $result = $apiInstance->getDataExtractsUserData($from_date, $login_name, $to_date);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DataExtractsApi->getDataExtractsUserData: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **from_date** | **string**| From DateTime (YYYY-MM-DDThh:mm:ssZ) | |
| **login_name** | **string**| Login Name | |
| **to_date** | **string**| To DateTime (YYYY-MM-DDThh:mm:ssZ) | |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\DataExtractsUserDataResponse**](../Model/DataExtractsUserDataResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
