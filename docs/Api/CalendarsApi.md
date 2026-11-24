# Hostinger\CalendarsApi

All URIs are relative to https://api.mail.hostinger.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createCalendar()**](CalendarsApi.md#createCalendar) | **POST** /api/v1/mailboxes/{mailboxResourceId}/calendars | Create calendar |
| [**deleteCalendar()**](CalendarsApi.md#deleteCalendar) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid} | Delete calendar |
| [**getCalendar()**](CalendarsApi.md#getCalendar) | **GET** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid} | Get calendar |
| [**listCalendars()**](CalendarsApi.md#listCalendars) | **GET** /api/v1/mailboxes/{mailboxResourceId}/calendars | List calendars |
| [**updateCalendar()**](CalendarsApi.md#updateCalendar) | **PUT** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid} | Update calendar |


## `createCalendar()`

```php
createCalendar($mailboxResourceId, $v1CalendarsCreateRequest): \Hostinger\Model\V1CalendarsResource
```

Create calendar

Create a calendar owned by the mailbox. The number of calendars a mailbox can own is limited; when the limit is reached the request fails with `400` and code `ERR_CALENDAR_LIMIT_REACHED`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\CalendarsApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$v1CalendarsCreateRequest = new \Hostinger\Model\V1CalendarsCreateRequest(); // \Hostinger\Model\V1CalendarsCreateRequest

try {
    $result = $apiInstance->createCalendar($mailboxResourceId, $v1CalendarsCreateRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CalendarsApi->createCalendar: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **v1CalendarsCreateRequest** | [**\Hostinger\Model\V1CalendarsCreateRequest**](../Model/V1CalendarsCreateRequest.md)|  | |

### Return type

[**\Hostinger\Model\V1CalendarsResource**](../Model/V1CalendarsResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteCalendar()`

```php
deleteCalendar($mailboxResourceId, $calendarUuid)
```

Delete calendar

Delete a calendar owned by the mailbox together with all its events, or remove a calendar shared with the mailbox from its list. This cannot be undone. A calendar that cannot be deleted is rejected with `403` and code `ERR_CALENDAR_NOT_DELETABLE`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\CalendarsApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$calendarUuid = 42c370e3-48ae-4286-90c5-d952f28c67cc; // string | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.

try {
    $apiInstance->deleteCalendar($mailboxResourceId, $calendarUuid);
} catch (Exception $e) {
    echo 'Exception when calling CalendarsApi->deleteCalendar: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **calendarUuid** | **string**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | |

### Return type

void (empty response body)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getCalendar()`

```php
getCalendar($mailboxResourceId, $calendarUuid): \Hostinger\Model\V1CalendarsResource
```

Get calendar

Retrieve one calendar of a mailbox: its name, description, color, whether it is the default calendar and whether it is shown in the calendar view. It does not return events; use `listCalendarEvents` for those.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\CalendarsApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$calendarUuid = 42c370e3-48ae-4286-90c5-d952f28c67cc; // string | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.

try {
    $result = $apiInstance->getCalendar($mailboxResourceId, $calendarUuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CalendarsApi->getCalendar: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **calendarUuid** | **string**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | |

### Return type

[**\Hostinger\Model\V1CalendarsResource**](../Model/V1CalendarsResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listCalendars()`

```php
listCalendars($mailboxResourceId, $page, $perPage): \Hostinger\Model\V1CalendarsCollection
```

List calendars

List the calendars of a mailbox: its own calendars and the calendars shared with it, in display order. Call it first to get the `calendarUuid` every calendar event operation needs: the `uuid` of each calendar. The calendar with `default` true is where new events go unless another one is named. `visible` false means the calendar is hidden in the calendar view; its events still exist.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\CalendarsApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$page = 1; // int | Page number (1-based).
$perPage = 25; // int | Items per page (max 200).

try {
    $result = $apiInstance->listCalendars($mailboxResourceId, $page, $perPage);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CalendarsApi->listCalendars: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **page** | **int**| Page number (1-based). | [optional] [default to 1] |
| **perPage** | **int**| Items per page (max 200). | [optional] [default to 25] |

### Return type

[**\Hostinger\Model\V1CalendarsCollection**](../Model/V1CalendarsCollection.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateCalendar()`

```php
updateCalendar($mailboxResourceId, $calendarUuid, $v1CalendarsUpdateRequest): \Hostinger\Model\V1CalendarsResource
```

Update calendar

Update the name, description, color and visibility of a calendar. Name, description and color replace the stored values: an omitted `description` is cleared and an omitted `color` resets to the default color. An omitted `visible` keeps the current value.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\CalendarsApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$calendarUuid = 42c370e3-48ae-4286-90c5-d952f28c67cc; // string | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
$v1CalendarsUpdateRequest = new \Hostinger\Model\V1CalendarsUpdateRequest(); // \Hostinger\Model\V1CalendarsUpdateRequest

try {
    $result = $apiInstance->updateCalendar($mailboxResourceId, $calendarUuid, $v1CalendarsUpdateRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CalendarsApi->updateCalendar: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **calendarUuid** | **string**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | |
| **v1CalendarsUpdateRequest** | [**\Hostinger\Model\V1CalendarsUpdateRequest**](../Model/V1CalendarsUpdateRequest.md)|  | |

### Return type

[**\Hostinger\Model\V1CalendarsResource**](../Model/V1CalendarsResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
