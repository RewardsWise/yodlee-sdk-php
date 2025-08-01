# # VerifiedAccountResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**request_id** | **string** | The unique identifier for the verification request that returns contextual data | [optional] [readonly]
**request_date** | **string** | The date of the verification request | [optional] [readonly]
**state** | **string** | The overall status of the verification request | [optional] [readonly]
**verified_account** | [**\OpenAPI\Client\Model\VerifiedAccounts[]**](VerifiedAccounts.md) |  | [optional] [readonly]
**failed_reason** | **string** | The reason for the failure of the verification request | [optional] [readonly]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
