# RewardsWise\Yodlee\OpenAPI\Client\StatementsApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getStatements()**](StatementsApi.md#getStatements) | **GET** /statements | Get Statements |


## `getStatements()`

```php
getStatements($account_id, $container, $from_date, $is_latest, $status): \RewardsWise\Yodlee\OpenAPI\Client\Model\StatementResponse
```

Get Statements

The statements service is used to get the list of statement related information. <br>By default, all the latest statements of active and to be closed accounts are retrieved for the user. <br>Certain sites do not have both a statement date and a due date. When a fromDate is passed as an input, all the statements that have the due date on or after the passed date are retrieved. <br>For sites that do not have the due date, statements that have the statement date on or after the passed date are retrieved. <br>The default value of \"isLatest\" is true. To retrieve historical statements isLatest needs to be set to false.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\StatementsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_id = 'account_id_example'; // string | accountId
$container = 'container_example'; // string | creditCard/loan/insurance
$from_date = 'from_date_example'; // string | from date for statement retrieval (YYYY-MM-DD)
$is_latest = 'is_latest_example'; // string | isLatest (true/false)
$status = 'status_example'; // string | ACTIVE,TO_BE_CLOSED,CLOSED

try {
    $result = $apiInstance->getStatements($account_id, $container, $from_date, $is_latest, $status);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StatementsApi->getStatements: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**| accountId | [optional] |
| **container** | **string**| creditCard/loan/insurance | [optional] |
| **from_date** | **string**| from date for statement retrieval (YYYY-MM-DD) | [optional] |
| **is_latest** | **string**| isLatest (true/false) | [optional] |
| **status** | **string**| ACTIVE,TO_BE_CLOSED,CLOSED | [optional] |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\StatementResponse**](../Model/StatementResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
