# # DerivedTransactionsSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**category_type** | **string** | Type of categories provided by transactions/categories service.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, bank, investment&lt;br&gt;&lt;b&gt;Applicable Values&lt;/b&gt;&lt;br&gt; | [optional] [readonly]
**category_summary** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\DerivedCategorySummary[]**](DerivedCategorySummary.md) | Summary of transaction amouts at category level.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, bank, investment&lt;br&gt; | [optional] [readonly]
**credit_total** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\Money**](Money.md) |  | [optional]
**links** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\DerivedTransactionsLinks**](DerivedTransactionsLinks.md) |  | [optional]
**debit_total** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\Money**](Money.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
