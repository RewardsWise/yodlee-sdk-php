# OpenAPI\Client\VerificationApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getClassificationSummary()**](VerificationApi.md#getClassificationSummary) | **GET** /verification/classification/summary | Get Classification Summary |
| [**getHolderProfile()**](VerificationApi.md#getHolderProfile) | **GET** /verification/holderProfile | Get Holder Profile |
| [**getVerificationStatus()**](VerificationApi.md#getVerificationStatus) | **GET** /verification | Get Verification Status |
| [**getVerifiedAccounts()**](VerificationApi.md#getVerifiedAccounts) | **GET** /verification/verifiedAccounts | Get Verified Accounts |
| [**initiateMatchingOrChallengeDepositeVerification()**](VerificationApi.md#initiateMatchingOrChallengeDepositeVerification) | **POST** /verification | Initiaite Challenge Deposit |
| [**verifyChallengeDeposit()**](VerificationApi.md#verifyChallengeDeposit) | **PUT** /verification | Verify Challenge Deposit |


## `getClassificationSummary()`

```php
getClassificationSummary($account_id): \OpenAPI\Client\Model\ClassificationSummaryResponse
```

Get Classification Summary

The get classification summary API service returns attributes that provide account-level and transaction-level summary for a user's account.<br><br>As a prerequisite, the Account Verification customers should have Transactions enabled to fetch a response. The API can be invoked only for an account verified by the user following the get verified accounts API call. If the prerequisite is not satisfied, an appropriate error will be returned on invoking the API.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\VerificationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_id = 'account_id_example'; // string | accountId

try {
    $result = $apiInstance->getClassificationSummary($account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VerificationApi->getClassificationSummary: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**| accountId | |

### Return type

[**\OpenAPI\Client\Model\ClassificationSummaryResponse**](../Model/ClassificationSummaryResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getHolderProfile()`

```php
getHolderProfile($provider_account_id, $account_id): \OpenAPI\Client\Model\HolderProfileResponse
```

Get Holder Profile

The Holder Profile API service allows retrieving the user's profile details (i.e., PII data such as name, email, phone number, and address) that are available at the provider account and each account level. The API accepts the providerAccountId and retrieves the profile information available under it and all the details available under each of the associated accounts.  <br><br>This service can only be invoked by Yodlee API v1.1, FastLink 3, and FastLink 4 customers. <br><br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\VerificationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$provider_account_id = 'provider_account_id_example'; // string | providerAccountId.
$account_id = 'account_id_example'; // string | accountId

try {
    $result = $apiInstance->getHolderProfile($provider_account_id, $account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VerificationApi->getHolderProfile: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **provider_account_id** | **string**| providerAccountId. | |
| **account_id** | **string**| accountId | [optional] |

### Return type

[**\OpenAPI\Client\Model\HolderProfileResponse**](../Model/HolderProfileResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getVerificationStatus()`

```php
getVerificationStatus($account_id, $provider_account_id, $verification_type): \OpenAPI\Client\Model\VerificationStatusResponse
```

Get Verification Status

The get verification status service is used to retrieve the verification status of all accounts for which the MS or CDV process has been initiated.<br>For the MS process, the account details object returns the aggregated information of the verified accounts. For the CDV process, the account details object returns the user provided account information.<br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\VerificationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$account_id = 'account_id_example'; // string | Comma separated accountId
$provider_account_id = 'provider_account_id_example'; // string | Comma separated providerAccountId
$verification_type = 'verification_type_example'; // string | verificationType

try {
    $result = $apiInstance->getVerificationStatus($account_id, $provider_account_id, $verification_type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VerificationApi->getVerificationStatus: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **account_id** | **string**| Comma separated accountId | [optional] |
| **provider_account_id** | **string**| Comma separated providerAccountId | [optional] |
| **verification_type** | **string**| verificationType | [optional] |

### Return type

[**\OpenAPI\Client\Model\VerificationStatusResponse**](../Model/VerificationStatusResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getVerifiedAccounts()`

```php
getVerifiedAccounts($provider_account_id, $account_id, $is_selected, $verification_status): \OpenAPI\Client\Model\VerifiedAccountResponse
```

Get Verified Accounts

The Verified Accounts API v1.1 provides information about the bank and investment accounts that the user  has selected for verification, during the Account Verification flow on FastLink 4. By default, the API only returns information of the accounts that were selected and have been successfully verified. <br><br>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\VerificationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$provider_account_id = 'provider_account_id_example'; // string | providerAccountId.
$account_id = 'account_id_example'; // string | Comma separated accountIds.
$is_selected = 'is_selected_example'; // string | Comma separated isSelected. Allowed values are true, false. <br>
$verification_status = 'verification_status_example'; // string | Comma separated verificationStatus. Allowed values are SUCCESS, FAILED <br><b>Note:</b> If no value is passed, the implicit default value is SUCCESS.

try {
    $result = $apiInstance->getVerifiedAccounts($provider_account_id, $account_id, $is_selected, $verification_status);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VerificationApi->getVerifiedAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **provider_account_id** | **string**| providerAccountId. | |
| **account_id** | **string**| Comma separated accountIds. | [optional] |
| **is_selected** | **string**| Comma separated isSelected. Allowed values are true, false. &lt;br&gt; | [optional] |
| **verification_status** | **string**| Comma separated verificationStatus. Allowed values are SUCCESS, FAILED &lt;br&gt;&lt;b&gt;Note:&lt;/b&gt; If no value is passed, the implicit default value is SUCCESS. | [optional] |

### Return type

[**\OpenAPI\Client\Model\VerifiedAccountResponse**](../Model/VerifiedAccountResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `initiateMatchingOrChallengeDepositeVerification()`

```php
initiateMatchingOrChallengeDepositeVerification($verification_param): \OpenAPI\Client\Model\VerificationResponse
```

Initiaite Challenge Deposit

The post verification service is used to initiate the matching service (MS) and the challenge deposit account verification (CDV) process to verify account ownership.<br>The MS and CDV process can verify ownership of only bank accounts (i.e., checking and savings).<br>The MS verification can be initiated only for an already aggregated account or a providerAccount.<br>The prerequisite for the MS verification process is to request the ACCT_PROFILE dataset with the HOLDER_NAME attribute.<br>In the MS verification process, a string-match of the account holder name with the registered user name is performed instantaneously. You can contact the Yodlee CustomerCare to configure the full name or only the last name match.<br>Once the CDV process is initiated Yodlee will post the microtransaction (i.e., credit and debit) in the user's account. The CDV process takes 2 to 3 days to complete as it requires the user to provide the microtransaction details.<br>The CDV process is currently supported only in the United States.<br>The verificationId in the response can be used to track the verification request.<br><br><b>Notes:</b><li>This endpoint cannot be used to test the CDV functionality in the developer sandbox or test environment. You will need a money transmitter license to implement the CDV functionality and also require the Yodlee Professional Services team's assistance to set up a dedicated environment.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\VerificationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$verification_param = new \OpenAPI\Client\Model\VerificationRequest(); // \OpenAPI\Client\Model\VerificationRequest | verification information

try {
    $result = $apiInstance->initiateMatchingOrChallengeDepositeVerification($verification_param);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VerificationApi->initiateMatchingOrChallengeDepositeVerification: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **verification_param** | [**\OpenAPI\Client\Model\VerificationRequest**](../Model/VerificationRequest.md)| verification information | |

### Return type

[**\OpenAPI\Client\Model\VerificationResponse**](../Model/VerificationResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `verifyChallengeDeposit()`

```php
verifyChallengeDeposit($verification_param): \OpenAPI\Client\Model\VerificationResponse
```

Verify Challenge Deposit

The put verification service is used to complete the challenge deposit verification (CDV) process.<br>This service is used only by the customer of CDV flow.<br>In the CDV process, the user-provided microtransaction details (i.e., credit and debit) is matched against the microtransactions posted by Yodlee. For a successful verification of the account's ownership both the microtransaction details should match.<br>The CDV process is currently supported only in the United States.<br><br><b>Notes:</b><ul><li>This endpoint cannot be used to test the CDV functionality in the developer sandbox or test environment. You will need a money transmitter license to implement the CDV functionality and also require the Yodlee Professional Services team's assistance to set up a dedicated environment.</li></ul>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\VerificationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$verification_param = new \OpenAPI\Client\Model\UpdateVerificationRequest(); // \OpenAPI\Client\Model\UpdateVerificationRequest | verification information

try {
    $result = $apiInstance->verifyChallengeDeposit($verification_param);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VerificationApi->verifyChallengeDeposit: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **verification_param** | [**\OpenAPI\Client\Model\UpdateVerificationRequest**](../Model/UpdateVerificationRequest.md)| verification information | |

### Return type

[**\OpenAPI\Client\Model\VerificationResponse**](../Model/VerificationResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json;charset=UTF-8`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
