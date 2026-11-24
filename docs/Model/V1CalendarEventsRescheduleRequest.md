# # V1CalendarEventsRescheduleRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**start** | **string** | ISO 8601 date-time with offset; without an offset it is read as UTC. For an all-day event a date is enough (2026-09-28). |
**end** | **string** | Exclusive end, same format as &#x60;start&#x60;. Required for a timed event and not before &#x60;start&#x60;. For an all-day event the day after the last day (2026-09-29 for one day on 2026-09-28); omitted means one day. |
**allDay** | **bool** | &#x60;true&#x60; for an all-day event (dates only, &#x60;timeZone&#x60; ignored), &#x60;false&#x60; for an event at a time of day. |
**timeZone** | **string** | IANA time zone of the event. Required when &#x60;allDay&#x60; is false, ignored when &#x60;allDay&#x60; is true. |
**scope** | **string** | For a recurring event: &#x60;this&#x60; moves the occurrence at &#x60;recurrenceId&#x60;, &#x60;future&#x60; moves it and every later one, &#x60;all&#x60; moves the whole series. Omitted or null means &#x60;all&#x60;. Required when &#x60;recurrenceId&#x60; is sent. |
**recurrenceId** | **\DateTime** | &#x60;recurrenceId&#x60; of one occurrence, copied unchanged from a &#x60;listCalendarEvents&#x60; item. Required when &#x60;scope&#x60; is &#x60;this&#x60; or &#x60;future&#x60;, ignored for &#x60;all&#x60;. |
**notifyAttendees** | **bool** | &#x60;false&#x60; saves the change without emailing attendees, and copies of the event in the calendars of other Hostinger mailboxes are not updated. Omitted or null means &#x60;true&#x60;. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
