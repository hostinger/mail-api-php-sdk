# Hostinger Mail API PHP SDK

## About
This is a PHP SDK for the Hostinger API. 

## Installation & Usage

### Requirements

PHP 8.1 and later.

### Composer

To install the package via [Composer](https://getcomposer.org/), run the following command:

```bash
composer require hostinger/mail-api-php-sdk
```

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    client: new GuzzleHttp\Client(),
    config: $config
);

try {
    $result = $apiInstance->getCurrentAccount();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->getCurrentAccount: ', $e->getMessage(), PHP_EOL;
}

```

## API Endpoints

All URIs are relative to *https://api.mail.hostinger.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccountApi* | [**getCurrentAccount**](docs/Api/AccountApi.md#getcurrentaccount) | **GET** /api/v1/me | Get the authenticated account
*FoldersApi* | [**createFolder**](docs/Api/FoldersApi.md#createfolder) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders | Create folder
*FoldersApi* | [**deleteFolder**](docs/Api/FoldersApi.md#deletefolder) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder} | Delete folder
*FoldersApi* | [**listFolders**](docs/Api/FoldersApi.md#listfolders) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders | List folders
*FoldersApi* | [**updateFolder**](docs/Api/FoldersApi.md#updatefolder) | **PUT** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder} | Update folder
*MessagesApi* | [**deleteAllMessages**](docs/Api/MessagesApi.md#deleteallmessages) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages | Delete all messages
*MessagesApi* | [**deleteMessage**](docs/Api/MessagesApi.md#deletemessage) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Delete message
*MessagesApi* | [**deleteMessages**](docs/Api/MessagesApi.md#deletemessages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/delete | Delete messages
*MessagesApi* | [**getMessage**](docs/Api/MessagesApi.md#getmessage) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Get message
*MessagesApi* | [**getMessageAttachment**](docs/Api/MessagesApi.md#getmessageattachment) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/attachments/{attachmentId} | Download message attachment
*MessagesApi* | [**getMessageSource**](docs/Api/MessagesApi.md#getmessagesource) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/source | Get message source
*MessagesApi* | [**getMessageText**](docs/Api/MessagesApi.md#getmessagetext) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/text | Get message text content
*MessagesApi* | [**listMessages**](docs/Api/MessagesApi.md#listmessages) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages | List messages
*MessagesApi* | [**moveMessage**](docs/Api/MessagesApi.md#movemessage) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/move | Move message
*MessagesApi* | [**moveMessages**](docs/Api/MessagesApi.md#movemessages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/move | Move messages
*MessagesApi* | [**patchMessage**](docs/Api/MessagesApi.md#patchmessage) | **PATCH** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Update message flags
*MessagesApi* | [**searchMessages**](docs/Api/MessagesApi.md#searchmessages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/search | Search messages
*MessagesApi* | [**updateMessageFlags**](docs/Api/MessagesApi.md#updatemessageflags) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/flags | Update message flags
*QuotaApi* | [**getQuota**](docs/Api/QuotaApi.md#getquota) | **GET** /api/v1/mailboxes/{mailboxResourceId}/quota | Get mailbox quota
*SendApi* | [**sendEmail**](docs/Api/SendApi.md#sendemail) | **POST** /api/v1/mailboxes/{mailboxResourceId}/send | Send email
*WebhooksApi* | [**createWebhook**](docs/Api/WebhooksApi.md#createwebhook) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks | Create webhook
*WebhooksApi* | [**deleteWebhook**](docs/Api/WebhooksApi.md#deletewebhook) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Delete webhook
*WebhooksApi* | [**getWebhook**](docs/Api/WebhooksApi.md#getwebhook) | **GET** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Get webhook
*WebhooksApi* | [**listWebhooks**](docs/Api/WebhooksApi.md#listwebhooks) | **GET** /api/v1/mailboxes/{mailboxResourceId}/webhooks | List webhooks
*WebhooksApi* | [**regenerateWebhookSecret**](docs/Api/WebhooksApi.md#regeneratewebhooksecret) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook}/regenerate-secret | Regenerate webhook secret
*WebhooksApi* | [**testWebhook**](docs/Api/WebhooksApi.md#testwebhook) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook}/test | Test webhook
*WebhooksApi* | [**updateWebhook**](docs/Api/WebhooksApi.md#updatewebhook) | **PATCH** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Update webhook

## Models

- [Error](docs/Model/Error.md)
- [Pagination](docs/Model/Pagination.md)
- [V1FolderMessagesCollection](docs/Model/V1FolderMessagesCollection.md)
- [V1FolderMessagesDeleteBulkRequest](docs/Model/V1FolderMessagesDeleteBulkRequest.md)
- [V1FolderMessagesFlagsBulkRequest](docs/Model/V1FolderMessagesFlagsBulkRequest.md)
- [V1FolderMessagesFlagsRequest](docs/Model/V1FolderMessagesFlagsRequest.md)
- [V1FolderMessagesMessage](docs/Model/V1FolderMessagesMessage.md)
- [V1FolderMessagesMessageAddress](docs/Model/V1FolderMessagesMessageAddress.md)
- [V1FolderMessagesMessageAttachment](docs/Model/V1FolderMessagesMessageAttachment.md)
- [V1FolderMessagesMessageText](docs/Model/V1FolderMessagesMessageText.md)
- [V1FolderMessagesMessageTextResource](docs/Model/V1FolderMessagesMessageTextResource.md)
- [V1FolderMessagesMoveBulkRequest](docs/Model/V1FolderMessagesMoveBulkRequest.md)
- [V1FolderMessagesMoveRequest](docs/Model/V1FolderMessagesMoveRequest.md)
- [V1FolderMessagesResource](docs/Model/V1FolderMessagesResource.md)
- [V1FolderMessagesSearchRequest](docs/Model/V1FolderMessagesSearchRequest.md)
- [V1FolderMessagesUpdateFlagsResult](docs/Model/V1FolderMessagesUpdateFlagsResult.md)
- [V1FolderMessagesUpdateFlagsResultData](docs/Model/V1FolderMessagesUpdateFlagsResultData.md)
- [V1FolderMessagesUpdateFlagsResultDataFailedInner](docs/Model/V1FolderMessagesUpdateFlagsResultDataFailedInner.md)
- [V1FoldersCollection](docs/Model/V1FoldersCollection.md)
- [V1FoldersCreateRequest](docs/Model/V1FoldersCreateRequest.md)
- [V1FoldersFolder](docs/Model/V1FoldersFolder.md)
- [V1FoldersResource](docs/Model/V1FoldersResource.md)
- [V1FoldersUpdateRequest](docs/Model/V1FoldersUpdateRequest.md)
- [V1MeMailbox](docs/Model/V1MeMailbox.md)
- [V1MeResource](docs/Model/V1MeResource.md)
- [V1MeResourceData](docs/Model/V1MeResourceData.md)
- [V1QuotaQuota](docs/Model/V1QuotaQuota.md)
- [V1QuotaQuotaResource](docs/Model/V1QuotaQuotaResource.md)
- [V1QuotaResource](docs/Model/V1QuotaResource.md)
- [V1SendAttachment](docs/Model/V1SendAttachment.md)
- [V1SendMessageRef](docs/Model/V1SendMessageRef.md)
- [V1SendRequest](docs/Model/V1SendRequest.md)
- [V1WebhooksCollection](docs/Model/V1WebhooksCollection.md)
- [V1WebhooksCreateRequest](docs/Model/V1WebhooksCreateRequest.md)
- [V1WebhooksResource](docs/Model/V1WebhooksResource.md)
- [V1WebhooksResourceWithSecret](docs/Model/V1WebhooksResourceWithSecret.md)
- [V1WebhooksTestResult](docs/Model/V1WebhooksTestResult.md)
- [V1WebhooksTestResultData](docs/Model/V1WebhooksTestResultData.md)
- [V1WebhooksUpdateRequest](docs/Model/V1WebhooksUpdateRequest.md)
- [V1WebhooksWebhook](docs/Model/V1WebhooksWebhook.md)
- [V1WebhooksWebhookWithSecret](docs/Model/V1WebhooksWebhookWithSecret.md)
