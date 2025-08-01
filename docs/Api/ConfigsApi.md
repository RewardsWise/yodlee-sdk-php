# RewardsWise\Yodlee\OpenAPI\Client\ConfigsApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createSubscriptionNotificationEvent()**](ConfigsApi.md#createSubscriptionNotificationEvent) | **POST** /configs/notifications/events/{eventName} | Subscribe For Notification Event |
| [**deleteSubscribedNotificationEvent()**](ConfigsApi.md#deleteSubscribedNotificationEvent) | **DELETE** /configs/notifications/events/{eventName} | Delete Notification Subscription |
| [**getPublicEncryptionKey()**](ConfigsApi.md#getPublicEncryptionKey) | **GET** /configs/publicKey | Get Public Key |
| [**getSubscribedNotificationEvents()**](ConfigsApi.md#getSubscribedNotificationEvents) | **GET** /configs/notifications/events | Get Subscribed Notification Events |
| [**updateSubscribedNotificationEvent()**](ConfigsApi.md#updateSubscribedNotificationEvent) | **PUT** /configs/notifications/events/{eventName} | Update Notification Subscription |


## `createSubscriptionNotificationEvent()`

```php
createSubscriptionNotificationEvent($event_name, $event_request)
```

Subscribe For Notification Event

The subscribe events service is used to subscribe to an event for receiving notifications.<br>The callback URL, where the notification will be posted should be provided to this service.<br>If the callback URL is invalid or inaccessible, the subscription will be unsuccessful, and an error will be thrown.<br>Customers can subscribe to REFRESH,DATA_UPDATES,AUTO_REFRESH_UPDATES,LATEST_BALANCE_UPDATES and CREDIT_MATRIX_REPORT_UPDATES event.<br><br><b>Notes:</b><li>This service is not available in developer sandbox/test environment and will be made available for testing in your dedicated environment, once the contract is signed.<li>The content type has to be passed as application/json for the body parameter.</li>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\ConfigsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$event_name = 'event_name_example'; // string | Name of the webhook subscription event
$event_request = new \RewardsWise\Yodlee\OpenAPI\Client\Model\CreateConfigsNotificationEventRequest(); // \RewardsWise\Yodlee\OpenAPI\Client\Model\CreateConfigsNotificationEventRequest | eventRequest

try {
    $apiInstance->createSubscriptionNotificationEvent($event_name, $event_request);
} catch (Exception $e) {
    echo 'Exception when calling ConfigsApi->createSubscriptionNotificationEvent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **event_name** | **string**| Name of the webhook subscription event | |
| **event_request** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\CreateConfigsNotificationEventRequest**](../Model/CreateConfigsNotificationEventRequest.md)| eventRequest | |

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

## `deleteSubscribedNotificationEvent()`

```php
deleteSubscribedNotificationEvent($event_name)
```

Delete Notification Subscription

The delete events service is used to unsubscribe from an events service.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\ConfigsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$event_name = 'event_name_example'; // string | Name of the webhook subscription event

try {
    $apiInstance->deleteSubscribedNotificationEvent($event_name);
} catch (Exception $e) {
    echo 'Exception when calling ConfigsApi->deleteSubscribedNotificationEvent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **event_name** | **string**| Name of the webhook subscription event | |

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

## `getPublicEncryptionKey()`

```php
getPublicEncryptionKey(): \RewardsWise\Yodlee\OpenAPI\Client\Model\ConfigsPublicKeyResponse
```

Get Public Key

The get public key service provides the public key that should be used to encrypt user credentials while invoking POST /providerAccounts and PUT /providerAccounts endpoints.<br>This service will only work if the PKI (public key infrastructure) feature is enabled for the customer.<br><br><b>Note:</b><li> The key in the response is a string in PEM format.</li><li>This endpoint is not available in the Sandbox environment and it is useful only if the PKI feature is enabled.</li>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\ConfigsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getPublicEncryptionKey();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConfigsApi->getPublicEncryptionKey: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\ConfigsPublicKeyResponse**](../Model/ConfigsPublicKeyResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getSubscribedNotificationEvents()`

```php
getSubscribedNotificationEvents($event_name): \RewardsWise\Yodlee\OpenAPI\Client\Model\ConfigsNotificationResponse
```

Get Subscribed Notification Events

The get events service provides the list of events for which consumers subscribed to receive notifications. <br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\ConfigsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$event_name = 'event_name_example'; // string | Name of the webhook subscription event

try {
    $result = $apiInstance->getSubscribedNotificationEvents($event_name);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConfigsApi->getSubscribedNotificationEvents: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **event_name** | **string**| Name of the webhook subscription event | [optional] |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\ConfigsNotificationResponse**](../Model/ConfigsNotificationResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateSubscribedNotificationEvent()`

```php
updateSubscribedNotificationEvent($event_name, $event_request)
```

Update Notification Subscription

The update events service is used to update the callback URL.<br>If the callback URL is invalid or inaccessible, the subscription will be unsuccessful, and an error will be thrown.<br><br><b>Note:</b> <li>The content type has to be passed as application/json for the body parameter. <br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\ConfigsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$event_name = 'event_name_example'; // string | Name of the webhook subscription event
$event_request = new \RewardsWise\Yodlee\OpenAPI\Client\Model\UpdateConfigsNotificationEventRequest(); // \RewardsWise\Yodlee\OpenAPI\Client\Model\UpdateConfigsNotificationEventRequest | eventRequest

try {
    $apiInstance->updateSubscribedNotificationEvent($event_name, $event_request);
} catch (Exception $e) {
    echo 'Exception when calling ConfigsApi->updateSubscribedNotificationEvent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **event_name** | **string**| Name of the webhook subscription event | |
| **event_request** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\UpdateConfigsNotificationEventRequest**](../Model/UpdateConfigsNotificationEventRequest.md)| eventRequest | |

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
