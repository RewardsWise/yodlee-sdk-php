# # RuleClause

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**field** | **string** | Field for which the clause is created.&lt;br&gt;&lt;br&gt;&lt;br&gt;&lt;b&gt;Valid Values&lt;/b&gt;:amount,description&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]
**user_defined_rule_id** | **int** | Unique identifier generated for every rule the user creates.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]
**field_value** | **string** | The value would be the amount value in case of amount based rule clause or the string value in case of description based rule clause.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]
**operation** | **string** | Operation for which the clause is created.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]
**rule_clause_id** | **int** | Unique identifier generated for the rule clause.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: creditCard, investment, insurance, loan&lt;br&gt; | [optional] [readonly]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
