# # CreateConsentRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**provider_id** | **int** | Unique identifier for the provider site.(e.g., financial institution sites, biller sites, lender sites, etc.).&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST Consent&lt;/li&gt;&lt;/ul&gt; | [optional]
**business_user_detail** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\BusinessUserDetailForCreateConsent**](BusinessUserDetailForCreateConsent.md) |  | [optional]
**dataset** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\ProvidersDataset[]**](ProvidersDataset.md) | The name of the dataset attribute supported by the provider.If no dataset value is provided, the datasets that are configured for the customer will be considered.The configured dataset can be overridden by providing the dataset as an input.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST Consent&lt;/li&gt;&lt;/ul&gt; | [optional]
**application_name** | **string** | The name of the application.If no applicationName is provided in the input, the default applicationName will be considered&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST Consent&lt;/li&gt;&lt;/ul&gt; | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
