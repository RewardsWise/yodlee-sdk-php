# RewardsWise\Yodlee\OpenAPI\Client\CobrandApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**cobrandLogin()**](CobrandApi.md#cobrandLogin) | **POST** /cobrand/login | Cobrand Login |
| [**cobrandLogout()**](CobrandApi.md#cobrandLogout) | **POST** /cobrand/logout | Cobrand Logout |
| [**createSubscriptionEvent()**](CobrandApi.md#createSubscriptionEvent) | **POST** /cobrand/config/notifications/events/{eventName} | Subscribe Event |
| [**deleteSubscribedEvent()**](CobrandApi.md#deleteSubscribedEvent) | **DELETE** /cobrand/config/notifications/events/{eventName} | Delete Subscription |
| [**getPublicKey()**](CobrandApi.md#getPublicKey) | **GET** /cobrand/publicKey | Get Public Key |
| [**getSubscribedEvents()**](CobrandApi.md#getSubscribedEvents) | **GET** /cobrand/config/notifications/events | Get Subscribed Events |
| [**updateSubscribedEvent()**](CobrandApi.md#updateSubscribedEvent) | **PUT** /cobrand/config/notifications/events/{eventName} | Update Subscription |


## `cobrandLogin()`

```php
cobrandLogin($cobrand_login_request): \RewardsWise\Yodlee\OpenAPI\Client\Model\CobrandLoginResponse
```

Cobrand Login

The cobrand login service authenticates a cobrand.<br>Cobrand session in the response includes the cobrand session token (cobSession) <br>which is used in subsequent API calls like registering or signing in the user. <br>The idle timeout for a cobrand session is 2 hours and the absolute timeout is 24 hours. This service can be <br>invoked to create a new cobrand session token. <br><b>Note:</b> This endpoint is deprecated for customers using the API Key-based authentication and is applicable only to customers who use the SAML-based authentication.<br>The content type has to be passed as application/json for the body parameter. <br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\CobrandApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$cobrand_login_request = new \RewardsWise\Yodlee\OpenAPI\Client\Model\CobrandLoginRequest(); // \RewardsWise\Yodlee\OpenAPI\Client\Model\CobrandLoginRequest | cobrandLoginRequest

try {
    $result = $apiInstance->cobrandLogin($cobrand_login_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CobrandApi->cobrandLogin: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **cobrand_login_request** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\CobrandLoginRequest**](../Model/CobrandLoginRequest.md)| cobrandLoginRequest | |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\CobrandLoginResponse**](../Model/CobrandLoginResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `cobrandLogout()`

```php
cobrandLogout()
```

Cobrand Logout

The cobrand logout service is used to log out the cobrand.<br>This service does not return a response. The HTTP response code is 204 (Success with no content).<br><b>Note:</b> This endpoint is deprecated for customers using the API Key-based authentication and is applicable only to customers who use the SAML-based authentication.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\CobrandApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->cobrandLogout();
} catch (Exception $e) {
    echo 'Exception when calling CobrandApi->cobrandLogout: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createSubscriptionEvent()`

```php
createSubscriptionEvent($event_name, $event_request)
```

Subscribe Event

<b>Refer POST /configs/notifications/events/{eventName}.</b><br>The subscribe events service is used to subscribe to an event for receiving notifications.<br>The callback URL, where the notification will be posted should be provided to this service.<br>If the callback URL is invalid or inaccessible, the subscription will be unsuccessful, and an error will be thrown.<br>Customers can subscribe to REFRESH,DATA_UPDATES and AUTO_REFRESH_UPDATES event.<br><br><b>Notes</b>:<br>This service is not available in developer sandbox/test environment and will be made available for testing in your dedicated environment, once the contract is signed.<br>The content type has to be passed as application/json for the body parameter.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\CobrandApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$event_name = 'event_name_example'; // string | eventName
$event_request = new \RewardsWise\Yodlee\OpenAPI\Client\Model\CreateCobrandNotificationEventRequest(); // \RewardsWise\Yodlee\OpenAPI\Client\Model\CreateCobrandNotificationEventRequest | eventRequest

try {
    $apiInstance->createSubscriptionEvent($event_name, $event_request);
} catch (Exception $e) {
    echo 'Exception when calling CobrandApi->createSubscriptionEvent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **event_name** | **string**| eventName | |
| **event_request** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\CreateCobrandNotificationEventRequest**](../Model/CreateCobrandNotificationEventRequest.md)| eventRequest | |

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

## `deleteSubscribedEvent()`

```php
deleteSubscribedEvent($event_name)
```

Delete Subscription

<b>Refer DELETE /configs/notifications/events/{eventName}.</b><br>The delete events service is used to unsubscribe from an events service.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\CobrandApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$event_name = 'event_name_example'; // string | eventName

try {
    $apiInstance->deleteSubscribedEvent($event_name);
} catch (Exception $e) {
    echo 'Exception when calling CobrandApi->deleteSubscribedEvent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **event_name** | **string**| eventName | |

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

## `getPublicKey()`

```php
getPublicKey(): \RewardsWise\Yodlee\OpenAPI\Client\Model\CobrandPublicKeyResponse
```

Get Public Key

<b>Refer GET /configs/publicKey.</b><br>The get public key service provides the customer the public key that should be used to encrypt the user credentials before sending it to Yodlee.<br>This endpoint is useful only for PKI enabled.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\CobrandApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getPublicKey();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CobrandApi->getPublicKey: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\CobrandPublicKeyResponse**](../Model/CobrandPublicKeyResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getSubscribedEvents()`

```php
getSubscribedEvents($event_name): \RewardsWise\Yodlee\OpenAPI\Client\Model\CobrandNotificationResponse
```

Get Subscribed Events

<b>Refer GET /configs/notifications/events.</b><br>The get events service provides the list of events for which consumers subscribed <br>to receive notifications. <br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\CobrandApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$event_name = 'event_name_example'; // string | eventName

try {
    $result = $apiInstance->getSubscribedEvents($event_name);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CobrandApi->getSubscribedEvents: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **event_name** | **string**| eventName | [optional] |

### Return type

[**\RewardsWise\Yodlee\OpenAPI\Client\Model\CobrandNotificationResponse**](../Model/CobrandNotificationResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateSubscribedEvent()`

```php
updateSubscribedEvent($event_name, $event_request)
```

Update Subscription

<b>Refer PUT /configs/notifications/events/{eventName}.</b><br>The update events service is used to update the callback URL.<br>If the callback URL is invalid or inaccessible, the subscription will be unsuccessful, and an error will be thrown.<br><b>Note:</b> The content type has to be passed as application/json for the body parameter. <br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new RewardsWise\Yodlee\OpenAPI\Client\Api\CobrandApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$event_name = 'event_name_example'; // string | eventName
$event_request = new \RewardsWise\Yodlee\OpenAPI\Client\Model\UpdateCobrandNotificationEventRequest(); // \RewardsWise\Yodlee\OpenAPI\Client\Model\UpdateCobrandNotificationEventRequest | eventRequest

try {
    $apiInstance->updateSubscribedEvent($event_name, $event_request);
} catch (Exception $e) {
    echo 'Exception when calling CobrandApi->updateSubscribedEvent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **event_name** | **string**| eventName | |
| **event_request** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\UpdateCobrandNotificationEventRequest**](../Model/UpdateCobrandNotificationEventRequest.md)| eventRequest | |

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
