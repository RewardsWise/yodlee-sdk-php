# # TransactionCategorizationRule

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**rule_clauses** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\RuleClause[]**](RuleClause.md) | Details of rules. &lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]
**user_defined_rule_id** | **int** | Unique identifier generated for every rule the user creates.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]
**category_level_id** | **int** | The level of the category for which the rule is created.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, insurance, loan&lt;br&gt; | [optional] [readonly]
**transaction_categorisation_id** | **int** | Category id that is assigned to the transaction when the transaction matches the rule clause. This is the id field of the transaction category resource.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]
**mem_id** | **int** | Unique identifier of the user.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]
**rule_priority** | **int** | The order in which the rules get executed on transactions.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
