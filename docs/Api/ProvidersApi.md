# OpenAPI\Client\ProvidersApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getAllProviders()**](ProvidersApi.md#getAllProviders) | **GET** /providers | Get Providers |
| [**getProvider()**](ProvidersApi.md#getProvider) | **GET** /providers/{providerId} | Get Provider Details |
| [**getProvidersCount()**](ProvidersApi.md#getProvidersCount) | **GET** /providers/count | Get Providers Count |


## `getAllProviders()`

```php
getAllProviders($capability, $datasetfilter, $full_account_number_fields, $institution_id, $name, $priority, $provider_id, $skip, $top): \OpenAPI\Client\Model\ProviderResponse
```

Get Providers

The get provider service is used to get all the providers that are enabled, search a provider service by name or routing number and get popular sites of a region. <br>Searching for a provider using a routing number is applicable only to the USA and Canada regions.<br>The valid values for priority are: <br>   1. cobrand: Returns providers enabled for the cobrand (Default priority)<br>   2. popular: Returns providers popular among users of the customer<br><br>Only the datasets, attributes, and containers that are enabled for the customer will be returned in the response.<br>Input for the dataset$filter should adhere to the following expression:<br><dataset.name>[<attribute.name>.container[<container> OR <container>] OR <attribute.name>.container[<container>]] <br>OR <dataset.name>[<attribute.name> OR <attribute.name>]<br><b>dataset$filter value examples:</b><br>ACCT_PROFILE[FULL_ACCT_NUMBER.container[bank OR investment OR creditCard]]<br>ACCT_PROFILE[FULL_ACCT_NUMBER.container[bank]]<br>BASIC_AGG_DATA[ACCOUNT_DETAILS.container[bank OR investment] OR HOLDINGS.container[bank]] OR ACCT_PROFILE[FULL_ACCT_NUMBER.container[bank]]<br>BASIC_AGG_DATA<br>BASIC_AGG_DATA OR ACCT_PROFILE<br>BASIC_AGG_DATA [ ACCOUNT_DETAILS OR HOLDINGS ]<br>BASIC_AGG_DATA [ ACCOUNT_DETAILS] OR DOCUMENT <br>BASIC_AGG_DATA [ BASIC_ACCOUNT_INFO OR ACCOUNT_DETAILS ] <br><br>The fullAcountNumberFields is specified to filter the providers that have paymentAccountNumber or unmaskedAccountNumber support in the FULL_ACCT_NUMBER dataset attribute.<br><b>Examples for usage of fullAccountNumberFields </b><br>dataset$filter=ACCT_PROFILE[ FULL_ACCT_NUMBER.container [ bank ]] &amp; fullAccountNumberFields=paymentAccountNumber<br>dataset$filter=ACCT_PROFILE[ FULL_ACCT_NUMBER.container [ bank ]] &amp; fullAccountNumberFields=unmaskedAccountNumber<br>dataset$filter=ACCT_PROFILE[ FULL_ACCT_NUMBER.container [ bank ]] &amp; fullAccountNumberFields=unmaskedAccountNumber,paymentAccountNumber<br><br>The skip and top parameters are used for pagination. In the skip and top parameters, pass the number of records to be skipped and retrieved, respectively.<br>The response header provides the links to retrieve the next and previous set of transactions.<br><br><b>Note:</b> <ol><li>In a product flow involving user interaction, Yodlee recommends invoking this service with filters.<li>Without filters, the service may perform slowly as it takes a few minutes to return data in the response.<li>The AuthParameter appears in the response only in case of token-based aggregation sites.<li>The pagination feature only applies when the priority parameter is set as cobrand. If no values are provided in the skip and top parameters, the API will only return the first 500 records.<li>This service supports the localization feature and accepts locale as a header parameter.<li>The capability has been deprecated in query parameter and response.</li></ol>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ProvidersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$capability = 'capability_example'; // string | CHALLENGE_DEPOSIT_VERIFICATION - capability search is deprecated
$datasetfilter = 'datasetfilter_example'; // string | Expression to filter the providers by dataset(s) or dataset attribute(s). The default value will be the dataset or dataset attributes configured as default for the customer.
$full_account_number_fields = 'full_account_number_fields_example'; // string | Specify to filter the providers with values paymentAccountNumber,unmaskedAccountNumber.
$institution_id = 56; // int | Institution Id for Single site selection
$name = 'name_example'; // string | Name in minimum 1 character or routing number.
$priority = 'priority_example'; // string | Search priority
$provider_id = 'provider_id_example'; // string | Max 5 Comma seperated Provider Ids
$skip = 56; // int | skip (Min 0) - This is not applicable along with 'name' parameter.
$top = 56; // int | top (Max 500) - This is not applicable along with 'name' parameter.

try {
    $result = $apiInstance->getAllProviders($capability, $datasetfilter, $full_account_number_fields, $institution_id, $name, $priority, $provider_id, $skip, $top);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProvidersApi->getAllProviders: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **capability** | **string**| CHALLENGE_DEPOSIT_VERIFICATION - capability search is deprecated | [optional] |
| **datasetfilter** | **string**| Expression to filter the providers by dataset(s) or dataset attribute(s). The default value will be the dataset or dataset attributes configured as default for the customer. | [optional] |
| **full_account_number_fields** | **string**| Specify to filter the providers with values paymentAccountNumber,unmaskedAccountNumber. | [optional] |
| **institution_id** | **int**| Institution Id for Single site selection | [optional] |
| **name** | **string**| Name in minimum 1 character or routing number. | [optional] |
| **priority** | **string**| Search priority | [optional] |
| **provider_id** | **string**| Max 5 Comma seperated Provider Ids | [optional] |
| **skip** | **int**| skip (Min 0) - This is not applicable along with &#39;name&#39; parameter. | [optional] |
| **top** | **int**| top (Max 500) - This is not applicable along with &#39;name&#39; parameter. | [optional] |

### Return type

[**\OpenAPI\Client\Model\ProviderResponse**](../Model/ProviderResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getProvider()`

```php
getProvider($provider_id): \OpenAPI\Client\Model\ProviderDetailResponse
```

Get Provider Details

The get provider detail service is used to get detailed information including the login form for a provider.<br>The response is a provider object that includes information such as name of the provider, <br>provider's base URL, a list of containers supported by the provider, the login form details of the provider, etc.<br>Only enabled datasets, attributes and containers gets returned in the response.<br><br><b>Note:</b><li>This service supports the localization feature and accepts locale as a header parameter.<li>The capability has been deprecated in the response.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ProvidersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$provider_id = 56; // int | providerId

try {
    $result = $apiInstance->getProvider($provider_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProvidersApi->getProvider: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **provider_id** | **int**| providerId | |

### Return type

[**\OpenAPI\Client\Model\ProviderDetailResponse**](../Model/ProviderDetailResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getProvidersCount()`

```php
getProvidersCount($capability, $datasetfilter, $full_account_number_fields, $name, $priority): \OpenAPI\Client\Model\ProvidersCountResponse
```

Get Providers Count

The count service provides the total number of providers that get returned in the GET /providers depending on the input parameters passed.<br>If you are implementing pagination for providers, call this endpoint before calling GET /providers to know the number of providers that are returned for the input parameters passed.<br>The functionality of the input parameters remains the same as that of the GET /providers endpoint<br><br><b>Note:</b> <li>The capability has been deprecated in the query parameter.</li>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ProvidersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$capability = 'capability_example'; // string | CHALLENGE_DEPOSIT_VERIFICATION - capability search is deprecated
$datasetfilter = 'datasetfilter_example'; // string | Expression to filter the providers by dataset(s) or dataset attribute(s). The default value will be the dataset or dataset attributes configured as default for the customer.
$full_account_number_fields = 'full_account_number_fields_example'; // string | Specify to filter the providers with values paymentAccountNumber,unmaskedAccountNumber.
$name = 'name_example'; // string | Name in minimum 1 character or routing number.
$priority = 'priority_example'; // string | Search priority

try {
    $result = $apiInstance->getProvidersCount($capability, $datasetfilter, $full_account_number_fields, $name, $priority);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProvidersApi->getProvidersCount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **capability** | **string**| CHALLENGE_DEPOSIT_VERIFICATION - capability search is deprecated | [optional] |
| **datasetfilter** | **string**| Expression to filter the providers by dataset(s) or dataset attribute(s). The default value will be the dataset or dataset attributes configured as default for the customer. | [optional] |
| **full_account_number_fields** | **string**| Specify to filter the providers with values paymentAccountNumber,unmaskedAccountNumber. | [optional] |
| **name** | **string**| Name in minimum 1 character or routing number. | [optional] |
| **priority** | **string**| Search priority | [optional] |

### Return type

[**\OpenAPI\Client\Model\ProvidersCountResponse**](../Model/ProvidersCountResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
