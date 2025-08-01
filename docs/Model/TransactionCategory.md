# # TransactionCategory

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**high_level_category_name** | **string** | The name of the high level category. A group of similar transaction categories are clubbed together to form a high-level category.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]
**default_high_level_category_name** | **string** | A attribute which will always hold the first value(initial name) of Yodlee defined highLevelCategoryName attribute.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]
**high_level_category_id** | **int** | The unique identifier of the high level category.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]
**business_category** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\BusinessCategory**](BusinessCategory.md) |  | [optional]
**detail_category** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\DetailCategory[]**](DetailCategory.md) | Entity that provides detail category attributes&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]
**id** | **int** | Unique identifier of the category.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]
**source** | **string** | Source used to identify whether the transaction category is user defined category or system created category.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt;&lt;b&gt;Applicable Values&lt;/b&gt;&lt;br&gt; | [optional] [readonly]
**category** | **string** | The name of the category.&lt;br&gt;&lt;b&gt;Note&lt;/b&gt;: Transaction categorization is one of the core features offered by Yodlee and the categories are assigned to the transactions by the system. Transactions can be clubbed together by the category that is assigned to them.  &lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]
**classification** | **string** | Category Classification.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt;&lt;b&gt;Applicable Values&lt;/b&gt;&lt;br&gt; | [optional] [readonly]
**type** | **string** | Transaction categories and high-level categories are further mapped to five transaction category types. Customers, based on their needs can either use the transaction categories, the high-level categories, or the transaction category types. &lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt;&lt;b&gt;Applicable Values&lt;/b&gt;&lt;br&gt; | [optional] [readonly]
**default_category_name** | **string** | A attribute which will always hold the first value(initial name) of Yodlee defined category attribute.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
