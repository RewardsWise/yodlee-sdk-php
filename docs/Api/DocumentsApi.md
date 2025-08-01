# OpenAPI\Client\DocumentsApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteDocument()**](DocumentsApi.md#deleteDocument) | **DELETE** /documents/{documentId} | Delete Document |
| [**downloadDocument()**](DocumentsApi.md#downloadDocument) | **GET** /documents/{documentId} | Download a Document |
| [**getDocuments()**](DocumentsApi.md#getDocuments) | **GET** /documents | Get Documents |


## `deleteDocument()`

```php
deleteDocument($document_id)
```

Delete Document

The delete document service allows the consumer to delete a document. The deleted document will not be returned in the get documents API. The HTTP response code is 204 (success without content).<br>Documents can be deleted only if the document related dataset attributes are subscribed.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$document_id = 'document_id_example'; // string | documentId

try {
    $apiInstance->deleteDocument($document_id);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->deleteDocument: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **document_id** | **string**| documentId | |

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

## `downloadDocument()`

```php
downloadDocument($document_id): \OpenAPI\Client\Model\DocumentDownloadResponse
```

Download a Document

The get document details service allows consumers to download a document. The document is provided in base64.<br>This API is a premium service which requires subscription in advance to use.  Please contact Yodlee Client Services for more information. <br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$document_id = 'document_id_example'; // string | documentId

try {
    $result = $apiInstance->downloadDocument($document_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->downloadDocument: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **document_id** | **string**| documentId | |

### Return type

[**\OpenAPI\Client\Model\DocumentDownloadResponse**](../Model/DocumentDownloadResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getDocuments()`

```php
getDocuments($keyword, $account_id, $doc_type, $from_date, $to_date): \OpenAPI\Client\Model\DocumentResponse
```

Get Documents

The get documents service allows customers to search or retrieve metadata related to documents. <br>The API returns the document as per the input parameters passed. If no date range is provided then all downloaded documents will be retrieved. Details of deleted documents or documents associated to closed providerAccount will not be returned. <br>This API is a premium service which requires subscription in advance to use.  Please contact Yodlee Client Services for more information. <br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$keyword = 'keyword_example'; // string | The string used to search a document by its name.
$account_id = 'account_id_example'; // string | The unique identifier of an account. Retrieve documents for a given accountId.
$doc_type = 'doc_type_example'; // string | Accepts only one of the following valid document types: STMT, TAX, and EBILL.
$from_date = 'from_date_example'; // string | The date from which documents have to be retrieved.
$to_date = 'to_date_example'; // string | The date to which documents have to be retrieved.

try {
    $result = $apiInstance->getDocuments($keyword, $account_id, $doc_type, $from_date, $to_date);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->getDocuments: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **keyword** | **string**| The string used to search a document by its name. | [optional] |
| **account_id** | **string**| The unique identifier of an account. Retrieve documents for a given accountId. | [optional] |
| **doc_type** | **string**| Accepts only one of the following valid document types: STMT, TAX, and EBILL. | [optional] |
| **from_date** | **string**| The date from which documents have to be retrieved. | [optional] |
| **to_date** | **string**| The date to which documents have to be retrieved. | [optional] |

### Return type

[**\OpenAPI\Client\Model\DocumentResponse**](../Model/DocumentResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
