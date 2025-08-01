# # ClassificationSummaryAccountSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_id** | **int** | The primary key of the account resource and the unique identifier for the account.&lt;br&gt;&lt;br&gt;&lt;b&gt;Aggregated / Manual&lt;/b&gt;: Aggregated&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: bank | [optional] [readonly]
**last_updated** | **string** | The date-time the account information was last retrieved from the provider site and updated in the Yodlee system | [optional] [readonly]
**site** | **string** | The name of the provider site | [optional] [readonly]
**account_name** | **string** | The account name as it appears at the site | [optional] [readonly]
**account_type** | **string** | The type of account that is aggregated such as savings, checking, etc. The account type is derived based on the attributes of the account. | [optional] [readonly]
**account_open_date** | **string** | The date on which the user opened the account at the provider site | [optional] [readonly]
**transaction_summary** | [**\OpenAPI\Client\Model\ClassificationSummaryTransactionSummary**](ClassificationSummaryTransactionSummary.md) |  | [optional]
**available_balance** | [**\OpenAPI\Client\Model\Money**](Money.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
