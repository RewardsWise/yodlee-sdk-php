# # CreateConsent

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data_access_frequency** | **string** | Data Access Frequency explains the number of times that this consent can be used.&lt;br&gt; Otherwise called as consent frequency type. | [optional]
**otsp_adr_name** | **string** | Name of the Accredited Data Recipient/Organization | [optional]
**expiration_date_time** | **string** | Consent expiry datetime. |
**preferences** | [**\OpenAPI\Client\Model\Preferences[]**](Preferences.md) | Preferences describes options about the additional usage of data or purge data |
**otsp_adr** | **string** | Unique/Accredition Id of the ADR | [optional]
**client_adr** | **string** | Client Name of the ADR |
**renewal** | [**\OpenAPI\Client\Model\Renewal**](Renewal.md) |  | [optional]
**client_trusted_advisor** | [**\OpenAPI\Client\Model\ClientTrustedAdvisor[]**](ClientTrustedAdvisor.md) | describes information of client trusted advisor | [optional]
**revoke_date_time** | **string** | Consent revoke datetime. |
**provider_consent_id** | **string** | Provider consent id | [optional]
**revoke_date** | **string** | Consent revoke date. |
**title** | **string** | Title for the consent form. |
**application_display_name** | **string** | Application display name. |
**title_body** | **string** | Description for the title. |
**consent_id** | **int** | Consent Id generated through POST Consent. |
**start_date_time** | **string** | Consent start datetime. |
**custom_display_data** | [**\OpenAPI\Client\Model\CustomDisplayData**](CustomDisplayData.md) |  | [optional]
**third_party_adr** | [**\OpenAPI\Client\Model\ThirdPartyADR[]**](ThirdPartyADR.md) | ThirdPartyADR describes details of additional parties which are accredited data recipients under organization | [optional]
**provider_id** | **int** | Provider Id for which the consent needs to be generated. |
**consent_status** | **string** | Status of the consent. |
**scope** | [**\OpenAPI\Client\Model\Scope[]**](Scope.md) | Scope describes about the consent permissions and their purpose. |
**links** | [**\OpenAPI\Client\Model\Links[]**](Links.md) | GET consent preferences API details |
**start_date** | **string** | Consent start date. |
**expiration_date** | **string** | Consent expiry date. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
