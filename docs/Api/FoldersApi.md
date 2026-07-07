# Hostinger\FoldersApi

All URIs are relative to https://api.mail.hostinger.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createFolder()**](FoldersApi.md#createFolder) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders | Create folder |
| [**deleteFolder()**](FoldersApi.md#deleteFolder) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder} | Delete folder |
| [**listFolders()**](FoldersApi.md#listFolders) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders | List folders |
| [**updateFolder()**](FoldersApi.md#updateFolder) | **PUT** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder} | Update folder |


## `createFolder()`

```php
createFolder($mailboxResourceId, $v1FoldersCreateRequest): \Hostinger\Model\V1FoldersResource
```

Create folder

Create a new folder in the managed mailbox.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\FoldersApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$v1FoldersCreateRequest = new \Hostinger\Model\V1FoldersCreateRequest(); // \Hostinger\Model\V1FoldersCreateRequest

try {
    $result = $apiInstance->createFolder($mailboxResourceId, $v1FoldersCreateRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FoldersApi->createFolder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **v1FoldersCreateRequest** | [**\Hostinger\Model\V1FoldersCreateRequest**](../Model/V1FoldersCreateRequest.md)|  | |

### Return type

[**\Hostinger\Model\V1FoldersResource**](../Model/V1FoldersResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteFolder()`

```php
deleteFolder($mailboxResourceId, $folder)
```

Delete folder

Delete a folder and all of its subfolders.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\FoldersApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX.OldName; // string | Folder path to delete (URL-encoded).

try {
    $apiInstance->deleteFolder($mailboxResourceId, $folder);
} catch (Exception $e) {
    echo 'Exception when calling FoldersApi->deleteFolder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Folder path to delete (URL-encoded). | |

### Return type

void (empty response body)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listFolders()`

```php
listFolders($mailboxResourceId, $page, $perPage): \Hostinger\Model\V1FoldersCollection
```

List folders

Retrieve a paginated list of folders in the managed mailbox.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\FoldersApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$page = 1; // int | Page number (1-based).
$perPage = 25; // int | Items per page (max 100).

try {
    $result = $apiInstance->listFolders($mailboxResourceId, $page, $perPage);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FoldersApi->listFolders: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **page** | **int**| Page number (1-based). | [optional] [default to 1] |
| **perPage** | **int**| Items per page (max 100). | [optional] [default to 25] |

### Return type

[**\Hostinger\Model\V1FoldersCollection**](../Model/V1FoldersCollection.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateFolder()`

```php
updateFolder($mailboxResourceId, $folder, $v1FoldersUpdateRequest): \Hostinger\Model\V1FoldersResource
```

Update folder

Rename an existing folder.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\FoldersApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$folder = INBOX.OldName; // string | Current folder path (URL-encoded).
$v1FoldersUpdateRequest = new \Hostinger\Model\V1FoldersUpdateRequest(); // \Hostinger\Model\V1FoldersUpdateRequest

try {
    $result = $apiInstance->updateFolder($mailboxResourceId, $folder, $v1FoldersUpdateRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FoldersApi->updateFolder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **folder** | **string**| Current folder path (URL-encoded). | |
| **v1FoldersUpdateRequest** | [**\Hostinger\Model\V1FoldersUpdateRequest**](../Model/V1FoldersUpdateRequest.md)|  | |

### Return type

[**\Hostinger\Model\V1FoldersResource**](../Model/V1FoldersResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
