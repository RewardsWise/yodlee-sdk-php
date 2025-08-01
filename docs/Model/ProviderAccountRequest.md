# # ProviderAccountRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**config_name** | **string** | The name of configuration created at the time onboarding or configuration creation. | [optional]
**consent_id** | **int** | Consent Id generated for the request through POST Consent.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST Provider Account&lt;/li&gt;&lt;li&gt;PUT Provider Account&lt;/li&gt;&lt;/ul&gt; | [optional]
**preferences** | [**\OpenAPI\Client\Model\ProviderAccountPreferences**](ProviderAccountPreferences.md) |  | [optional]
**aggregation_source** | **string** |  | [optional]
**field** | [**\OpenAPI\Client\Model\Field[]**](Field.md) |  |
**dataset_name** | **string[]** |  | [optional]
**dataset** | [**\OpenAPI\Client\Model\ProvidersDataset[]**](ProvidersDataset.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
