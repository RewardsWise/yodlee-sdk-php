# RewardsWise\Yodlee\OpenAPI\Client\UserDocumentsApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteuserdocuments()**](UserDocumentsApi.md#deleteuserdocuments) | **DELETE** /documents | Delete User Documents |
| [**getuserdocuments()**](UserDocumentsApi.md#getuserdocuments) | **POST** /documents/search | Get User Documents |


## `deleteuserdocuments()`

```php
deleteuserdocuments($delete_documents_request)
```

Delete User Documents

The Delete User Documents service allows the consumer to delete the PDF documents uploaded by user through FastLink 4 flow.<br>The deleted documents will not be returned in the Get User Documents API.<br>The HTTP response code is 204 (success without content).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\UserDocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$delete_documents_request = new \RewardsWise\Yodlee\OpenAPI\Client\Model\DeleteDocumentsRequest(); // \RewardsWise\Yodlee\OpenAPI\Client\Model\DeleteDocumentsRequest | deleteDocumentsRequest

try {
    $apiInstance->deleteuserdocuments($delete_documents_request);
} catch (Exception $e) {
    echo 'Exception when calling UserDocumentsApi->deleteuserdocuments: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **delete_documents_request** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\DeleteDocumentsRequest**](../Model/DeleteDocumentsRequest.md)| deleteDocumentsRequest | |

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

## `getuserdocuments()`

```php
getuserdocuments($get_documents_request): \RewardsWise\Yodlee\OpenAPI\Client\Model\GetDocumentsResponse
```

Get User Documents

The Get User Documents service will allow customers to search or retrieve metadata related to PDF documents uploaded by user through the FastLink 4 flow.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\UserDocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$get_documents_request = new \RewardsWise\Yodlee\OpenAPI\Client\Model\GetDocumentsRequest(); // \RewardsWise\Yodlee\OpenAPI\Client\Model\GetDocumentsRequest | getDocumentsRequest

try {
    $result = $apiInstance->getuserdocuments($get_documents_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UserDocumentsApi->getuserdocuments: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **get_documents_request** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\GetDocumentsRequest**](../Model/GetDocumentsRequest.md)| getDocumentsRequest | [optional] |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\GetDocumentsResponse**](../Model/GetDocumentsResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
