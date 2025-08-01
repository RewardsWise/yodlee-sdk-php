# # UpdateVerification

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_id** | **int** | Unique identifier for the account.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST verification&lt;/li&gt;&lt;li&gt;GET verification&lt;/li&gt;&lt;li&gt;PUT verification&lt;/li&gt;&lt;/ul&gt; | [optional]
**reason** | **string** | The reason the account verification failed.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST verification&lt;/li&gt;&lt;li&gt;GET verification&lt;/li&gt;&lt;li&gt;PUT verification&lt;/li&gt;&lt;/ul&gt; | [optional] [readonly]
**verification_status** | **string** | The status of the account verification.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST verification&lt;/li&gt;&lt;li&gt;GET verification&lt;/li&gt;&lt;li&gt;PUT verification&lt;/li&gt;&lt;/ul&gt;&lt;br&gt;&lt;b&gt;Applicable Values&lt;/b&gt; | [optional] [readonly]
**provider_account_id** | **int** | Unique identifier for the provider account.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST verification&lt;/li&gt;&lt;li&gt;GET verification&lt;/li&gt;&lt;li&gt;PUT verification&lt;/li&gt;&lt;/ul&gt; | [optional]
**additional_message** | **string** | The additional information of the status of account verification.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;GET verification&lt;/li&gt;&lt;/ul&gt;&lt;br&gt;&lt;b&gt;Applicable Values&lt;/b&gt; | [optional] [readonly]
**verification_type** | **string** | The account verification type.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST verification&lt;/li&gt;&lt;li&gt;GET verification&lt;/li&gt;&lt;li&gt;PUT verification&lt;/li&gt;&lt;/ul&gt;&lt;br&gt;&lt;b&gt;Applicable Values&lt;/b&gt; | [optional]
**account** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\VerificationAccount**](VerificationAccount.md) |  | [optional]
**transaction** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\VerificationTransaction[]**](VerificationTransaction.md) |  |
**transaction_reference_text** | **bool** | A one time reference code of randomly generated 4 digits that is sent along with the single credit transaction and visible in transaction reference field.&lt;br&gt;This is applicable only when single ACH key is enabled. | [optional]
**verification_date** | **string** | The date of the account verification.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST verification&lt;/li&gt;&lt;li&gt;GET verification&lt;/li&gt;&lt;li&gt;PUT verification&lt;/li&gt;&lt;/ul&gt; | [optional] [readonly]
**verification_id** | **int** | Unique identifier for the verification request.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST verification&lt;/li&gt;&lt;li&gt;GET verification&lt;/li&gt;&lt;li&gt;PUT verification&lt;/li&gt;&lt;/ul&gt; | [optional] [readonly]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
