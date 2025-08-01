# OpenAPI\Client\HoldingsApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**addHolding()**](HoldingsApi.md#addHolding) | **POST** /holdings | Add Holding |
| [**getAssetClassificationList()**](HoldingsApi.md#getAssetClassificationList) | **GET** /holdings/assetClassificationList | Get Asset Classification List |
| [**getHoldingTypeList()**](HoldingsApi.md#getHoldingTypeList) | **GET** /holdings/holdingTypeList | Get Holding Type List |
| [**getHoldings()**](HoldingsApi.md#getHoldings) | **GET** /holdings | Get Holdings |
| [**getSecurities()**](HoldingsApi.md#getSecurities) | **GET** /holdings/securities | Get Security Details |


## `addHolding()`

```php
addHolding($add_holding_request): \OpenAPI\Client\Model\HoldingIdListResponse
```

Add Holding

The add manual holding service is used to add manual holdings. The response of add manual holding service includes the Yodlee generated holding id.<br><br>Add manual holding can only be added to a manual account of investment type container only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\HoldingsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$add_holding_request = new \OpenAPI\Client\Model\HoldingRequest(); // \OpenAPI\Client\Model\HoldingRequest | addHoldingRequest

try {
    $result = $apiInstance->addHolding($add_holding_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HoldingsApi->addHolding: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **add_holding_request** | [**\OpenAPI\Client\Model\HoldingRequest**](../Model/HoldingRequest.md)| addHoldingRequest | |

### Return type

[**\OpenAPI\Client\Model\HoldingIdListResponse**](../Model/HoldingIdListResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAssetClassificationList()`

```php
getAssetClassificationList(): \OpenAPI\Client\Model\HoldingAssetClassificationListResponse
```

Get Asset Classification List

The get asset classifications list service is used to get the supported asset classifications. <br>The response includes different classification types like assetClass, country, sector, style, etc. and the values corresponding to each type.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\HoldingsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getAssetClassificationList();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HoldingsApi->getAssetClassificationList: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\OpenAPI\Client\Model\HoldingAssetClassificationListResponse**](../Model/HoldingAssetClassificationListResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getHoldingTypeList()`

```php
getHoldingTypeList(): \OpenAPI\Client\Model\HoldingTypeListResponse
```

Get Holding Type List

The get holding types list service is used to get the supported holding types.<br>The response includes different holding types such as future, moneyMarketFund, stock, etc. and it returns the supported holding types <br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\HoldingsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getHoldingTypeList();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HoldingsApi->getHoldingTypeList: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\OpenAPI\Client\Model\HoldingTypeListResponse**](../Model/HoldingTypeListResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getHoldings()`

```php
getHoldings($account_id, $asset_classification_classification_type, $classification_value, $include, $provider_account_id): \OpenAPI\Client\Model\HoldingResponse
```

Get Holdings

The get holdings service is used to get the list of holdings of a user.<br>Supported holding types can be employeeStockOption, moneyMarketFund, bond, etc. and is obtained using get holding type list service. <br>Asset classifications for the holdings need to be requested through the \"include\" parameter.<br>Asset classification information for holdings are not available by default, as it is a premium feature.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\HoldingsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_id = 'account_id_example'; // string | Comma separated accountId
$asset_classification_classification_type = 'asset_classification_classification_type_example'; // string | e.g. Country, Sector, etc.
$classification_value = 'classification_value_example'; // string | e.g. US
$include = 'include_example'; // string | assetClassification
$provider_account_id = 'provider_account_id_example'; // string | providerAccountId

try {
    $result = $apiInstance->getHoldings($account_id, $asset_classification_classification_type, $classification_value, $include, $provider_account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HoldingsApi->getHoldings: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**| Comma separated accountId | [optional] |
| **asset_classification_classification_type** | **string**| e.g. Country, Sector, etc. | [optional] |
| **classification_value** | **string**| e.g. US | [optional] |
| **include** | **string**| assetClassification | [optional] |
| **provider_account_id** | **string**| providerAccountId | [optional] |

### Return type

[**\OpenAPI\Client\Model\HoldingResponse**](../Model/HoldingResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getSecurities()`

```php
getSecurities($holding_id): \OpenAPI\Client\Model\HoldingSecuritiesResponse
```

Get Security Details

The get security details service is used to get all the security information for the holdings<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\HoldingsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$holding_id = 'holding_id_example'; // string | Comma separated holdingId

try {
    $result = $apiInstance->getSecurities($holding_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HoldingsApi->getSecurities: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **holding_id** | **string**| Comma separated holdingId | [optional] |

### Return type

[**\OpenAPI\Client\Model\HoldingSecuritiesResponse**](../Model/HoldingSecuritiesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
