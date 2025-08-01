# # UserDetail

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**preferences** | [**\OpenAPI\Client\Model\UserResponsePreferences**](UserResponsePreferences.md) |  | [optional]
**address** | [**\OpenAPI\Client\Model\UserAddress**](UserAddress.md) |  | [optional]
**phone_number** | **string** |  | [optional]
**login_name** | **string** | The login name of the user used for authentication.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST user/register&lt;/li&gt;&lt;li&gt;GET user&lt;/li&gt;&lt;/ul&gt; | [optional] [readonly]
**name** | [**\OpenAPI\Client\Model\Name**](Name.md) |  | [optional]
**id** | **int** | The unique identifier of a consumer/user in Yodlee system for whom the API services would be accessed for.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;POST user/samlLogin&lt;/li&gt;&lt;li&gt;POST user/register&lt;/li&gt;&lt;li&gt;GET user&lt;/li&gt;&lt;/ul&gt; | [optional] [readonly]
**role_type** | **string** |  | [optional]
**email** | **string** | The email address of the user.&lt;br&gt;&lt;br&gt;&lt;b&gt;Endpoints&lt;/b&gt;:&lt;ul&gt;&lt;li&gt;GET user&lt;/li&gt;&lt;/ul&gt; | [optional] [readonly]
**segment_name** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
