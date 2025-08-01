# # UptimeMetrics

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**threshold_percentage** | **string** | Value is calculated based on number of site failures and the total successful refreshes performed.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;GET providers/{providerId}&lt;/li&gt;&lt;li&gt;GET providers&lt;/li&gt;&lt;/ul&gt; | [optional] [readonly]
**status** | **string** | Indicates the alert status for the site. ACCOUNT_LINKING_UNAVAILABLE: If the thresholdPercentage value is &gt;&#x3D; 100. REFRESH_FAILURE_ATTENTION: If the thresholdPercentage value is &gt;&#x3D; 90 and &lt; 100.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;GET providers/{providerId}&lt;/li&gt;&lt;li&gt;GET providers&lt;/li&gt;&lt;/ul&gt; | [optional] [readonly]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
