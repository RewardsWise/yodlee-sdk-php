# # DerivedCategorySummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**credit_total** | [**\OpenAPI\Client\Model\Money**](Money.md) |  | [optional]
**details** | [**\OpenAPI\Client\Model\DerivedCategorySummaryDetails[]**](DerivedCategorySummaryDetails.md) | Credit and debit summary per date.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, bank, investment&lt;br&gt; | [optional] [readonly]
**links** | [**\OpenAPI\Client\Model\DerivedTransactionsLinks**](DerivedTransactionsLinks.md) |  | [optional]
**category_name** | **string** | The name of the category.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, bank, investment&lt;br&gt; | [optional] [readonly]
**category_id** | **int** | Id of the category. This information is provided by transactions/categories service.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, bank, investment&lt;br&gt; | [optional] [readonly]
**debit_total** | [**\OpenAPI\Client\Model\Money**](Money.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
