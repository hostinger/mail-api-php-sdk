# Hostinger\WebhooksApi

All URIs are relative to https://api.mail.hostinger.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createWebhook()**](WebhooksApi.md#createWebhook) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks | Create webhook |
| [**deleteWebhook()**](WebhooksApi.md#deleteWebhook) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Delete webhook |
| [**getWebhook()**](WebhooksApi.md#getWebhook) | **GET** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Get webhook |
| [**listWebhooks()**](WebhooksApi.md#listWebhooks) | **GET** /api/v1/mailboxes/{mailboxResourceId}/webhooks | List webhooks |
| [**regenerateWebhookSecret()**](WebhooksApi.md#regenerateWebhookSecret) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook}/regenerate-secret | Regenerate webhook secret |
| [**testWebhook()**](WebhooksApi.md#testWebhook) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook}/test | Test webhook |
| [**updateWebhook()**](WebhooksApi.md#updateWebhook) | **PATCH** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Update webhook |


## `createWebhook()`

```php
createWebhook($mailboxResourceId, $v1WebhooksCreateRequest): \Hostinger\Model\V1WebhooksResourceWithSecret
```

Create webhook

Create a webhook. The response includes the one-time `secret` — store it securely as it is never returned again.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\WebhooksApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$v1WebhooksCreateRequest = new \Hostinger\Model\V1WebhooksCreateRequest(); // \Hostinger\Model\V1WebhooksCreateRequest

try {
    $result = $apiInstance->createWebhook($mailboxResourceId, $v1WebhooksCreateRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->createWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **v1WebhooksCreateRequest** | [**\Hostinger\Model\V1WebhooksCreateRequest**](../Model/V1WebhooksCreateRequest.md)|  | |

### Return type

[**\Hostinger\Model\V1WebhooksResourceWithSecret**](../Model/V1WebhooksResourceWithSecret.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteWebhook()`

```php
deleteWebhook($mailboxResourceId, $webhook)
```

Delete webhook

Delete a webhook.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\WebhooksApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox.
$webhook = 019683f8-1234-7abc-8def-0123456789ab; // string | Webhook identifier (UUID v7).

try {
    $apiInstance->deleteWebhook($mailboxResourceId, $webhook);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->deleteWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox. | |
| **webhook** | **string**| Webhook identifier (UUID v7). | |

### Return type

void (empty response body)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getWebhook()`

```php
getWebhook($mailboxResourceId, $webhook): \Hostinger\Model\V1WebhooksResource
```

Get webhook

Retrieve a single webhook by id.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\WebhooksApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox.
$webhook = 019683f8-1234-7abc-8def-0123456789ab; // string | Webhook identifier (UUID v7).

try {
    $result = $apiInstance->getWebhook($mailboxResourceId, $webhook);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->getWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox. | |
| **webhook** | **string**| Webhook identifier (UUID v7). | |

### Return type

[**\Hostinger\Model\V1WebhooksResource**](../Model/V1WebhooksResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listWebhooks()`

```php
listWebhooks($mailboxResourceId, $status, $page, $perPage): \Hostinger\Model\V1WebhooksCollection
```

List webhooks

List webhooks for a mailbox.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\WebhooksApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$status = 'status_example'; // string
$page = 1; // int
$perPage = 15; // int

try {
    $result = $apiInstance->listWebhooks($mailboxResourceId, $status, $page, $perPage);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->listWebhooks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **status** | **string**|  | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **perPage** | **int**|  | [optional] [default to 15] |

### Return type

[**\Hostinger\Model\V1WebhooksCollection**](../Model/V1WebhooksCollection.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `regenerateWebhookSecret()`

```php
regenerateWebhookSecret($mailboxResourceId, $webhook): \Hostinger\Model\V1WebhooksResourceWithSecret
```

Regenerate webhook secret

Regenerate the webhook secret. The previous secret is immediately invalidated. The new secret is returned once.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\WebhooksApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox.
$webhook = 019683f8-1234-7abc-8def-0123456789ab; // string | Webhook identifier (UUID v7).

try {
    $result = $apiInstance->regenerateWebhookSecret($mailboxResourceId, $webhook);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->regenerateWebhookSecret: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox. | |
| **webhook** | **string**| Webhook identifier (UUID v7). | |

### Return type

[**\Hostinger\Model\V1WebhooksResourceWithSecret**](../Model/V1WebhooksResourceWithSecret.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `testWebhook()`

```php
testWebhook($mailboxResourceId, $webhook): \Hostinger\Model\V1WebhooksTestResult
```

Test webhook

Send a test delivery to the webhook URL and return the upstream response.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\WebhooksApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox.
$webhook = 019683f8-1234-7abc-8def-0123456789ab; // string | Webhook identifier (UUID v7).

try {
    $result = $apiInstance->testWebhook($mailboxResourceId, $webhook);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->testWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox. | |
| **webhook** | **string**| Webhook identifier (UUID v7). | |

### Return type

[**\Hostinger\Model\V1WebhooksTestResult**](../Model/V1WebhooksTestResult.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateWebhook()`

```php
updateWebhook($mailboxResourceId, $webhook, $v1WebhooksUpdateRequest): \Hostinger\Model\V1WebhooksResource
```

Update webhook

Partially update a webhook.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\WebhooksApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox.
$webhook = 019683f8-1234-7abc-8def-0123456789ab; // string | Webhook identifier (UUID v7).
$v1WebhooksUpdateRequest = new \Hostinger\Model\V1WebhooksUpdateRequest(); // \Hostinger\Model\V1WebhooksUpdateRequest

try {
    $result = $apiInstance->updateWebhook($mailboxResourceId, $webhook, $v1WebhooksUpdateRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->updateWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox. | |
| **webhook** | **string**| Webhook identifier (UUID v7). | |
| **v1WebhooksUpdateRequest** | [**\Hostinger\Model\V1WebhooksUpdateRequest**](../Model/V1WebhooksUpdateRequest.md)|  | |

### Return type

[**\Hostinger\Model\V1WebhooksResource**](../Model/V1WebhooksResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
