# RewardsWise\Yodlee\OpenAPI\Client\ConsentsApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createConsent()**](ConsentsApi.md#createConsent) | **POST** /consents | Post Consent |
| [**getConsentDetails()**](ConsentsApi.md#getConsentDetails) | **GET** /consents/{consentId} | Get Authorization Details |
| [**getConsentHistory()**](ConsentsApi.md#getConsentHistory) | **GET** /consents/history | Get Consent History |
| [**getConsentHistoryCount()**](ConsentsApi.md#getConsentHistoryCount) | **GET** /consents/history/count | Get Consent History Count |
| [**getConsentPreferences()**](ConsentsApi.md#getConsentPreferences) | **GET** /consents/preferences | Get Consents Preferences |
| [**getConsents()**](ConsentsApi.md#getConsents) | **GET** /consents | Get Consents |
| [**renewConsent()**](ConsentsApi.md#renewConsent) | **PUT** /consents/{consentId}/renewal | Renew Consent |
| [**updateConsent()**](ConsentsApi.md#updateConsent) | **PUT** /consents/{consentId} | Put Consent |


## `createConsent()`

```php
createConsent($consent_request): \RewardsWise\Yodlee\OpenAPI\Client\Model\CreatedConsentResponse
```

Post Consent

The generate consent service is used to generate all the consent information and permissions associated to a provider. <br/>The scope provided in the response is based on the providerId and the datasets provided in the input. <br/>If no dataset value is provided, the datasets that are configured for the customer will be considered. <br/>The configured dataset can be overridden by providing the dataset as an input. <br/>If no applicationName is provided in the input, the default applicationName will be considered. <b>Note:</b>This service supports the localization feature and accepts locale as a header parameter.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\ConsentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$consent_request = new \RewardsWise\Yodlee\OpenAPI\Client\Model\CreateConsentRequest(); // \RewardsWise\Yodlee\OpenAPI\Client\Model\CreateConsentRequest | Unique identifier for the provider site(mandatory), the name of the application,  <br/>the flag responsible to include html content in the response, <br/>when passed as true and the name of the dataset attribute supported by the provider.

try {
    $result = $apiInstance->createConsent($consent_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConsentsApi->createConsent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **consent_request** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\CreateConsentRequest**](../Model/CreateConsentRequest.md)| Unique identifier for the provider site(mandatory), the name of the application,  &lt;br/&gt;the flag responsible to include html content in the response, &lt;br/&gt;when passed as true and the name of the dataset attribute supported by the provider. | |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\CreatedConsentResponse**](../Model/CreatedConsentResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getConsentDetails()`

```php
getConsentDetails($consent_id): \RewardsWise\Yodlee\OpenAPI\Client\Model\UpdatedConsentResponse
```

Get Authorization Details

The get authorization URL for consent service provides the authorization URL for the renew consent flow, within the consent dashboard.<b>Note:</b>This service supports the localization feature and accepts locale as a header parameter.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\ConsentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$consent_id = 56; // int | Consent Id generated through POST Consent.

try {
    $result = $apiInstance->getConsentDetails($consent_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConsentsApi->getConsentDetails: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **consent_id** | **int**| Consent Id generated through POST Consent. | |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\UpdatedConsentResponse**](../Model/UpdatedConsentResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getConsentHistory()`

```php
getConsentHistory($consent_id, $from_date, $skip, $to_date, $top): \RewardsWise\Yodlee\OpenAPI\Client\Model\ConsentHistoryResponse
```

Get Consent History

The get consent history service is used to retrieve all the history related to the consent. <br/>All history event details for few fields like userDataPurge, deidentificationPreference and consentCollectionPeriod may not be available for older AU Open Banking consents and other Open Banking regions.<br/>For any consent, history will be captured and available from consent authorization (consent status Active) event onwards.<br/><b>Note:</b><br/>  i. Duration (fromDate and toDate) is optional. In the absence of duration, one year history is retrieved from today's date.<br/>ii. The pagination feature is available by default. If no values are passed in the skip and top parameters, the API will only return the first 500 records.<br/>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\ConsentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$consent_id = 'consent_id_example'; // string | Consent Id generated through POST Consent.
$from_date = 'from_date_example'; // string | Consent History from date(YYYY-MM-DD)
$skip = 56; // int | skip (Min 0)
$to_date = 'to_date_example'; // string | Consent History end date (YYYY-MM-DD)
$top = 56; // int | top (Max 500)

try {
    $result = $apiInstance->getConsentHistory($consent_id, $from_date, $skip, $to_date, $top);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConsentsApi->getConsentHistory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **consent_id** | **string**| Consent Id generated through POST Consent. | |
| **from_date** | **string**| Consent History from date(YYYY-MM-DD) | [optional] |
| **skip** | **int**| skip (Min 0) | [optional] |
| **to_date** | **string**| Consent History end date (YYYY-MM-DD) | [optional] |
| **top** | **int**| top (Max 500) | [optional] |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\ConsentHistoryResponse**](../Model/ConsentHistoryResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getConsentHistoryCount()`

```php
getConsentHistoryCount($consent_id, $from_date, $to_date): \RewardsWise\Yodlee\OpenAPI\Client\Model\ConsentHistoryCountResponse
```

Get Consent History Count

The count service provides the total number of history records for a specific consent. <br/>If you are implementing pagination for consent history, call this endpoint before calling GET /consents/history to know the number of records for the given consent that are returned for the input parameters passed.<br/>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\ConsentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$consent_id = 'consent_id_example'; // string | Consent Id generated through POST Consent.
$from_date = 'from_date_example'; // string | Consent History from date(YYYY-MM-DD)
$to_date = 'to_date_example'; // string | Consent History end date (YYYY-MM-DD)

try {
    $result = $apiInstance->getConsentHistoryCount($consent_id, $from_date, $to_date);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConsentsApi->getConsentHistoryCount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **consent_id** | **string**| Consent Id generated through POST Consent. | |
| **from_date** | **string**| Consent History from date(YYYY-MM-DD) | [optional] |
| **to_date** | **string**| Consent History end date (YYYY-MM-DD) | [optional] |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\ConsentHistoryCountResponse**](../Model/ConsentHistoryCountResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getConsentPreferences()`

```php
getConsentPreferences($consent_id): \RewardsWise\Yodlee\OpenAPI\Client\Model\ConsentPreferencesResponse
```

Get Consents Preferences

This API service provides user's preferences for the consent

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\ConsentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$consent_id = 'consent_id_example'; // string | consentId

try {
    $result = $apiInstance->getConsentPreferences($consent_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConsentsApi->getConsentPreferences: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **consent_id** | **string**| consentId | |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\ConsentPreferencesResponse**](../Model/ConsentPreferencesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getConsents()`

```php
getConsents($consent_ids, $include, $provider_account_ids): \RewardsWise\Yodlee\OpenAPI\Client\Model\ConsentResponse
```

Get Consents

The get consent service is used to retrieve all the consents submitted to Yodlee. <br>The service can be used to build a manage consent interface or a consent dashboard to implement the renew and revoke consent flows.<br><b>Note:</b>This service supports the localization feature and accepts locale as a header parameter.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\ConsentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$consent_ids = 'consent_ids_example'; // string | Consent Id generated through POST Consent.
$include = 'include_example'; // string | The flag responsible to include renew details like sharing duration and reauthorization required
$provider_account_ids = 'provider_account_ids_example'; // string | Unique identifier for the provider account resource. This is created during account addition.

try {
    $result = $apiInstance->getConsents($consent_ids, $include, $provider_account_ids);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConsentsApi->getConsents: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **consent_ids** | **string**| Consent Id generated through POST Consent. | [optional] |
| **include** | **string**| The flag responsible to include renew details like sharing duration and reauthorization required | [optional] |
| **provider_account_ids** | **string**| Unique identifier for the provider account resource. This is created during account addition. | [optional] |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\ConsentResponse**](../Model/ConsentResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `renewConsent()`

```php
renewConsent($consent_id, $renew_consent_request): \RewardsWise\Yodlee\OpenAPI\Client\Model\RenewConsentResponse
```

Renew Consent

The consent renewal service is used to renew the consent by validating the consent state. This API supports both UK and AU Open Banking. </br><b>Renewing an UK Open Banking consent:</b><br><li>Before the grace period of 90 days: The consent will be renewed using the third-party provider (TPP) renewal process that Yodlee does, and no consent reauthorisation is required.The API response will contain the complete renewed consent object.</li><li>After the grace period of 90 days: The API will provide an authorisation URL to redirect the user to the financial institution site to complete the consent reauthorization process.<br><b>Renewing an AU Open Banking consent:</b><br><li>Invoke this API, and in the API response, an authorisation URL will be provided to redirect the user to the financial institution site to complete the consent reauthorisation process.</li><br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\ConsentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$consent_id = 56; // int | Consent Id to be renewed.
$renew_consent_request = new \RewardsWise\Yodlee\OpenAPI\Client\Model\RenewConsentRequest(); // \RewardsWise\Yodlee\OpenAPI\Client\Model\RenewConsentRequest | renewal entity from consent details service.

try {
    $result = $apiInstance->renewConsent($consent_id, $renew_consent_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConsentsApi->renewConsent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **consent_id** | **int**| Consent Id to be renewed. | |
| **renew_consent_request** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\RenewConsentRequest**](../Model/RenewConsentRequest.md)| renewal entity from consent details service. | [optional] |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\RenewConsentResponse**](../Model/RenewConsentResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateConsent()`

```php
updateConsent($consent_id, $consent_request): \RewardsWise\Yodlee\OpenAPI\Client\Model\UpdatedConsentResponse
```

Put Consent

The update consent service is used to capture the user acceptance of the consent presented to him or her. <br/>This service returns the authorization-redirect URL that should be used to display to the user, the bank's authentication interface.<b>Note:</b>This service supports the localization feature and accepts locale as a header parameter.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\ConsentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$consent_id = 56; // int | Consent Id generated through POST Consent.
$consent_request = new \RewardsWise\Yodlee\OpenAPI\Client\Model\UpdateConsentRequest(); // \RewardsWise\Yodlee\OpenAPI\Client\Model\UpdateConsentRequest | Applicable Open Banking data cluster values.

try {
    $result = $apiInstance->updateConsent($consent_id, $consent_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConsentsApi->updateConsent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **consent_id** | **int**| Consent Id generated through POST Consent. | |
| **consent_request** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\UpdateConsentRequest**](../Model/UpdateConsentRequest.md)| Applicable Open Banking data cluster values. | |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\UpdatedConsentResponse**](../Model/UpdatedConsentResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
