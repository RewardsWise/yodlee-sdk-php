# # DerivedHoldingsSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**holding** | [**\OpenAPI\Client\Model\DerivedHolding[]**](DerivedHolding.md) | Securities that belong to the asset classification type and contributed to the summary value.&lt;br&gt;&lt;b&gt;Required Feature Enablement&lt;/b&gt;: Asset classification feature.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: investment, insurance&lt;br&gt; | [optional] [readonly]
**classification_type** | **string** | The classification type of the security. The supported asset classification type and the values are provided in the /holdings/assetClassificationList.&lt;br&gt;&lt;b&gt;Required Feature Enablement&lt;/b&gt;: Asset classification feature.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: investment, insurance&lt;br&gt; | [optional] [readonly]
**classification_value** | **string** | The classification value that corresponds to the classification type of the holding. The supported asset classification type and the values are provided in the /holdings/assetClassificationList.&lt;br&gt;&lt;b&gt;Required Feature Enablement&lt;/b&gt;: Asset classification feature.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: investment, insurance&lt;br&gt; | [optional] [readonly]
**value** | [**\OpenAPI\Client\Model\Money**](Money.md) |  | [optional]
**account** | [**\OpenAPI\Client\Model\DerivedHoldingsAccount[]**](DerivedHoldingsAccount.md) | Accounts that contribute to the classification. &lt;br&gt;&lt;b&gt;Required Feature Enablement&lt;/b&gt;: Asset classification feature.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: investment, insurance&lt;br&gt; | [optional] [readonly]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
