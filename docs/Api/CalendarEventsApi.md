# Hostinger\CalendarEventsApi

All URIs are relative to https://api.mail.hostinger.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createCalendarEvent()**](CalendarEventsApi.md#createCalendarEvent) | **POST** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events | Create calendar event |
| [**deleteCalendarEvent()**](CalendarEventsApi.md#deleteCalendarEvent) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid} | Delete calendar event |
| [**getCalendarEvent()**](CalendarEventsApi.md#getCalendarEvent) | **GET** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid} | Get calendar event |
| [**listCalendarEvents()**](CalendarEventsApi.md#listCalendarEvents) | **GET** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events | List calendar events |
| [**replyToCalendarEvent()**](CalendarEventsApi.md#replyToCalendarEvent) | **POST** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid}/reply | Reply to calendar event |
| [**rescheduleCalendarEvent()**](CalendarEventsApi.md#rescheduleCalendarEvent) | **PUT** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid}/reschedule | Reschedule calendar event |
| [**updateCalendarEvent()**](CalendarEventsApi.md#updateCalendarEvent) | **PUT** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid} | Update calendar event |


## `createCalendarEvent()`

```php
createCalendarEvent($mailboxResourceId, $calendarUuid, $v1CalendarEventsCreateRequest): \Hostinger\Model\V1CalendarEventsResource
```

Create calendar event

Create an event in one calendar of the mailbox. `calendarUuid` comes from `listCalendars`: use the calendar with `default` true unless another one is named. A calendar the mailbox can only read is rejected with `403` and code `ERR_EVENT_NOT_EDITABLE`. The mailbox becomes the organizer and every address in `attendees` immediately receives an email invitation, which cannot be recalled. Without attendees no email is sent. A timed event needs `allDay` false, `start`, `end` and `timeZone`. An all-day event needs `allDay` true and a `start` date; `end` is optional. Set `recurrenceRule` for a repeating event and `reminder` for an alarm. Returns the created event. Its `uuid` is the `eventUuid` for `getCalendarEvent`, `updateCalendarEvent`, `rescheduleCalendarEvent` and `deleteCalendarEvent`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\CalendarEventsApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$calendarUuid = 42c370e3-48ae-4286-90c5-d952f28c67cc; // string | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
$v1CalendarEventsCreateRequest = new \Hostinger\Model\V1CalendarEventsCreateRequest(); // \Hostinger\Model\V1CalendarEventsCreateRequest

try {
    $result = $apiInstance->createCalendarEvent($mailboxResourceId, $calendarUuid, $v1CalendarEventsCreateRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CalendarEventsApi->createCalendarEvent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **calendarUuid** | **string**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | |
| **v1CalendarEventsCreateRequest** | [**\Hostinger\Model\V1CalendarEventsCreateRequest**](../Model/V1CalendarEventsCreateRequest.md)|  | |

### Return type

[**\Hostinger\Model\V1CalendarEventsResource**](../Model/V1CalendarEventsResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteCalendarEvent()`

```php
deleteCalendarEvent($mailboxResourceId, $calendarUuid, $eventUuid, $scope, $recurrenceId, $notifyAttendees, $ifMatch)
```

Delete calendar event

Delete an event, one occurrence of a recurring event, or a recurring event from one occurrence on. This cannot be undone. `calendarUuid` and `eventUuid` come from `listCalendarEvents`. For a one-off event omit `scope` and `recurrenceId`. For a recurring event, `scope` `this` removes only the occurrence at `recurrenceId`, `future` removes it and every later one, `all` (the default) deletes the whole series. An event with `editable` true can be deleted with any scope, and its attendees receive a cancellation or the updated series by email. An invitation from someone else on the own calendar of the mailbox can be deleted with `all` or `this`: the organizer receives a decline for the removed occurrences. Any other event is rejected with `403` and code `ERR_EVENT_NOT_EDITABLE`. `notifyAttendees` false deletes without sending any email.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\CalendarEventsApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$calendarUuid = 42c370e3-48ae-4286-90c5-d952f28c67cc; // string | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
$eventUuid = a1b2c3d4-e5f6-7890-abcd-ef1234567890; // string | Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence.
$scope = this; // string | For a recurring event: `this` removes the occurrence at `recurrenceId`, `future` removes it and every later one, `all` deletes the whole series. Omitted means `all`. Required when `recurrenceId` is sent.
$recurrenceId = 2026-10-05T07:00:00.000000Z; // \DateTime | `recurrenceId` of one occurrence, copied unchanged from a `listCalendarEvents` item. Required when `scope` is `this` or `future`. A value that matches no occurrence, or any value on a one-off event, returns `404`.
$notifyAttendees = 'true'; // string | `false` deletes without emailing attendees a cancellation or update, or the organizer a decline. Omitted means `true`.
$ifMatch = 3c9f1a2b8e04; // string | Optional `etag` from `getCalendarEvent`. When the event changed since that call, nothing is deleted and the request fails with `412`: fetch the event again and retry. Omit it to apply the request to the current version.

try {
    $apiInstance->deleteCalendarEvent($mailboxResourceId, $calendarUuid, $eventUuid, $scope, $recurrenceId, $notifyAttendees, $ifMatch);
} catch (Exception $e) {
    echo 'Exception when calling CalendarEventsApi->deleteCalendarEvent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **calendarUuid** | **string**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | |
| **eventUuid** | **string**| Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | |
| **scope** | **string**| For a recurring event: &#x60;this&#x60; removes the occurrence at &#x60;recurrenceId&#x60;, &#x60;future&#x60; removes it and every later one, &#x60;all&#x60; deletes the whole series. Omitted means &#x60;all&#x60;. Required when &#x60;recurrenceId&#x60; is sent. | [optional] |
| **recurrenceId** | **\DateTime**| &#x60;recurrenceId&#x60; of one occurrence, copied unchanged from a &#x60;listCalendarEvents&#x60; item. Required when &#x60;scope&#x60; is &#x60;this&#x60; or &#x60;future&#x60;. A value that matches no occurrence, or any value on a one-off event, returns &#x60;404&#x60;. | [optional] |
| **notifyAttendees** | **string**| &#x60;false&#x60; deletes without emailing attendees a cancellation or update, or the organizer a decline. Omitted means &#x60;true&#x60;. | [optional] [default to &#39;true&#39;] |
| **ifMatch** | **string**| Optional &#x60;etag&#x60; from &#x60;getCalendarEvent&#x60;. When the event changed since that call, nothing is deleted and the request fails with &#x60;412&#x60;: fetch the event again and retry. Omit it to apply the request to the current version. | [optional] |

### Return type

void (empty response body)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getCalendarEvent()`

```php
getCalendarEvent($mailboxResourceId, $calendarUuid, $eventUuid, $recurrenceId): \Hostinger\Model\V1CalendarEventsResource
```

Get calendar event

Retrieve the full details of one event: title, times, description, location, meeting link, recurrence rule, reminder, organizer, attendees with their answers, and its `etag`. `calendarUuid` and `eventUuid` come from `listCalendarEvents` (the `calendarUuid` and `uuid` of an item). For one occurrence of a recurring event pass the `recurrenceId` of the item; without it the whole series is returned and `recurrenceId` is null. A `recurrenceId` that matches no occurrence returns `404`. Call it before `updateCalendarEvent`, which replaces every field, so the values that should stay can be sent back. `replyable` true means the mailbox was invited by someone else and can answer with `replyToCalendarEvent`. `editable` true means the event can be changed or moved.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\CalendarEventsApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$calendarUuid = 42c370e3-48ae-4286-90c5-d952f28c67cc; // string | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
$eventUuid = a1b2c3d4-e5f6-7890-abcd-ef1234567890; // string | Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence.
$recurrenceId = 2026-10-05T07:00:00.000000Z; // \DateTime | `recurrenceId` of one occurrence, copied unchanged from a `listCalendarEvents` item. Omit it for a one-off event or for the whole series.

try {
    $result = $apiInstance->getCalendarEvent($mailboxResourceId, $calendarUuid, $eventUuid, $recurrenceId);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CalendarEventsApi->getCalendarEvent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **calendarUuid** | **string**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | |
| **eventUuid** | **string**| Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | |
| **recurrenceId** | **\DateTime**| &#x60;recurrenceId&#x60; of one occurrence, copied unchanged from a &#x60;listCalendarEvents&#x60; item. Omit it for a one-off event or for the whole series. | [optional] |

### Return type

[**\Hostinger\Model\V1CalendarEventsResource**](../Model/V1CalendarEventsResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listCalendarEvents()`

```php
listCalendarEvents($mailboxResourceId, $calendarUuid, $start, $end, $timeZone): \Hostinger\Model\V1CalendarEventsCollection
```

List calendar events

List the events of one calendar that overlap a time range. It covers one calendar only: get the calendars from `listCalendars` and call it for each. The range runs from `start` (inclusive) to `end` (exclusive), at most 32 days; for a longer period call it again with the next range. Recurring events are expanded: each occurrence is a separate item with the same `uuid` and its own `recurrenceId`. Results are not paginated. Items hold summary fields only. For description, location, attendees and organizer call `getCalendarEvent` with the `calendarUuid`, `uuid` (as `eventUuid`) and `recurrenceId` of the item. Times are in UTC; `timeZone` is the zone the event was created in. `participationStatus` is the answer of the mailbox to an invitation from someone else, null for its own events. `status` CANCELLED means the organizer cancelled the event.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\CalendarEventsApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$calendarUuid = 42c370e3-48ae-4286-90c5-d952f28c67cc; // string | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
$start = 2026-09-28T00:00:00+03:00; // \DateTime | Start of the range, inclusive. ISO 8601 date-time with offset.
$end = 2026-10-05T00:00:00+03:00; // \DateTime | End of the range, exclusive. ISO 8601 date-time after `start` and at most 32 days after it.
$timeZone = Europe/Vilnius; // string | IANA time zone used to place all-day events and events without a time zone on days, also across a daylight saving change. Defaults to the fixed offset of `start`.

try {
    $result = $apiInstance->listCalendarEvents($mailboxResourceId, $calendarUuid, $start, $end, $timeZone);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CalendarEventsApi->listCalendarEvents: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **calendarUuid** | **string**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | |
| **start** | **\DateTime**| Start of the range, inclusive. ISO 8601 date-time with offset. | |
| **end** | **\DateTime**| End of the range, exclusive. ISO 8601 date-time after &#x60;start&#x60; and at most 32 days after it. | |
| **timeZone** | **string**| IANA time zone used to place all-day events and events without a time zone on days, also across a daylight saving change. Defaults to the fixed offset of &#x60;start&#x60;. | [optional] |

### Return type

[**\Hostinger\Model\V1CalendarEventsCollection**](../Model/V1CalendarEventsCollection.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `replyToCalendarEvent()`

```php
replyToCalendarEvent($mailboxResourceId, $calendarUuid, $eventUuid, $v1CalendarEventsReplyRequest, $ifMatch): \Hostinger\Model\V1CalendarEventsResource
```

Reply to calendar event

Answer an invitation from someone else: accept, decline or tentatively accept. It saves the answer on the event and emails it to the organizer, which cannot be recalled. `calendarUuid` and `eventUuid` come from `listCalendarEvents`. It works only when `getCalendarEvent` returns `replyable` true. An event the mailbox organizes or is not invited to is rejected with `403` and code `ERR_EVENT_NOT_REPLYABLE`, an event the organizer cancelled with `409` and code `ERR_EVENT_CANCELLED`. Send the `recurrenceId` of an item to answer one occurrence of a recurring event, or omit it to answer the whole series. Returns the event with the new `participationStatus`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\CalendarEventsApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$calendarUuid = 42c370e3-48ae-4286-90c5-d952f28c67cc; // string | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
$eventUuid = a1b2c3d4-e5f6-7890-abcd-ef1234567890; // string | Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence.
$v1CalendarEventsReplyRequest = new \Hostinger\Model\V1CalendarEventsReplyRequest(); // \Hostinger\Model\V1CalendarEventsReplyRequest
$ifMatch = 3c9f1a2b8e04; // string | Optional `etag` from `getCalendarEvent`. When the event changed since that call, the answer is not saved and the request fails with `412`: fetch the event again and retry. Omit it to apply the request to the current version.

try {
    $result = $apiInstance->replyToCalendarEvent($mailboxResourceId, $calendarUuid, $eventUuid, $v1CalendarEventsReplyRequest, $ifMatch);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CalendarEventsApi->replyToCalendarEvent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **calendarUuid** | **string**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | |
| **eventUuid** | **string**| Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | |
| **v1CalendarEventsReplyRequest** | [**\Hostinger\Model\V1CalendarEventsReplyRequest**](../Model/V1CalendarEventsReplyRequest.md)|  | |
| **ifMatch** | **string**| Optional &#x60;etag&#x60; from &#x60;getCalendarEvent&#x60;. When the event changed since that call, the answer is not saved and the request fails with &#x60;412&#x60;: fetch the event again and retry. Omit it to apply the request to the current version. | [optional] |

### Return type

[**\Hostinger\Model\V1CalendarEventsResource**](../Model/V1CalendarEventsResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `rescheduleCalendarEvent()`

```php
rescheduleCalendarEvent($mailboxResourceId, $calendarUuid, $eventUuid, $v1CalendarEventsRescheduleRequest, $ifMatch): \Hostinger\Model\V1CalendarEventsResource
```

Reschedule calendar event

Move an event to another time or change its length, keeping everything else (title, attendees, description and so on) as stored, so the event does not have to be fetched first. To change other fields use `updateCalendarEvent`. `calendarUuid` and `eventUuid` come from `listCalendarEvents`. Only an event with `editable` true can be moved; any other is rejected with `403` and code `ERR_EVENT_NOT_EDITABLE`. For a recurring event, `scope` `this` moves only the occurrence at `recurrenceId`, `future` ends the series before that occurrence and starts a new one with a new `uuid`, `all` (the default) moves the whole series: only the time of day and the length apply and the series keeps the date of its first occurrence. Attendees receive an email update unless `notifyAttendees` is false. Returns the moved event, or the moved occurrence for `scope` `this`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\CalendarEventsApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$calendarUuid = 42c370e3-48ae-4286-90c5-d952f28c67cc; // string | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
$eventUuid = a1b2c3d4-e5f6-7890-abcd-ef1234567890; // string | Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence.
$v1CalendarEventsRescheduleRequest = new \Hostinger\Model\V1CalendarEventsRescheduleRequest(); // \Hostinger\Model\V1CalendarEventsRescheduleRequest
$ifMatch = 3c9f1a2b8e04; // string | Optional `etag` from `getCalendarEvent`. When the event changed since that call, nothing is changed and the request fails with `412`: fetch the event again and retry. Omit it to apply the request to the current version.

try {
    $result = $apiInstance->rescheduleCalendarEvent($mailboxResourceId, $calendarUuid, $eventUuid, $v1CalendarEventsRescheduleRequest, $ifMatch);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CalendarEventsApi->rescheduleCalendarEvent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **calendarUuid** | **string**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | |
| **eventUuid** | **string**| Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | |
| **v1CalendarEventsRescheduleRequest** | [**\Hostinger\Model\V1CalendarEventsRescheduleRequest**](../Model/V1CalendarEventsRescheduleRequest.md)|  | |
| **ifMatch** | **string**| Optional &#x60;etag&#x60; from &#x60;getCalendarEvent&#x60;. When the event changed since that call, nothing is changed and the request fails with &#x60;412&#x60;: fetch the event again and retry. Omit it to apply the request to the current version. | [optional] |

### Return type

[**\Hostinger\Model\V1CalendarEventsResource**](../Model/V1CalendarEventsResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateCalendarEvent()`

```php
updateCalendarEvent($mailboxResourceId, $calendarUuid, $eventUuid, $v1CalendarEventsUpdateRequest, $ifMatch): \Hostinger\Model\V1CalendarEventsResource
```

Update calendar event

Change the details of an event: title, times, description, location, attendees, recurrence and so on. Every field replaces the stored value and an omitted optional field is cleared, so call `getCalendarEvent` first and send back the values that should stay. To only move an event in time, use `rescheduleCalendarEvent`. Only an event with `editable` true can be changed; any other is rejected with `403` and code `ERR_EVENT_NOT_EDITABLE`. For a recurring event, `scope` `this` changes only the occurrence at `recurrenceId`, `future` ends the series before that occurrence and starts a new one with a new `uuid`, `all` (the default) changes the whole series, keeping the date of its first occurrence. Attendees receive an email update, added attendees an invitation and removed ones a cancellation, unless `notifyAttendees` is false. Returns the changed event, or the changed occurrence for `scope` `this`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = Hostinger\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Hostinger\Api\CalendarEventsApi(config: $config);
$mailboxResourceId = AC1a2b3c4d5e6f7g; // string | Resource ID of the managed mailbox the bearer token is authorized for.
$calendarUuid = 42c370e3-48ae-4286-90c5-d952f28c67cc; // string | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
$eventUuid = a1b2c3d4-e5f6-7890-abcd-ef1234567890; // string | Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence.
$v1CalendarEventsUpdateRequest = new \Hostinger\Model\V1CalendarEventsUpdateRequest(); // \Hostinger\Model\V1CalendarEventsUpdateRequest
$ifMatch = 3c9f1a2b8e04; // string | Optional `etag` from `getCalendarEvent`. When the event changed since that call, nothing is changed and the request fails with `412`: fetch the event again and retry. Omit it to apply the request to the current version.

try {
    $result = $apiInstance->updateCalendarEvent($mailboxResourceId, $calendarUuid, $eventUuid, $v1CalendarEventsUpdateRequest, $ifMatch);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CalendarEventsApi->updateCalendarEvent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **mailboxResourceId** | **string**| Resource ID of the managed mailbox the bearer token is authorized for. | |
| **calendarUuid** | **string**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | |
| **eventUuid** | **string**| Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | |
| **v1CalendarEventsUpdateRequest** | [**\Hostinger\Model\V1CalendarEventsUpdateRequest**](../Model/V1CalendarEventsUpdateRequest.md)|  | |
| **ifMatch** | **string**| Optional &#x60;etag&#x60; from &#x60;getCalendarEvent&#x60;. When the event changed since that call, nothing is changed and the request fails with &#x60;412&#x60;: fetch the event again and retry. Omit it to apply the request to the current version. | [optional] |

### Return type

[**\Hostinger\Model\V1CalendarEventsResource**](../Model/V1CalendarEventsResource.md)

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
