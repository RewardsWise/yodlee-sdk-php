# OpenAPIClient-php

This file describes the Yodlee Platform APIs using the swagger notation. You can use this swagger file to generate client side SDKs to the Yodlee Platform APIs for many different programming languages. Yodlee API v1.1 - Overview</a>.<br><br>You will have to set the header before making the API call. The following headers apply to all the APIs:<ul><li>Authorization: This header holds the access token</li> <li> Api-Version: 1.1</li></ul><b>Note</b>: If there are any API-specific headers, they are mentioned explicitly in the respective API's description.


## Installation & Usage

### Requirements

PHP 8.1 and later.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/GIT_USER_ID/GIT_REPO_ID.git"
    }
  ],
  "require": {
    "GIT_USER_ID/GIT_REPO_ID": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/OpenAPIClient-php/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');




$apiInstance = new OpenAPI\Client\Api\AccountTokenApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$token_request = new \OpenAPI\Client\Model\PaymentProcessorTokenRequest(); // \OpenAPI\Client\Model\PaymentProcessorTokenRequest | account information

try {
    $result = $apiInstance->generatePaymentProcessorToken($token_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountTokenApi->generatePaymentProcessorToken: ', $e->getMessage(), PHP_EOL;
}

```

## API Endpoints

All URIs are relative to *http://localhost*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccountTokenApi* | [**generatePaymentProcessorToken**](docs/Api/AccountTokenApi.md#generatepaymentprocessortoken) | **POST** /paymentProcessor/token | Create Account Token
*AccountTokenApi* | [**revokePaymentProcessorToken**](docs/Api/AccountTokenApi.md#revokepaymentprocessortoken) | **DELETE** /paymentProcessor/token | Delete Account Token
*AccountsApi* | [**createManualAccount**](docs/Api/AccountsApi.md#createmanualaccount) | **POST** /accounts | Add Manual Account
*AccountsApi* | [**deleteAccount**](docs/Api/AccountsApi.md#deleteaccount) | **DELETE** /accounts/{accountId} | Delete Account
*AccountsApi* | [**evaluateAddress**](docs/Api/AccountsApi.md#evaluateaddress) | **POST** /accounts/evaluateAddress | Evaluate Address
*AccountsApi* | [**getAccount**](docs/Api/AccountsApi.md#getaccount) | **GET** /accounts/{accountId} | Get Account Details
*AccountsApi* | [**getAllAccounts**](docs/Api/AccountsApi.md#getallaccounts) | **GET** /accounts | Get Accounts
*AccountsApi* | [**getAssociatedAccounts**](docs/Api/AccountsApi.md#getassociatedaccounts) | **GET** /accounts/associatedAccounts/{providerAccountId} | Associated Accounts
*AccountsApi* | [**getHistoricalBalances**](docs/Api/AccountsApi.md#gethistoricalbalances) | **GET** /accounts/historicalBalances | Get Historical Balances
*AccountsApi* | [**getLatestBalances**](docs/Api/AccountsApi.md#getlatestbalances) | **GET** /accounts/latestBalances | Get Latest Balances
*AccountsApi* | [**migrateAccounts**](docs/Api/AccountsApi.md#migrateaccounts) | **PUT** /accounts/migrateAccounts/{providerAccountId} | Migrate Accounts
*AccountsApi* | [**updateAccount**](docs/Api/AccountsApi.md#updateaccount) | **PUT** /accounts/{accountId} | Update Account
*AuthApi* | [**deleteApiKey**](docs/Api/AuthApi.md#deleteapikey) | **DELETE** /auth/apiKey/{key} | Delete API Key
*AuthApi* | [**deleteToken**](docs/Api/AuthApi.md#deletetoken) | **DELETE** /auth/token | Delete Token
*AuthApi* | [**generateAccessToken**](docs/Api/AuthApi.md#generateaccesstoken) | **POST** /auth/token | Generate Access Token
*AuthApi* | [**generateApiKey**](docs/Api/AuthApi.md#generateapikey) | **POST** /auth/apiKey | Generate API Key
*AuthApi* | [**getApiKeys**](docs/Api/AuthApi.md#getapikeys) | **GET** /auth/apiKey | Get API Keys
*CobrandApi* | [**cobrandLogin**](docs/Api/CobrandApi.md#cobrandlogin) | **POST** /cobrand/login | Cobrand Login
*CobrandApi* | [**cobrandLogout**](docs/Api/CobrandApi.md#cobrandlogout) | **POST** /cobrand/logout | Cobrand Logout
*CobrandApi* | [**createSubscriptionEvent**](docs/Api/CobrandApi.md#createsubscriptionevent) | **POST** /cobrand/config/notifications/events/{eventName} | Subscribe Event
*CobrandApi* | [**deleteSubscribedEvent**](docs/Api/CobrandApi.md#deletesubscribedevent) | **DELETE** /cobrand/config/notifications/events/{eventName} | Delete Subscription
*CobrandApi* | [**getPublicKey**](docs/Api/CobrandApi.md#getpublickey) | **GET** /cobrand/publicKey | Get Public Key
*CobrandApi* | [**getSubscribedEvents**](docs/Api/CobrandApi.md#getsubscribedevents) | **GET** /cobrand/config/notifications/events | Get Subscribed Events
*CobrandApi* | [**updateSubscribedEvent**](docs/Api/CobrandApi.md#updatesubscribedevent) | **PUT** /cobrand/config/notifications/events/{eventName} | Update Subscription
*ConfigsApi* | [**createSubscriptionNotificationEvent**](docs/Api/ConfigsApi.md#createsubscriptionnotificationevent) | **POST** /configs/notifications/events/{eventName} | Subscribe For Notification Event
*ConfigsApi* | [**deleteSubscribedNotificationEvent**](docs/Api/ConfigsApi.md#deletesubscribednotificationevent) | **DELETE** /configs/notifications/events/{eventName} | Delete Notification Subscription
*ConfigsApi* | [**getPublicEncryptionKey**](docs/Api/ConfigsApi.md#getpublicencryptionkey) | **GET** /configs/publicKey | Get Public Key
*ConfigsApi* | [**getSubscribedNotificationEvents**](docs/Api/ConfigsApi.md#getsubscribednotificationevents) | **GET** /configs/notifications/events | Get Subscribed Notification Events
*ConfigsApi* | [**updateSubscribedNotificationEvent**](docs/Api/ConfigsApi.md#updatesubscribednotificationevent) | **PUT** /configs/notifications/events/{eventName} | Update Notification Subscription
*ConsentsApi* | [**createConsent**](docs/Api/ConsentsApi.md#createconsent) | **POST** /consents | Post Consent
*ConsentsApi* | [**getConsentDetails**](docs/Api/ConsentsApi.md#getconsentdetails) | **GET** /consents/{consentId} | Get Authorization Details
*ConsentsApi* | [**getConsentHistory**](docs/Api/ConsentsApi.md#getconsenthistory) | **GET** /consents/history | Get Consent History
*ConsentsApi* | [**getConsentHistoryCount**](docs/Api/ConsentsApi.md#getconsenthistorycount) | **GET** /consents/history/count | Get Consent History Count
*ConsentsApi* | [**getConsentPreferences**](docs/Api/ConsentsApi.md#getconsentpreferences) | **GET** /consents/preferences | Get Consents Preferences
*ConsentsApi* | [**getConsents**](docs/Api/ConsentsApi.md#getconsents) | **GET** /consents | Get Consents
*ConsentsApi* | [**renewConsent**](docs/Api/ConsentsApi.md#renewconsent) | **PUT** /consents/{consentId}/renewal | Renew Consent
*ConsentsApi* | [**updateConsent**](docs/Api/ConsentsApi.md#updateconsent) | **PUT** /consents/{consentId} | Put Consent
*DataExtractsApi* | [**getDataExtractsEvents**](docs/Api/DataExtractsApi.md#getdataextractsevents) | **GET** /dataExtracts/events | Get Events
*DataExtractsApi* | [**getDataExtractsUserData**](docs/Api/DataExtractsApi.md#getdataextractsuserdata) | **GET** /dataExtracts/userData | Get userData
*DerivedApi* | [**getHoldingSummary**](docs/Api/DerivedApi.md#getholdingsummary) | **GET** /derived/holdingSummary | Get Holding Summary
*DerivedApi* | [**getNetworth**](docs/Api/DerivedApi.md#getnetworth) | **GET** /derived/networth | Get Networth Summary
*DerivedApi* | [**getTransactionSummary**](docs/Api/DerivedApi.md#gettransactionsummary) | **GET** /derived/transactionSummary | Get Transaction Summary
*DocumentsApi* | [**deleteDocument**](docs/Api/DocumentsApi.md#deletedocument) | **DELETE** /documents/{documentId} | Delete Document
*DocumentsApi* | [**downloadDocument**](docs/Api/DocumentsApi.md#downloaddocument) | **GET** /documents/{documentId} | Download a Document
*DocumentsApi* | [**getDocuments**](docs/Api/DocumentsApi.md#getdocuments) | **GET** /documents | Get Documents
*HoldingsApi* | [**addHolding**](docs/Api/HoldingsApi.md#addholding) | **POST** /holdings | Add Holding
*HoldingsApi* | [**getAssetClassificationList**](docs/Api/HoldingsApi.md#getassetclassificationlist) | **GET** /holdings/assetClassificationList | Get Asset Classification List
*HoldingsApi* | [**getHoldingTypeList**](docs/Api/HoldingsApi.md#getholdingtypelist) | **GET** /holdings/holdingTypeList | Get Holding Type List
*HoldingsApi* | [**getHoldings**](docs/Api/HoldingsApi.md#getholdings) | **GET** /holdings | Get Holdings
*HoldingsApi* | [**getSecurities**](docs/Api/HoldingsApi.md#getsecurities) | **GET** /holdings/securities | Get Security Details
*InstitutionsApi* | [**getInstitutions**](docs/Api/InstitutionsApi.md#getinstitutions) | **GET** /institutions | Get institutions
*PaymentProcessorApi* | [**getVerifiedAccount**](docs/Api/PaymentProcessorApi.md#getverifiedaccount) | **GET** /partner/paymentProcessor/account | Get Account Details
*PaymentProcessorApi* | [**getVerifiedAccountBalance**](docs/Api/PaymentProcessorApi.md#getverifiedaccountbalance) | **GET** /partner/paymentProcessor/account/balance | Get Account Balance
*PaymentProcessorApi* | [**getVerifiedAccountHolder**](docs/Api/PaymentProcessorApi.md#getverifiedaccountholder) | **GET** /partner/paymentProcessor/account/holder | Get Account Holder Details
*ProviderAccountsApi* | [**deleteProviderAccount**](docs/Api/ProviderAccountsApi.md#deleteprovideraccount) | **DELETE** /providerAccounts/{providerAccountId} | Delete Provider Account
*ProviderAccountsApi* | [**editCredentialsOrRefreshProviderAccount**](docs/Api/ProviderAccountsApi.md#editcredentialsorrefreshprovideraccount) | **PUT** /providerAccounts | Update Account
*ProviderAccountsApi* | [**getAllProviderAccounts**](docs/Api/ProviderAccountsApi.md#getallprovideraccounts) | **GET** /providerAccounts | Get Provider Accounts
*ProviderAccountsApi* | [**getProviderAccount**](docs/Api/ProviderAccountsApi.md#getprovideraccount) | **GET** /providerAccounts/{providerAccountId} | Get Provider Account Details
*ProviderAccountsApi* | [**getProviderAccountProfiles**](docs/Api/ProviderAccountsApi.md#getprovideraccountprofiles) | **GET** /providerAccounts/profile | Get User Profile Details
*ProviderAccountsApi* | [**linkProviderAccount**](docs/Api/ProviderAccountsApi.md#linkprovideraccount) | **POST** /providerAccounts | Add Account
*ProviderAccountsApi* | [**refreshProviderAccount**](docs/Api/ProviderAccountsApi.md#refreshprovideraccount) | **PUT** /providerAccounts/refresh | Refresh Provider Account
*ProviderAccountsApi* | [**updatePreferences**](docs/Api/ProviderAccountsApi.md#updatepreferences) | **PUT** /providerAccounts/{providerAccountId}/preferences | Update Preferences
*ProvidersApi* | [**getAllProviders**](docs/Api/ProvidersApi.md#getallproviders) | **GET** /providers | Get Providers
*ProvidersApi* | [**getProvider**](docs/Api/ProvidersApi.md#getprovider) | **GET** /providers/{providerId} | Get Provider Details
*ProvidersApi* | [**getProvidersCount**](docs/Api/ProvidersApi.md#getproviderscount) | **GET** /providers/count | Get Providers Count
*StatementsApi* | [**getStatements**](docs/Api/StatementsApi.md#getstatements) | **GET** /statements | Get Statements
*TransactionsApi* | [**createOrRunTransactionCategorizationRules**](docs/Api/TransactionsApi.md#createorruntransactioncategorizationrules) | **POST** /transactions/categories/rules | Create or Run Transaction Categorization Rule
*TransactionsApi* | [**createTransactionCategory**](docs/Api/TransactionsApi.md#createtransactioncategory) | **POST** /transactions/categories | Create Category
*TransactionsApi* | [**deleteTransactionCategorizationRule**](docs/Api/TransactionsApi.md#deletetransactioncategorizationrule) | **DELETE** /transactions/categories/rules/{ruleId} | Delete Transaction Categorization Rule
*TransactionsApi* | [**deleteTransactionCategory**](docs/Api/TransactionsApi.md#deletetransactioncategory) | **DELETE** /transactions/categories/{categoryId} | Delete Category
*TransactionsApi* | [**getTransactionCategories**](docs/Api/TransactionsApi.md#gettransactioncategories) | **GET** /transactions/categories | Get Transaction Category List
*TransactionsApi* | [**getTransactionCategorizationRules**](docs/Api/TransactionsApi.md#gettransactioncategorizationrules) | **GET** /transactions/categories/txnRules | Get Transaction Categorization Rules
*TransactionsApi* | [**getTransactionCategorizationRulesDeprecated**](docs/Api/TransactionsApi.md#gettransactioncategorizationrulesdeprecated) | **GET** /transactions/categories/rules | Get Transaction Categorization Rules
*TransactionsApi* | [**getTransactions**](docs/Api/TransactionsApi.md#gettransactions) | **GET** /transactions | Get Transactions
*TransactionsApi* | [**getTransactionsCount**](docs/Api/TransactionsApi.md#gettransactionscount) | **GET** /transactions/count | Get Transactions Count
*TransactionsApi* | [**runTransactionCategorizationRule**](docs/Api/TransactionsApi.md#runtransactioncategorizationrule) | **POST** /transactions/categories/rules/{ruleId} | Run Transaction Categorization Rule
*TransactionsApi* | [**updateTransaction**](docs/Api/TransactionsApi.md#updatetransaction) | **PUT** /transactions | Update Transaction for Transaction Source ID
*TransactionsApi* | [**updateTransaction1**](docs/Api/TransactionsApi.md#updatetransaction1) | **PUT** /transactions/{transactionId} | Update Transaction
*TransactionsApi* | [**updateTransactionCategorizationRule**](docs/Api/TransactionsApi.md#updatetransactioncategorizationrule) | **PUT** /transactions/categories/rules/{ruleId} | Update Transaction Categorization Rule
*TransactionsApi* | [**updateTransactionCategory**](docs/Api/TransactionsApi.md#updatetransactioncategory) | **PUT** /transactions/categories | Update Category
*UserApi* | [**getAccessTokens**](docs/Api/UserApi.md#getaccesstokens) | **GET** /user/accessTokens | Get Access Tokens
*UserApi* | [**getUser**](docs/Api/UserApi.md#getuser) | **GET** /user | Get User Details
*UserApi* | [**registerUser**](docs/Api/UserApi.md#registeruser) | **POST** /user/register | Register User
*UserApi* | [**samlLogin**](docs/Api/UserApi.md#samllogin) | **POST** /user/samlLogin | Saml Login
*UserApi* | [**unregister**](docs/Api/UserApi.md#unregister) | **DELETE** /user/unregister | Delete User
*UserApi* | [**updateUser**](docs/Api/UserApi.md#updateuser) | **PUT** /user | Update User Details
*UserApi* | [**userLogout**](docs/Api/UserApi.md#userlogout) | **POST** /user/logout | User Logout
*UserDocumentsApi* | [**deleteuserdocuments**](docs/Api/UserDocumentsApi.md#deleteuserdocuments) | **DELETE** /documents | Delete User Documents
*UserDocumentsApi* | [**getuserdocuments**](docs/Api/UserDocumentsApi.md#getuserdocuments) | **POST** /documents/search | Get User Documents
*VerificationApi* | [**getClassificationSummary**](docs/Api/VerificationApi.md#getclassificationsummary) | **GET** /verification/classification/summary | Get Classification Summary
*VerificationApi* | [**getHolderProfile**](docs/Api/VerificationApi.md#getholderprofile) | **GET** /verification/holderProfile | Get Holder Profile
*VerificationApi* | [**getVerificationStatus**](docs/Api/VerificationApi.md#getverificationstatus) | **GET** /verification | Get Verification Status
*VerificationApi* | [**getVerifiedAccounts**](docs/Api/VerificationApi.md#getverifiedaccounts) | **GET** /verification/verifiedAccounts | Get Verified Accounts
*VerificationApi* | [**initiateMatchingOrChallengeDepositeVerification**](docs/Api/VerificationApi.md#initiatematchingorchallengedepositeverification) | **POST** /verification | Initiaite Challenge Deposit
*VerificationApi* | [**verifyChallengeDeposit**](docs/Api/VerificationApi.md#verifychallengedeposit) | **PUT** /verification | Verify Challenge Deposit
*VerifyAccountApi* | [**initiateAccountVerification**](docs/Api/VerifyAccountApi.md#initiateaccountverification) | **POST** /verifyAccount/{providerAccountId} | Verify Accounts Using Transactions

## Models

- [AbstractAddress](docs/Model/AbstractAddress.md)
- [AccessTokens](docs/Model/AccessTokens.md)
- [Account](docs/Model/Account.md)
- [AccountAddress](docs/Model/AccountAddress.md)
- [AccountBalanceResponse](docs/Model/AccountBalanceResponse.md)
- [AccountDataset](docs/Model/AccountDataset.md)
- [AccountHistoricalBalancesResponse](docs/Model/AccountHistoricalBalancesResponse.md)
- [AccountHistory](docs/Model/AccountHistory.md)
- [AccountHolder](docs/Model/AccountHolder.md)
- [AccountHolderData](docs/Model/AccountHolderData.md)
- [AccountLatestBalance](docs/Model/AccountLatestBalance.md)
- [AccountMigrationResponse](docs/Model/AccountMigrationResponse.md)
- [AccountProfile](docs/Model/AccountProfile.md)
- [AccountProfileDetail](docs/Model/AccountProfileDetail.md)
- [AccountResponse](docs/Model/AccountResponse.md)
- [AccountToken](docs/Model/AccountToken.md)
- [AddedProviderAccount](docs/Model/AddedProviderAccount.md)
- [AddedProviderAccountResponse](docs/Model/AddedProviderAccountResponse.md)
- [ApiKeyOutput](docs/Model/ApiKeyOutput.md)
- [ApiKeyRequest](docs/Model/ApiKeyRequest.md)
- [ApiKeyResponse](docs/Model/ApiKeyResponse.md)
- [AssetClassification](docs/Model/AssetClassification.md)
- [AssetClassificationList](docs/Model/AssetClassificationList.md)
- [AssociatedAccount](docs/Model/AssociatedAccount.md)
- [AssociatedAccountsResponse](docs/Model/AssociatedAccountsResponse.md)
- [Attribute](docs/Model/Attribute.md)
- [AutoRefresh](docs/Model/AutoRefresh.md)
- [BankTransferCode](docs/Model/BankTransferCode.md)
- [BusinessCategory](docs/Model/BusinessCategory.md)
- [BusinessInformation](docs/Model/BusinessInformation.md)
- [BusinessUserDetail](docs/Model/BusinessUserDetail.md)
- [BusinessUserDetailForCreateConsent](docs/Model/BusinessUserDetailForCreateConsent.md)
- [CDRInsights](docs/Model/CDRInsights.md)
- [CDRInsightsDisclosure](docs/Model/CDRInsightsDisclosure.md)
- [Capability](docs/Model/Capability.md)
- [CdrPolicy](docs/Model/CdrPolicy.md)
- [ClassificationSummaryAccountSummary](docs/Model/ClassificationSummaryAccountSummary.md)
- [ClassificationSummaryMerchant](docs/Model/ClassificationSummaryMerchant.md)
- [ClassificationSummaryResponse](docs/Model/ClassificationSummaryResponse.md)
- [ClassificationSummaryTransaction](docs/Model/ClassificationSummaryTransaction.md)
- [ClassificationSummaryTransactionSummary](docs/Model/ClassificationSummaryTransactionSummary.md)
- [ClientCredentialToken](docs/Model/ClientCredentialToken.md)
- [ClientCredentialTokenResponse](docs/Model/ClientCredentialTokenResponse.md)
- [ClientTrustedAdvisor](docs/Model/ClientTrustedAdvisor.md)
- [ClientTrustedAdvisorTxt](docs/Model/ClientTrustedAdvisorTxt.md)
- [Cobrand](docs/Model/Cobrand.md)
- [CobrandLoginRequest](docs/Model/CobrandLoginRequest.md)
- [CobrandLoginResponse](docs/Model/CobrandLoginResponse.md)
- [CobrandNotificationEvent](docs/Model/CobrandNotificationEvent.md)
- [CobrandNotificationResponse](docs/Model/CobrandNotificationResponse.md)
- [CobrandPublicKeyResponse](docs/Model/CobrandPublicKeyResponse.md)
- [CobrandSession](docs/Model/CobrandSession.md)
- [ConfigsNotificationEvent](docs/Model/ConfigsNotificationEvent.md)
- [ConfigsNotificationResponse](docs/Model/ConfigsNotificationResponse.md)
- [ConfigsPublicKey](docs/Model/ConfigsPublicKey.md)
- [ConfigsPublicKeyResponse](docs/Model/ConfigsPublicKeyResponse.md)
- [Consent](docs/Model/Consent.md)
- [ConsentConfirmation](docs/Model/ConsentConfirmation.md)
- [ConsentHistory](docs/Model/ConsentHistory.md)
- [ConsentHistoryCount](docs/Model/ConsentHistoryCount.md)
- [ConsentHistoryCountResponse](docs/Model/ConsentHistoryCountResponse.md)
- [ConsentHistoryResponse](docs/Model/ConsentHistoryResponse.md)
- [ConsentPreferencesResponse](docs/Model/ConsentPreferencesResponse.md)
- [ConsentResponse](docs/Model/ConsentResponse.md)
- [Contact](docs/Model/Contact.md)
- [ContainerAttributes](docs/Model/ContainerAttributes.md)
- [Coordinates](docs/Model/Coordinates.md)
- [Coverage](docs/Model/Coverage.md)
- [CoverageAmount](docs/Model/CoverageAmount.md)
- [CreateAccountInfo](docs/Model/CreateAccountInfo.md)
- [CreateAccountRequest](docs/Model/CreateAccountRequest.md)
- [CreateCobrandNotificationEvent](docs/Model/CreateCobrandNotificationEvent.md)
- [CreateCobrandNotificationEventRequest](docs/Model/CreateCobrandNotificationEventRequest.md)
- [CreateConfigsNotificationEvent](docs/Model/CreateConfigsNotificationEvent.md)
- [CreateConfigsNotificationEventRequest](docs/Model/CreateConfigsNotificationEventRequest.md)
- [CreateConsent](docs/Model/CreateConsent.md)
- [CreateConsentRequest](docs/Model/CreateConsentRequest.md)
- [CreatedAccountInfo](docs/Model/CreatedAccountInfo.md)
- [CreatedAccountResponse](docs/Model/CreatedAccountResponse.md)
- [CreatedConsentResponse](docs/Model/CreatedConsentResponse.md)
- [CustomDisplayData](docs/Model/CustomDisplayData.md)
- [DataExtractsAccount](docs/Model/DataExtractsAccount.md)
- [DataExtractsEvent](docs/Model/DataExtractsEvent.md)
- [DataExtractsEventData](docs/Model/DataExtractsEventData.md)
- [DataExtractsEventLinks](docs/Model/DataExtractsEventLinks.md)
- [DataExtractsEventResponse](docs/Model/DataExtractsEventResponse.md)
- [DataExtractsEventUserData](docs/Model/DataExtractsEventUserData.md)
- [DataExtractsHolding](docs/Model/DataExtractsHolding.md)
- [DataExtractsProviderAccount](docs/Model/DataExtractsProviderAccount.md)
- [DataExtractsTransaction](docs/Model/DataExtractsTransaction.md)
- [DataExtractsUser](docs/Model/DataExtractsUser.md)
- [DataExtractsUserData](docs/Model/DataExtractsUserData.md)
- [DataExtractsUserDataResponse](docs/Model/DataExtractsUserDataResponse.md)
- [DataHandling](docs/Model/DataHandling.md)
- [DeleteDocumentsRequest](docs/Model/DeleteDocumentsRequest.md)
- [DeletePreference](docs/Model/DeletePreference.md)
- [DerivedCategorySummary](docs/Model/DerivedCategorySummary.md)
- [DerivedCategorySummaryDetails](docs/Model/DerivedCategorySummaryDetails.md)
- [DerivedHolding](docs/Model/DerivedHolding.md)
- [DerivedHoldingSummaryResponse](docs/Model/DerivedHoldingSummaryResponse.md)
- [DerivedHoldingsAccount](docs/Model/DerivedHoldingsAccount.md)
- [DerivedHoldingsLinks](docs/Model/DerivedHoldingsLinks.md)
- [DerivedHoldingsSummary](docs/Model/DerivedHoldingsSummary.md)
- [DerivedNetworth](docs/Model/DerivedNetworth.md)
- [DerivedNetworthHistoricalBalance](docs/Model/DerivedNetworthHistoricalBalance.md)
- [DerivedNetworthResponse](docs/Model/DerivedNetworthResponse.md)
- [DerivedTransactionSummaryResponse](docs/Model/DerivedTransactionSummaryResponse.md)
- [DerivedTransactionsLinks](docs/Model/DerivedTransactionsLinks.md)
- [DerivedTransactionsSummary](docs/Model/DerivedTransactionsSummary.md)
- [Description](docs/Model/Description.md)
- [DetailCategory](docs/Model/DetailCategory.md)
- [Document](docs/Model/Document.md)
- [DocumentDownload](docs/Model/DocumentDownload.md)
- [DocumentDownloadResponse](docs/Model/DocumentDownloadResponse.md)
- [DocumentResponse](docs/Model/DocumentResponse.md)
- [Email](docs/Model/Email.md)
- [EvaluateAccountAddress](docs/Model/EvaluateAccountAddress.md)
- [EvaluateAddressRequest](docs/Model/EvaluateAddressRequest.md)
- [EvaluateAddressResponse](docs/Model/EvaluateAddressResponse.md)
- [Field](docs/Model/Field.md)
- [FieldOperation](docs/Model/FieldOperation.md)
- [FullAccountNumberList](docs/Model/FullAccountNumberList.md)
- [FullAccountNumbers](docs/Model/FullAccountNumbers.md)
- [GetDocumentsList](docs/Model/GetDocumentsList.md)
- [GetDocumentsRequest](docs/Model/GetDocumentsRequest.md)
- [GetDocumentsResponse](docs/Model/GetDocumentsResponse.md)
- [HistoricalBalance](docs/Model/HistoricalBalance.md)
- [HolderProfileResponse](docs/Model/HolderProfileResponse.md)
- [Holding](docs/Model/Holding.md)
- [HoldingAssetClassificationListResponse](docs/Model/HoldingAssetClassificationListResponse.md)
- [HoldingId](docs/Model/HoldingId.md)
- [HoldingIdListResponse](docs/Model/HoldingIdListResponse.md)
- [HoldingRequest](docs/Model/HoldingRequest.md)
- [HoldingRequestInfo](docs/Model/HoldingRequestInfo.md)
- [HoldingResponse](docs/Model/HoldingResponse.md)
- [HoldingSecuritiesResponse](docs/Model/HoldingSecuritiesResponse.md)
- [HoldingTypeListResponse](docs/Model/HoldingTypeListResponse.md)
- [Identifier](docs/Model/Identifier.md)
- [Institution](docs/Model/Institution.md)
- [InstitutionResponse](docs/Model/InstitutionResponse.md)
- [Links](docs/Model/Links.md)
- [LoanPayoffDetails](docs/Model/LoanPayoffDetails.md)
- [LoginForm](docs/Model/LoginForm.md)
- [LogoURLs](docs/Model/LogoURLs.md)
- [Merchant](docs/Model/Merchant.md)
- [Money](docs/Model/Money.md)
- [Name](docs/Model/Name.md)
- [Option](docs/Model/Option.md)
- [PaymentAccount](docs/Model/PaymentAccount.md)
- [PaymentAccountBalance](docs/Model/PaymentAccountBalance.md)
- [PaymentAccountBalanceResponse](docs/Model/PaymentAccountBalanceResponse.md)
- [PaymentAccountHolder](docs/Model/PaymentAccountHolder.md)
- [PaymentAccountHolderResponse](docs/Model/PaymentAccountHolderResponse.md)
- [PaymentAccountResponse](docs/Model/PaymentAccountResponse.md)
- [PaymentBankTransferCode](docs/Model/PaymentBankTransferCode.md)
- [PaymentBankTransferCodeData](docs/Model/PaymentBankTransferCodeData.md)
- [PaymentIdentifier](docs/Model/PaymentIdentifier.md)
- [PaymentProcessorTokenRequest](docs/Model/PaymentProcessorTokenRequest.md)
- [PaymentProcessorTokenResponse](docs/Model/PaymentProcessorTokenResponse.md)
- [PaymentProfile](docs/Model/PaymentProfile.md)
- [PhoneNumber](docs/Model/PhoneNumber.md)
- [Preferences](docs/Model/Preferences.md)
- [Profile](docs/Model/Profile.md)
- [ProviderAccount](docs/Model/ProviderAccount.md)
- [ProviderAccountDetail](docs/Model/ProviderAccountDetail.md)
- [ProviderAccountDetailResponse](docs/Model/ProviderAccountDetailResponse.md)
- [ProviderAccountPreferences](docs/Model/ProviderAccountPreferences.md)
- [ProviderAccountPreferencesRequest](docs/Model/ProviderAccountPreferencesRequest.md)
- [ProviderAccountProfile](docs/Model/ProviderAccountProfile.md)
- [ProviderAccountRefreshRequest](docs/Model/ProviderAccountRefreshRequest.md)
- [ProviderAccountRequest](docs/Model/ProviderAccountRequest.md)
- [ProviderAccountResponse](docs/Model/ProviderAccountResponse.md)
- [ProviderAccountUserProfileResponse](docs/Model/ProviderAccountUserProfileResponse.md)
- [ProviderDetail](docs/Model/ProviderDetail.md)
- [ProviderDetailResponse](docs/Model/ProviderDetailResponse.md)
- [ProviderResponse](docs/Model/ProviderResponse.md)
- [Providers](docs/Model/Providers.md)
- [ProvidersCount](docs/Model/ProvidersCount.md)
- [ProvidersCountResponse](docs/Model/ProvidersCountResponse.md)
- [ProvidersDataset](docs/Model/ProvidersDataset.md)
- [RefreshProviderAccountResponse](docs/Model/RefreshProviderAccountResponse.md)
- [RenewConsentPreferences](docs/Model/RenewConsentPreferences.md)
- [RenewConsentRequest](docs/Model/RenewConsentRequest.md)
- [RenewConsentResponse](docs/Model/RenewConsentResponse.md)
- [Renewal](docs/Model/Renewal.md)
- [RenewalConsent](docs/Model/RenewalConsent.md)
- [RewardBalance](docs/Model/RewardBalance.md)
- [Row](docs/Model/Row.md)
- [RuleClause](docs/Model/RuleClause.md)
- [Scope](docs/Model/Scope.md)
- [Security](docs/Model/Security.md)
- [SecurityHolding](docs/Model/SecurityHolding.md)
- [Statement](docs/Model/Statement.md)
- [StatementResponse](docs/Model/StatementResponse.md)
- [StatusLink](docs/Model/StatusLink.md)
- [StockExchangeDetail](docs/Model/StockExchangeDetail.md)
- [SuccessAssociations](docs/Model/SuccessAssociations.md)
- [ThirdParty](docs/Model/ThirdParty.md)
- [ThirdPartyADR](docs/Model/ThirdPartyADR.md)
- [TotalCount](docs/Model/TotalCount.md)
- [Transaction](docs/Model/Transaction.md)
- [TransactionCategorizationRule](docs/Model/TransactionCategorizationRule.md)
- [TransactionCategorizationRuleInfo](docs/Model/TransactionCategorizationRuleInfo.md)
- [TransactionCategorizationRuleRequest](docs/Model/TransactionCategorizationRuleRequest.md)
- [TransactionCategorizationRuleResponse](docs/Model/TransactionCategorizationRuleResponse.md)
- [TransactionCategory](docs/Model/TransactionCategory.md)
- [TransactionCategoryRequest](docs/Model/TransactionCategoryRequest.md)
- [TransactionCategoryResponse](docs/Model/TransactionCategoryResponse.md)
- [TransactionCount](docs/Model/TransactionCount.md)
- [TransactionCountResponse](docs/Model/TransactionCountResponse.md)
- [TransactionDays](docs/Model/TransactionDays.md)
- [TransactionRequest](docs/Model/TransactionRequest.md)
- [TransactionResponse](docs/Model/TransactionResponse.md)
- [TransactionTotal](docs/Model/TransactionTotal.md)
- [TransactionWithDateTime](docs/Model/TransactionWithDateTime.md)
- [UpdateAccountInfo](docs/Model/UpdateAccountInfo.md)
- [UpdateAccountRequest](docs/Model/UpdateAccountRequest.md)
- [UpdateCategoryRequest](docs/Model/UpdateCategoryRequest.md)
- [UpdateCobrandNotificationEvent](docs/Model/UpdateCobrandNotificationEvent.md)
- [UpdateCobrandNotificationEventRequest](docs/Model/UpdateCobrandNotificationEventRequest.md)
- [UpdateConfigsNotificationEvent](docs/Model/UpdateConfigsNotificationEvent.md)
- [UpdateConfigsNotificationEventRequest](docs/Model/UpdateConfigsNotificationEventRequest.md)
- [UpdateConsent](docs/Model/UpdateConsent.md)
- [UpdateConsentRequest](docs/Model/UpdateConsentRequest.md)
- [UpdateTransaction](docs/Model/UpdateTransaction.md)
- [UpdateUserRegistration](docs/Model/UpdateUserRegistration.md)
- [UpdateUserRequest](docs/Model/UpdateUserRequest.md)
- [UpdateVerification](docs/Model/UpdateVerification.md)
- [UpdateVerificationRequest](docs/Model/UpdateVerificationRequest.md)
- [UpdatedConsentResponse](docs/Model/UpdatedConsentResponse.md)
- [UpdatedProviderAccount](docs/Model/UpdatedProviderAccount.md)
- [UpdatedProviderAccountResponse](docs/Model/UpdatedProviderAccountResponse.md)
- [UptimeMetrics](docs/Model/UptimeMetrics.md)
- [User](docs/Model/User.md)
- [UserAccessToken](docs/Model/UserAccessToken.md)
- [UserAccessTokensResponse](docs/Model/UserAccessTokensResponse.md)
- [UserAddress](docs/Model/UserAddress.md)
- [UserDataTreatment](docs/Model/UserDataTreatment.md)
- [UserDetail](docs/Model/UserDetail.md)
- [UserDetailResponse](docs/Model/UserDetailResponse.md)
- [UserRegistration](docs/Model/UserRegistration.md)
- [UserRequest](docs/Model/UserRequest.md)
- [UserRequestPreferences](docs/Model/UserRequestPreferences.md)
- [UserResponse](docs/Model/UserResponse.md)
- [UserResponsePreferences](docs/Model/UserResponsePreferences.md)
- [UserSession](docs/Model/UserSession.md)
- [Verification](docs/Model/Verification.md)
- [VerificationAccount](docs/Model/VerificationAccount.md)
- [VerificationBankTransferCode](docs/Model/VerificationBankTransferCode.md)
- [VerificationHolder](docs/Model/VerificationHolder.md)
- [VerificationHolderProfile](docs/Model/VerificationHolderProfile.md)
- [VerificationRequest](docs/Model/VerificationRequest.md)
- [VerificationResponse](docs/Model/VerificationResponse.md)
- [VerificationStatus](docs/Model/VerificationStatus.md)
- [VerificationStatusResponse](docs/Model/VerificationStatusResponse.md)
- [VerificationTransaction](docs/Model/VerificationTransaction.md)
- [VerifiedAccount](docs/Model/VerifiedAccount.md)
- [VerifiedAccountResponse](docs/Model/VerifiedAccountResponse.md)
- [VerifiedAccounts](docs/Model/VerifiedAccounts.md)
- [VerifyAccount](docs/Model/VerifyAccount.md)
- [VerifyAccountRequest](docs/Model/VerifyAccountRequest.md)
- [VerifyAccountResponse](docs/Model/VerifyAccountResponse.md)
- [VerifyTransactionCriteria](docs/Model/VerifyTransactionCriteria.md)
- [YodleeError](docs/Model/YodleeError.md)

## Authorization
Endpoints do not require authorization.

## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```

## Author

developer@yodlee.com

## About this package

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `1.1.0`
    - Generator version: `7.13.0`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
