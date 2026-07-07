# Hostinger\SendApi

All URIs are relative to https://api.mail.hostinger.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**sendEmail()**](SendApi.md#sendEmail) | **POST** /api/v1/mailboxes/{mailboxResourceId}/send | Send email |


## `sendEmail()`

```php
sendEmail($mailboxResourceId, $v1SendRequest)
```

Send email

Send a message from the managed mailbox. Saves a copy to INBOX.Sent.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\SendApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$v1SendRequest = new \Hostinger\Model\V1SendRequest(); // \Hostinger\Model\V1SendRequest

try {
    $apiInstance->sendEmail($mailboxResourceId, $v1SendRequest);
} catch (Exception $e) {
    echo 'Exception when calling SendApi->sendEmail: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **v1SendRequest** | [**\Hostinger\Model\V1SendRequest**](../Model/V1SendRequest.md)|  | |

### Return type

void (empty response body)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
