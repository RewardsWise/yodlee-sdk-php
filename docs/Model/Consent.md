# # Consent

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data_access_frequency** | **string** | Data Access Frequency explains the number of times that this consent can be used.&lt;br&gt; Otherwise called as consent frequency type. | [optional]
**expiration_date_time** | **string** | Consent expiry datetime. |
**otsp_adr** | **string** | Unique/Accredition Id of the ADR | [optional]
**business_user_detail** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\BusinessUserDetail**](BusinessUserDetail.md) |  | [optional]
**client_trusted_advisor** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\ClientTrustedAdvisor[]**](ClientTrustedAdvisor.md) | describes information of client trusted advisor | [optional]
**provider_consent_id** | **string** | Provider consent id | [optional]
**revoke_date** | **string** | Consent revoke date. |
**title** | **string** | Title for the consent form. |
**application_display_name** | **string** | Application display name. |
**consent_id** | **int** | Consent Id generated through POST Consent. |
**cdr_insights_disclosure** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\CDRInsightsDisclosure**](CDRInsightsDisclosure.md) |  | [optional]
**provider_id** | **int** | Provider Id for which the consent needs to be generated. |
**consent_status** | **string** | Status of the consent. |
**scope** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\Scope[]**](Scope.md) | Scope describes about the consent permissions and their purpose. |
**user_data_treatment** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\UserDataTreatment**](UserDataTreatment.md) |  | [optional]
**links** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\Links[]**](Links.md) | GET consent preferences API details |
**expiration_date** | **string** | Consent expiry date. |
**otsp_adr_name** | **string** | Name of the Accredited Data Recipient/Organization | [optional]
**preferences** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\Preferences[]**](Preferences.md) | Preferences describes options about the additional usage of data or purge data |
**client_adr** | **string** | Client Name of the ADR |
**renewal** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\Renewal**](Renewal.md) |  | [optional]
**revoke_date_time** | **string** | Consent revoke datetime. |
**title_body** | **string** | Description for the title. |
**start_date_time** | **string** | Consent start datetime. |
**third_party_adr** | [**\RewardsWise\Yodlee\OpenAPI\Client\Model\ThirdPartyADR[]**](ThirdPartyADR.md) | ThirdPartyADR describes details of additional parties which are accredited data recipients under organization | [optional]
**renewed_date_time** | **string** | Consent renewed datetime | [optional]
**provider_account_id** | **int** | Unique identifier for the provider account resource. &lt;br&gt;This is created during account addition.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;GET providerAccounts&lt;/li&gt;&lt;/ul&gt; | [optional] [readonly]
**start_date** | **string** | Consent start date. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
