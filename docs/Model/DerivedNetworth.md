# # DerivedNetworth

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**date** | **string** | The date as of when the networth information is provided.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: bank, creditcard, investment, insurance, realEstate, loan&lt;br&gt; | [optional] [readonly]
**liability** | [**\OpenAPI\Client\Model\Money**](Money.md) |  | [optional]
**historical_balances** | [**\OpenAPI\Client\Model\DerivedNetworthHistoricalBalance[]**](DerivedNetworthHistoricalBalance.md) | Balances of the accounts over the period of time.&lt;br&gt;&lt;br&gt;&lt;b&gt;Applicable containers&lt;/b&gt;: bank, creditcard, investment, insurance, realEstate, loan&lt;br&gt; | [optional] [readonly]
**networth** | [**\OpenAPI\Client\Model\Money**](Money.md) |  | [optional]
**asset** | [**\OpenAPI\Client\Model\Money**](Money.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
