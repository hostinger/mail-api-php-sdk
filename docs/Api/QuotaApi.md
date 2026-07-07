# Hostinger\QuotaApi

All URIs are relative to https://api.mail.hostinger.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getQuota()**](QuotaApi.md#getQuota) | **GET** /api/v1/mailboxes/{mailboxResourceId}/quota | Get mailbox quota |


## `getQuota()`

```php
getQuota($mailboxResourceId): \Hostinger\Model\V1QuotaResource
```

Get mailbox quota

Retrieve storage and message quota usage for the managed mailbox.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\QuotaApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.

try {
    $result = $apiInstance->getQuota($mailboxResourceId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling QuotaApi->getQuota: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |

### Return type

[**\Hostinger\Model\V1QuotaResource**](../Model/V1QuotaResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
