# OpenAPI\Client\TransactionsApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createOrRunTransactionCategorizationRules()**](TransactionsApi.md#createOrRunTransactionCategorizationRules) | **POST** /transactions/categories/rules | Create or Run Transaction Categorization Rule |
| [**createTransactionCategory()**](TransactionsApi.md#createTransactionCategory) | **POST** /transactions/categories | Create Category |
| [**deleteTransactionCategorizationRule()**](TransactionsApi.md#deleteTransactionCategorizationRule) | **DELETE** /transactions/categories/rules/{ruleId} | Delete Transaction Categorization Rule |
| [**deleteTransactionCategory()**](TransactionsApi.md#deleteTransactionCategory) | **DELETE** /transactions/categories/{categoryId} | Delete Category |
| [**getTransactionCategories()**](TransactionsApi.md#getTransactionCategories) | **GET** /transactions/categories | Get Transaction Category List |
| [**getTransactionCategorizationRules()**](TransactionsApi.md#getTransactionCategorizationRules) | **GET** /transactions/categories/txnRules | Get Transaction Categorization Rules |
| [**getTransactionCategorizationRulesDeprecated()**](TransactionsApi.md#getTransactionCategorizationRulesDeprecated) | **GET** /transactions/categories/rules | Get Transaction Categorization Rules |
| [**getTransactions()**](TransactionsApi.md#getTransactions) | **GET** /transactions | Get Transactions |
| [**getTransactionsCount()**](TransactionsApi.md#getTransactionsCount) | **GET** /transactions/count | Get Transactions Count |
| [**runTransactionCategorizationRule()**](TransactionsApi.md#runTransactionCategorizationRule) | **POST** /transactions/categories/rules/{ruleId} | Run Transaction Categorization Rule |
| [**updateTransaction()**](TransactionsApi.md#updateTransaction) | **PUT** /transactions | Update Transaction for Transaction Source ID |
| [**updateTransaction1()**](TransactionsApi.md#updateTransaction1) | **PUT** /transactions/{transactionId} | Update Transaction |
| [**updateTransactionCategorizationRule()**](TransactionsApi.md#updateTransactionCategorizationRule) | **PUT** /transactions/categories/rules/{ruleId} | Update Transaction Categorization Rule |
| [**updateTransactionCategory()**](TransactionsApi.md#updateTransactionCategory) | **PUT** /transactions/categories | Update Category |


## `createOrRunTransactionCategorizationRules()`

```php
createOrRunTransactionCategorizationRules($action, $rule_param)
```

Create or Run Transaction Categorization Rule

The Create or Run Transaction Categorization Rule endpoint is used to: <br>Create transaction categorization rules for both system and user-defined categories.<br>Run all the transaction categorization rules to categorize transactions by calling the endpoint with action=run as the query parameter. <br><br>The input body parameters to create transaction categorization rules follow:<br>     categoryId - This field is mandatory and numeric<br>     priority - This field is optional and numeric. Priority decides the order in which the rule gets applied on transactions.<br>     ruleClause - This field is mandatory and should contain at least one rule<br>     field - The value can be description or amount<br><br>       If the field value is description then,<br>         1. operation - value can be stringEquals or stringContains<br>         2. value - value should be min of 3 and max of 50 characters<br><br>       If the field value is amount then, <br>         1. operation - value can be numberEquals, numberLessThan, numberLessThanEquals, numberGreaterThan or numberGreaterThanEquals<br>         2. value - min value 0 and a max value of 99999999999.99 is allowed<br>The HTTP response code is 201 (Created Successfully).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$action = 'action_example'; // string | To run rules, pass action=run. Only value run is supported
$rule_param = 'rule_param_example'; // string | rules(JSON format) to categorize the transactions

try {
    $apiInstance->createOrRunTransactionCategorizationRules($action, $rule_param);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->createOrRunTransactionCategorizationRules: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **action** | **string**| To run rules, pass action&#x3D;run. Only value run is supported | [optional] |
| **rule_param** | **string**| rules(JSON format) to categorize the transactions | [optional] |

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

## `createTransactionCategory()`

```php
createTransactionCategory($transaction_category_request)
```

Create Category

The create transaction categories service is used to create user-defined categories for a system-defined category.<br>The parentCategoryId is the system-defined category id.This can be retrieved using get transaction categories service.<br>The categoryName can accept minimum of 1, maximum of 50 alphanumeric or special characters.<br>The HTTP response code is 201 (Created successfully).<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$transaction_category_request = new \OpenAPI\Client\Model\TransactionCategoryRequest(); // \OpenAPI\Client\Model\TransactionCategoryRequest | User Transaction Category in JSON format

try {
    $apiInstance->createTransactionCategory($transaction_category_request);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->createTransactionCategory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **transaction_category_request** | [**\OpenAPI\Client\Model\TransactionCategoryRequest**](../Model/TransactionCategoryRequest.md)| User Transaction Category in JSON format | |

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

## `deleteTransactionCategorizationRule()`

```php
deleteTransactionCategorizationRule($rule_id)
```

Delete Transaction Categorization Rule

The delete transaction categorization rule service is used to delete the given user-defined transaction categorization rule for both system-defined category as well as user-defined category.<br>This will delete all the corresponding rule clauses associated with the rule.<br>The HTTP response code is 204 (Success without content).<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$rule_id = 56; // int | ruleId

try {
    $apiInstance->deleteTransactionCategorizationRule($rule_id);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->deleteTransactionCategorizationRule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **rule_id** | **int**| ruleId | |

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

## `deleteTransactionCategory()`

```php
deleteTransactionCategory($category_id)
```

Delete Category

The delete transaction categories service is used to delete the given user-defined category.<br>The HTTP response code is 204 (Success without content).<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$category_id = 56; // int | categoryId

try {
    $apiInstance->deleteTransactionCategory($category_id);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->deleteTransactionCategory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **category_id** | **int**| categoryId | |

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

## `getTransactionCategories()`

```php
getTransactionCategories(): \OpenAPI\Client\Model\TransactionCategoryResponse
```

Get Transaction Category List

The categories service returns the list of available transaction categories.<br>High level category is returned in the response only if it is opted by the customer.<br>When invoked by passing the cobrand session or admin access token, this service returns the supported transaction categories at the cobrand level. <br>When invoked by passing the cobrand session and the user session or user access token, this service returns the transaction categories <br>along with user-defined categories.<br>Double quotes in the user-defined category name will be prefixed by backslashes (&#92;) in the response, <br>e.g. Toys \"R\" Us.<br/>Source and id are the primary attributes of the category entity.<br><br><b>Note:</b><li>This service supports the localization feature and accepts locale as a header parameter.</li>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getTransactionCategories();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->getTransactionCategories: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\OpenAPI\Client\Model\TransactionCategoryResponse**](../Model/TransactionCategoryResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTransactionCategorizationRules()`

```php
getTransactionCategorizationRules(): \OpenAPI\Client\Model\TransactionCategorizationRuleResponse
```

Get Transaction Categorization Rules

The get transaction categorization rule service is used to get all the categorization rules.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getTransactionCategorizationRules();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->getTransactionCategorizationRules: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\OpenAPI\Client\Model\TransactionCategorizationRuleResponse**](../Model/TransactionCategorizationRuleResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTransactionCategorizationRulesDeprecated()`

```php
getTransactionCategorizationRulesDeprecated(): \OpenAPI\Client\Model\TransactionCategorizationRule[]
```

Get Transaction Categorization Rules

The get transaction categorization rule service is used to get all the categorization rules.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getTransactionCategorizationRulesDeprecated();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->getTransactionCategorizationRulesDeprecated: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\OpenAPI\Client\Model\TransactionCategorizationRule[]**](../Model/TransactionCategorizationRule.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTransactions()`

```php
getTransactions($account_id, $base_type, $category_id, $category_type, $container, $convert_to_currency, $detail_category_id, $from_date, $high_level_category_id, $keyword, $skip, $to_date, $top, $type): \OpenAPI\Client\Model\TransactionResponse
```

Get Transactions

The Transaction service is used to get a list of transactions for a user.<br>By default, this service returns the last 30 days of transactions from today's date.<br>API will only return up to 2 years of transaction history. If the difference between fromDate and toDate is more than 2 years, API will return only last 2 years from the toDate.<br>The keyword parameter performs a contains search on the original, consumer, and simple description attributes, replace the special characters #, &, and + with percent-encoding values %23, %26, and %2B respectively. Eg: for -Debit# , pass the input as -Debit%23.<br>Values for categoryId parameter can be fetched from get transaction category list service.<br> The categoryId is used to filter transactions based on system-defined category as well as user-defined category.<br>User-defined categoryIds should be provided in the filter with the prefix ''U''. E.g. U10002<br>The skip and top parameters are used for pagination. In the skip and top parameters pass the number of records to be skipped and retrieved, respectively. The response header provides the links to retrieve the next and previous set of transactions.<br>Double quotes in the merchant name will be prefixed by backslashes (&#92;) in the response, e.g. Toys \"R\" Us. <br>sourceId is a unique ID that the provider site has assigned to the transaction. The source ID is only available for the pre-populated accounts. Pre-populated accounts are the accounts that the FI customers shares with Yodlee, so that the user does not have to add or aggregate those accounts.<br><br><b>Note</b><ul><li><a href=\"https://developer.yodlee.com/resources/yodlee/transaction-data-enrichment/docs/overview\">Transaction Data Enrichment</a> is made available for bank and card accounts. The address field in the response is available only when the Transaction Data Enrichment key is turned ON.</li><li>The pagination feature is available by default. If no values are passed in the skip and top parameters, the API will only return the first 500 transactions.</li><li>This service supports the localization feature and accepts locale as a header parameter.</li></ul>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_id = 'account_id_example'; // string | Comma separated accountIds
$base_type = 'base_type_example'; // string | DEBIT/CREDIT
$category_id = 'category_id_example'; // string | Comma separated categoryIds
$category_type = 'category_type_example'; // string | Transaction Category Type(LOAN, UNCATEGORIZE, INCOME, TRANSFER, EXPENSE or DEFERRED_COMPENSATION)
$container = 'container_example'; // string | bank/creditCard/investment/insurance/loan
$convert_to_currency = 'convert_to_currency_example'; // string | On-demand currency conversion parameter
$detail_category_id = 'detail_category_id_example'; // string | Comma separated detailCategoryIds
$from_date = 'from_date_example'; // string | Transaction from date(YYYY-MM-DD)
$high_level_category_id = 'high_level_category_id_example'; // string | Comma separated highLevelCategoryIds
$keyword = 'keyword_example'; // string | Transaction search text
$skip = 56; // int | skip (Min 0)
$to_date = 'to_date_example'; // string | Transaction end date (YYYY-MM-DD)
$top = 56; // int | top (Max 500)
$type = 'type_example'; // string | Transaction Type(SELL,SWEEP, etc.) for bank/creditCard/investment

try {
    $result = $apiInstance->getTransactions($account_id, $base_type, $category_id, $category_type, $container, $convert_to_currency, $detail_category_id, $from_date, $high_level_category_id, $keyword, $skip, $to_date, $top, $type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->getTransactions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**| Comma separated accountIds | [optional] |
| **base_type** | **string**| DEBIT/CREDIT | [optional] |
| **category_id** | **string**| Comma separated categoryIds | [optional] |
| **category_type** | **string**| Transaction Category Type(LOAN, UNCATEGORIZE, INCOME, TRANSFER, EXPENSE or DEFERRED_COMPENSATION) | [optional] |
| **container** | **string**| bank/creditCard/investment/insurance/loan | [optional] |
| **convert_to_currency** | **string**| On-demand currency conversion parameter | [optional] |
| **detail_category_id** | **string**| Comma separated detailCategoryIds | [optional] |
| **from_date** | **string**| Transaction from date(YYYY-MM-DD) | [optional] |
| **high_level_category_id** | **string**| Comma separated highLevelCategoryIds | [optional] |
| **keyword** | **string**| Transaction search text | [optional] |
| **skip** | **int**| skip (Min 0) | [optional] |
| **to_date** | **string**| Transaction end date (YYYY-MM-DD) | [optional] |
| **top** | **int**| top (Max 500) | [optional] |
| **type** | **string**| Transaction Type(SELL,SWEEP, etc.) for bank/creditCard/investment | [optional] |

### Return type

[**\OpenAPI\Client\Model\TransactionResponse**](../Model/TransactionResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTransactionsCount()`

```php
getTransactionsCount($account_id, $base_type, $category_id, $category_type, $container, $detail_category_id, $from_date, $high_level_category_id, $keyword, $to_date, $type): \OpenAPI\Client\Model\TransactionCountResponse
```

Get Transactions Count

The count service provides the total number of transactions for a specific user depending on the input parameters passed.<br>If you are implementing pagination for transactions, call this endpoint before calling GET /transactions to know the number of transactions that are returned for the input parameters passed.<br>The functionality of the input parameters remains the same as that of the GET /transactions endpoint.<br>If the difference between fromDate and toDate is more than 2 years, API will return the count of last 2 years from the toDate.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_id = 'account_id_example'; // string | Comma separated accountIds
$base_type = 'base_type_example'; // string | DEBIT/CREDIT
$category_id = 'category_id_example'; // string | Comma separated categoryIds
$category_type = 'category_type_example'; // string | Transaction Category Type(LOAN, UNCATEGORIZE, INCOME, TRANSFER, EXPENSE or DEFERRED_COMPENSATION)
$container = 'container_example'; // string | bank/creditCard/investment/insurance/loan
$detail_category_id = 'detail_category_id_example'; // string | Comma separated detailCategoryIds
$from_date = 'from_date_example'; // string | Transaction from date(YYYY-MM-DD)
$high_level_category_id = 'high_level_category_id_example'; // string | Comma separated highLevelCategoryIds
$keyword = 'keyword_example'; // string | Transaction search text
$to_date = 'to_date_example'; // string | Transaction end date (YYYY-MM-DD)
$type = 'type_example'; // string | Transaction Type(SELL,SWEEP, etc.)

try {
    $result = $apiInstance->getTransactionsCount($account_id, $base_type, $category_id, $category_type, $container, $detail_category_id, $from_date, $high_level_category_id, $keyword, $to_date, $type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->getTransactionsCount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**| Comma separated accountIds | [optional] |
| **base_type** | **string**| DEBIT/CREDIT | [optional] |
| **category_id** | **string**| Comma separated categoryIds | [optional] |
| **category_type** | **string**| Transaction Category Type(LOAN, UNCATEGORIZE, INCOME, TRANSFER, EXPENSE or DEFERRED_COMPENSATION) | [optional] |
| **container** | **string**| bank/creditCard/investment/insurance/loan | [optional] |
| **detail_category_id** | **string**| Comma separated detailCategoryIds | [optional] |
| **from_date** | **string**| Transaction from date(YYYY-MM-DD) | [optional] |
| **high_level_category_id** | **string**| Comma separated highLevelCategoryIds | [optional] |
| **keyword** | **string**| Transaction search text | [optional] |
| **to_date** | **string**| Transaction end date (YYYY-MM-DD) | [optional] |
| **type** | **string**| Transaction Type(SELL,SWEEP, etc.) | [optional] |

### Return type

[**\OpenAPI\Client\Model\TransactionCountResponse**](../Model/TransactionCountResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `runTransactionCategorizationRule()`

```php
runTransactionCategorizationRule($action, $rule_id)
```

Run Transaction Categorization Rule

The run transaction categorization rule service is used to run a rule on transactions, to categorize the transactions.<br>The HTTP response code is 204 (Success with no content).<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$action = 'run'; // string
$rule_id = 56; // int | Unique id of the categorization rule

try {
    $apiInstance->runTransactionCategorizationRule($action, $rule_id);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->runTransactionCategorizationRule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **action** | **string**|  | [default to &#39;run&#39;] |
| **rule_id** | **int**| Unique id of the categorization rule | |

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

## `updateTransaction()`

```php
updateTransaction($transaction_request)
```

Update Transaction for Transaction Source ID

Update the category, consumer description, memo, isPhysical, merchantType, and detailCategory for a transaction by filtering it using the Transaction Source ID.<br>The HTTP response code is 204 (Success without content).<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$transaction_request = new \OpenAPI\Client\Model\TransactionRequest(); // \OpenAPI\Client\Model\TransactionRequest | transactionRequest

try {
    $apiInstance->updateTransaction($transaction_request);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->updateTransaction: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **transaction_request** | [**\OpenAPI\Client\Model\TransactionRequest**](../Model/TransactionRequest.md)| transactionRequest | |

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

## `updateTransaction1()`

```php
updateTransaction1($transaction_id, $transaction_request)
```

Update Transaction

The update transaction service is used to update the category,consumer description, memo, isPhysical, merchantType, detailCategory for a transaction.<br>The HTTP response code is 204 (Success without content).<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$transaction_id = 56; // int | transactionId
$transaction_request = new \OpenAPI\Client\Model\TransactionRequest(); // \OpenAPI\Client\Model\TransactionRequest | transactionRequest

try {
    $apiInstance->updateTransaction1($transaction_id, $transaction_request);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->updateTransaction1: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **transaction_id** | **int**| transactionId | |
| **transaction_request** | [**\OpenAPI\Client\Model\TransactionRequest**](../Model/TransactionRequest.md)| transactionRequest | |

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

## `updateTransactionCategorizationRule()`

```php
updateTransactionCategorizationRule($rule_id, $transaction_categories_rule_request)
```

Update Transaction Categorization Rule

The update transaction categorization rule service is used to update a categorization rule for both system-defined category as well as user-defined category.<br>ruleParam JSON input should be as explained in the create transaction categorization rule service.<br>The HTTP response code is 204 (Success without content).<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$rule_id = 56; // int | ruleId
$transaction_categories_rule_request = new \OpenAPI\Client\Model\TransactionCategorizationRuleRequest(); // \OpenAPI\Client\Model\TransactionCategorizationRuleRequest | transactionCategoriesRuleRequest

try {
    $apiInstance->updateTransactionCategorizationRule($rule_id, $transaction_categories_rule_request);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->updateTransactionCategorizationRule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **rule_id** | **int**| ruleId | |
| **transaction_categories_rule_request** | [**\OpenAPI\Client\Model\TransactionCategorizationRuleRequest**](../Model/TransactionCategorizationRuleRequest.md)| transactionCategoriesRuleRequest | |

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

## `updateTransactionCategory()`

```php
updateTransactionCategory($update_category_request)
```

Update Category

The update transaction categories service is used to update the transaction category name<br>for a high level category, a system-defined category and a user-defined category.<br>The renamed category can be set back to the original name by passing an empty string for categoryName.<br>The categoryName can accept minimum of 1, maximum of 50 alphanumeric or special characters.<br>The HTTP response code is 204 (Success without content).<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$update_category_request = new \OpenAPI\Client\Model\UpdateCategoryRequest(); // \OpenAPI\Client\Model\UpdateCategoryRequest | updateCategoryRequest

try {
    $apiInstance->updateTransactionCategory($update_category_request);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->updateTransactionCategory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **update_category_request** | [**\OpenAPI\Client\Model\UpdateCategoryRequest**](../Model/UpdateCategoryRequest.md)| updateCategoryRequest | |

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
