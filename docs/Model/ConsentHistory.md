# # ConsentHistory

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**event_date_time** | **string** | History logged datetime. |
**expiration_date_time** | **string** | Consent expiry datetime where supported by the provider. | [optional]
**user_data_purge** | **int** | Applicable data deletion preference for consent as per AU OB onboarding model and user&#39;s &amp;quot;delete my data instead&amp;quot; option. This data point is applicable for AU Open Banking region only. | [optional]
**deidentification_preference** | **bool** | whether user has given consent to use deidentified data or not. This data point is applicable for AU Open Banking region only. Oauthpref id &#x3D; 4 | [optional]
**start_date_time** | **string** | Consent start datetime. |
**renewed_date_time** | **string** | Consent renewed datetime. | [optional]
**consent_status** | **string** | Status of the consent in each history event. Statuses will be shown as applicable for Open Banking regions. |
**revoked_date_time** | **string** | Revoked datetime for the consent if consent is revoked. | [optional]
**consent_collection_period** | **int** | Consent duration period selected by user for recurring consents during the new account addition or consent renewal. This data point is applicable for AU Open Banking region only. Oauthpref id &#x3D; 6 | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
