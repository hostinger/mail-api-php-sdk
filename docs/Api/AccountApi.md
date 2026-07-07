# Hostinger\AccountApi

All URIs are relative to https://api.mail.hostinger.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getCurrentAccount()**](AccountApi.md#getCurrentAccount) | **GET** /api/v1/me | Get the authenticated account |


## `getCurrentAccount()`

```php
getCurrentAccount(): \Hostinger\Model\V1MeResource
```

Get the authenticated account

Returns the authenticated account and the mailboxes it can manage.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\AccountApi(config: $config);

try {
    $result = $apiInstance->getCurrentAccount();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->getCurrentAccount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Hostinger\Model\V1MeResource**](../Model/V1MeResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
