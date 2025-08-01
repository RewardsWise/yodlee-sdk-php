# # Attribute

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**container** | **string[]** | Containers for which the attributes are supported.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;GET providers&lt;/li&gt;&lt;li&gt;GET providers/{providerId}&lt;/li&gt;&lt;/ul&gt; | [optional]
**from_date** | **string** | Applicable only to EBILLS and STATEMENTS attributes of DOCUMENT dataset.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST providerAccounts&lt;/li&gt;&lt;li&gt;PUT providerAccounts&lt;/li&gt;&lt;/ul&gt; | [optional] [readonly]
**to_fin_year** | **string** | Applicable only to TAX attribute of DOCUMENT dataset.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST providerAccounts&lt;/li&gt;&lt;li&gt;PUT providerAccounts&lt;/li&gt;&lt;/ul&gt; | [optional] [readonly]
**from_fin_year** | **string** | Applicable only to TAX attribute of DOCUMENT dataset.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST providerAccounts&lt;/li&gt;&lt;li&gt;PUT providerAccounts&lt;/li&gt;&lt;/ul&gt; | [optional] [readonly]
**container_attributes** | [**\OpenAPI\Client\Model\ContainerAttributes**](ContainerAttributes.md) |  | [optional]
**to_date** | **string** | Applicable only to EBILLS and STATEMENTS attributes of DOCUMENT dataset.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST providerAccounts&lt;/li&gt;&lt;li&gt;PUT providerAccounts&lt;/li&gt;&lt;/ul&gt; | [optional] [readonly]
**name** | **string** | Attributes that are supported for a dataset.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;GET providers&lt;/li&gt;&lt;li&gt;GET providers/{providerId}&lt;/li&gt;&lt;/ul&gt; | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
