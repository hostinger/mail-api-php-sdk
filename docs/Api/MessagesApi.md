# Hostinger\MessagesApi

All URIs are relative to https://api.mail.hostinger.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteAllMessages()**](MessagesApi.md#deleteAllMessages) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages | Delete all messages |
| [**deleteMessage()**](MessagesApi.md#deleteMessage) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Delete message |
| [**deleteMessages()**](MessagesApi.md#deleteMessages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/delete | Delete messages |
| [**getMessage()**](MessagesApi.md#getMessage) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Get message |
| [**getMessageAttachment()**](MessagesApi.md#getMessageAttachment) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/attachments/{attachmentId} | Download message attachment |
| [**getMessageSource()**](MessagesApi.md#getMessageSource) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/source | Get message source |
| [**getMessageText()**](MessagesApi.md#getMessageText) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/text | Get message text content |
| [**listMessages()**](MessagesApi.md#listMessages) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages | List messages |
| [**moveMessage()**](MessagesApi.md#moveMessage) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/move | Move message |
| [**moveMessages()**](MessagesApi.md#moveMessages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/move | Move messages |
| [**patchMessage()**](MessagesApi.md#patchMessage) | **PATCH** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Update message flags |
| [**searchMessages()**](MessagesApi.md#searchMessages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/search | Search messages |
| [**updateMessageFlags()**](MessagesApi.md#updateMessageFlags) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/flags | Update message flags |


## `deleteAllMessages()`

```php
deleteAllMessages($mailboxResourceId, $folder)
```

Delete all messages

Permanently delete every message in a folder (empty the folder).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\MessagesApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX.Trash; // string | Folder path (URL-encoded).

try {
    $apiInstance->deleteAllMessages($mailboxResourceId, $folder);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->deleteAllMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Folder path (URL-encoded). | |

### Return type

void (empty response body)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteMessage()`

```php
deleteMessage($mailboxResourceId, $folder, $uid)
```

Delete message

Permanently delete a single message.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\MessagesApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX; // string | Folder path (URL-encoded).
$uid = 42; // int | Message UID.

try {
    $apiInstance->deleteMessage($mailboxResourceId, $folder, $uid);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->deleteMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Folder path (URL-encoded). | |
| **uid** | **int**| Message UID. | |

### Return type

void (empty response body)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteMessages()`

```php
deleteMessages($mailboxResourceId, $folder, $v1FolderMessagesDeleteBulkRequest)
```

Delete messages

Permanently delete multiple messages from a folder.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\MessagesApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX; // string | Folder path (URL-encoded).
$v1FolderMessagesDeleteBulkRequest = new \Hostinger\Model\V1FolderMessagesDeleteBulkRequest(); // \Hostinger\Model\V1FolderMessagesDeleteBulkRequest

try {
    $apiInstance->deleteMessages($mailboxResourceId, $folder, $v1FolderMessagesDeleteBulkRequest);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->deleteMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Folder path (URL-encoded). | |
| **v1FolderMessagesDeleteBulkRequest** | [**\Hostinger\Model\V1FolderMessagesDeleteBulkRequest**](../Model/V1FolderMessagesDeleteBulkRequest.md)|  | |

### Return type

void (empty response body)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getMessage()`

```php
getMessage($mailboxResourceId, $folder, $uid): \Hostinger\Model\V1FolderMessagesResource
```

Get message

Retrieve a single message by UID.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\MessagesApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX; // string | Folder path (URL-encoded).
$uid = 42; // int | Message UID.

try {
    $result = $apiInstance->getMessage($mailboxResourceId, $folder, $uid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->getMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Folder path (URL-encoded). | |
| **uid** | **int**| Message UID. | |

### Return type

[**\Hostinger\Model\V1FolderMessagesResource**](../Model/V1FolderMessagesResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getMessageAttachment()`

```php
getMessageAttachment($mailboxResourceId, $folder, $uid, $attachmentId): \SplFileObject
```

Download message attachment

Download a message attachment as `application/octet-stream`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\MessagesApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX; // string | Folder path (URL-encoded).
$uid = 42; // int | Message UID.
$attachmentId = YXR0YWNobWVudDpJTkJPWDoxMjM6MS4y; // string | Attachment ID (opaque, returned by GET message).

try {
    $result = $apiInstance->getMessageAttachment($mailboxResourceId, $folder, $uid, $attachmentId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->getMessageAttachment: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Folder path (URL-encoded). | |
| **uid** | **int**| Message UID. | |
| **attachmentId** | **string**| Attachment ID (opaque, returned by GET message). | |

### Return type

**\SplFileObject**

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getMessageSource()`

```php
getMessageSource($mailboxResourceId, $folder, $uid): \SplFileObject
```

Get message source

Retrieve raw RFC822 source of a message as `message/rfc822` attachment.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\MessagesApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX; // string | Folder path (URL-encoded).
$uid = 42; // int | Message UID.

try {
    $result = $apiInstance->getMessageSource($mailboxResourceId, $folder, $uid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->getMessageSource: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Folder path (URL-encoded). | |
| **uid** | **int**| Message UID. | |

### Return type

**\SplFileObject**

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getMessageText()`

```php
getMessageText($mailboxResourceId, $folder, $uid): \Hostinger\Model\V1FolderMessagesMessageTextResource
```

Get message text content

Retrieve rendered text (plain + HTML) of a message. Marks message as `\\Seen`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\MessagesApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX; // string | Folder path (URL-encoded).
$uid = 42; // int | Message UID.

try {
    $result = $apiInstance->getMessageText($mailboxResourceId, $folder, $uid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->getMessageText: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Folder path (URL-encoded). | |
| **uid** | **int**| Message UID. | |

### Return type

[**\Hostinger\Model\V1FolderMessagesMessageTextResource**](../Model/V1FolderMessagesMessageTextResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listMessages()`

```php
listMessages($mailboxResourceId, $folder, $page, $perPage, $sort): \Hostinger\Model\V1FolderMessagesCollection
```

List messages

List messages in a folder. Use POST /search for filtering. Sort fields: uid, date, size (prefix with `-` for descending). Default `-uid`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\MessagesApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX; // string | Folder path (URL-encoded).
$page = 1; // int | Page number (1-based).
$perPage = 25; // int | Items per page (max 100).
$sort = '-uid'; // string | Sort field with optional `-` prefix for descending. Allowed: uid, date, size.

try {
    $result = $apiInstance->listMessages($mailboxResourceId, $folder, $page, $perPage, $sort);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->listMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Folder path (URL-encoded). | |
| **page** | **int**| Page number (1-based). | [optional] [default to 1] |
| **perPage** | **int**| Items per page (max 100). | [optional] [default to 25] |
| **sort** | **string**| Sort field with optional &#x60;-&#x60; prefix for descending. Allowed: uid, date, size. | [optional] [default to &#39;-uid&#39;] |

### Return type

[**\Hostinger\Model\V1FolderMessagesCollection**](../Model/V1FolderMessagesCollection.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `moveMessage()`

```php
moveMessage($mailboxResourceId, $folder, $uid, $v1FolderMessagesMoveRequest)
```

Move message

Move a single message to a target folder.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\MessagesApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX; // string | Source folder path (URL-encoded).
$uid = 42; // int | Message UID.
$v1FolderMessagesMoveRequest = new \Hostinger\Model\V1FolderMessagesMoveRequest(); // \Hostinger\Model\V1FolderMessagesMoveRequest

try {
    $apiInstance->moveMessage($mailboxResourceId, $folder, $uid, $v1FolderMessagesMoveRequest);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->moveMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Source folder path (URL-encoded). | |
| **uid** | **int**| Message UID. | |
| **v1FolderMessagesMoveRequest** | [**\Hostinger\Model\V1FolderMessagesMoveRequest**](../Model/V1FolderMessagesMoveRequest.md)|  | |

### Return type

void (empty response body)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `moveMessages()`

```php
moveMessages($mailboxResourceId, $folder, $v1FolderMessagesMoveBulkRequest)
```

Move messages

Move multiple messages from a source folder to a target folder.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\MessagesApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX; // string | Source folder path (URL-encoded).
$v1FolderMessagesMoveBulkRequest = new \Hostinger\Model\V1FolderMessagesMoveBulkRequest(); // \Hostinger\Model\V1FolderMessagesMoveBulkRequest

try {
    $apiInstance->moveMessages($mailboxResourceId, $folder, $v1FolderMessagesMoveBulkRequest);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->moveMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Source folder path (URL-encoded). | |
| **v1FolderMessagesMoveBulkRequest** | [**\Hostinger\Model\V1FolderMessagesMoveBulkRequest**](../Model/V1FolderMessagesMoveBulkRequest.md)|  | |

### Return type

void (empty response body)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `patchMessage()`

```php
patchMessage($mailboxResourceId, $folder, $uid, $v1FolderMessagesFlagsRequest): \Hostinger\Model\V1FolderMessagesResource
```

Update message flags

Add and/or remove flags on a single message. Returns the updated message.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\MessagesApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX; // string | Folder path (URL-encoded).
$uid = 42; // int | Message UID.
$v1FolderMessagesFlagsRequest = new \Hostinger\Model\V1FolderMessagesFlagsRequest(); // \Hostinger\Model\V1FolderMessagesFlagsRequest

try {
    $result = $apiInstance->patchMessage($mailboxResourceId, $folder, $uid, $v1FolderMessagesFlagsRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->patchMessage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Folder path (URL-encoded). | |
| **uid** | **int**| Message UID. | |
| **v1FolderMessagesFlagsRequest** | [**\Hostinger\Model\V1FolderMessagesFlagsRequest**](../Model/V1FolderMessagesFlagsRequest.md)|  | |

### Return type

[**\Hostinger\Model\V1FolderMessagesResource**](../Model/V1FolderMessagesResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `searchMessages()`

```php
searchMessages($mailboxResourceId, $folder, $page, $perPage, $sort, $v1FolderMessagesSearchRequest): \Hostinger\Model\V1FolderMessagesCollection
```

Search messages

Search messages in a folder. Filters in body; pagination and sort via query (`page`, `perPage`, `sort`).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\MessagesApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX; // string | Folder path (URL-encoded).
$page = 1; // int
$perPage = 25; // int
$sort = '-uid'; // string
$v1FolderMessagesSearchRequest = new \Hostinger\Model\V1FolderMessagesSearchRequest(); // \Hostinger\Model\V1FolderMessagesSearchRequest

try {
    $result = $apiInstance->searchMessages($mailboxResourceId, $folder, $page, $perPage, $sort, $v1FolderMessagesSearchRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->searchMessages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Folder path (URL-encoded). | |
| **page** | **int**|  | [optional] [default to 1] |
| **perPage** | **int**|  | [optional] [default to 25] |
| **sort** | **string**|  | [optional] [default to &#39;-uid&#39;] |
| **v1FolderMessagesSearchRequest** | [**\Hostinger\Model\V1FolderMessagesSearchRequest**](../Model/V1FolderMessagesSearchRequest.md)|  | [optional] |

### Return type

[**\Hostinger\Model\V1FolderMessagesCollection**](../Model/V1FolderMessagesCollection.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateMessageFlags()`

```php
updateMessageFlags($mailboxResourceId, $folder, $v1FolderMessagesFlagsBulkRequest): \Hostinger\Model\V1FolderMessagesUpdateFlagsResult
```

Update message flags

Add and/or remove flags on multiple messages. Returns 200 when all UIDs succeed, 207 with per-UID outcome when some fail.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\MessagesApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX; // string | Folder path (URL-encoded).
$v1FolderMessagesFlagsBulkRequest = new \Hostinger\Model\V1FolderMessagesFlagsBulkRequest(); // \Hostinger\Model\V1FolderMessagesFlagsBulkRequest

try {
    $result = $apiInstance->updateMessageFlags($mailboxResourceId, $folder, $v1FolderMessagesFlagsBulkRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessagesApi->updateMessageFlags: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Folder path (URL-encoded). | |
| **v1FolderMessagesFlagsBulkRequest** | [**\Hostinger\Model\V1FolderMessagesFlagsBulkRequest**](../Model/V1FolderMessagesFlagsBulkRequest.md)|  | |

### Return type

[**\Hostinger\Model\V1FolderMessagesUpdateFlagsResult**](../Model/V1FolderMessagesUpdateFlagsResult.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
