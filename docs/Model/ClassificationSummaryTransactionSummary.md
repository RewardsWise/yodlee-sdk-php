# # ClassificationSummaryTransactionSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**from_date** | **string** | The date from which the transactions are considered for evaluating the attributes (Date of the oldest transaction for the accountId) | [optional] [readonly]
**card_payments** | **bool** | Indicates whether the account has any card-related payments based on an implicit logic | [optional] [readonly]
**is_primary_account** | **bool** | Indicates whether the account is a primary account based on an implicit logic | [optional] [readonly]
**loan_payments** | **bool** | Indicates whether the account has any loan payments based on an implicit logic | [optional] [readonly]
**to_date** | **string** | The date until which the transactions are considered for evaluating the attributes (Date of the latest transaction for the accountId) | [optional] [readonly]
**bill_payments** | **bool** | Indicates whether the account has any bill payments based on an implicit logic | [optional] [readonly]
**mortgage_payments** | **bool** | Indicates whether the account has any mortgage payments based on an implicit logic | [optional] [readonly]
**salary_credits** | **bool** | Indicates whether the account has salary credits based on an implicit logic | [optional] [readonly]
**is_active_account** | **bool** | Indicates whether the account is an active account based on an implicit logic | [optional] [readonly]
**latest_transactions** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\ClassificationSummaryTransaction[]**](ClassificationSummaryTransaction.md) | An array that lists the details about the latest 3 transactions that occurred in the user&#39;s account | [optional] [readonly]
**income_credits** | **bool** | Indicates whether the account has any income credits based on an implicit logic | [optional] [readonly]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
