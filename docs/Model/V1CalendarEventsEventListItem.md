# # V1CalendarEventsEventListItem

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** | Event identifier, the &#x60;eventUuid&#x60; of the calendar event endpoints. Every occurrence of a recurring event has the same uuid. |
**calendarUuid** | **string** | Identifier of the calendar the event is stored in. |
**recurrenceId** | **\DateTime** | Identifies one occurrence of a recurring event. Null for a one-off event or for the series itself. |
**title** | **string** |  |
**start** | **\DateTime** | Start in UTC. When &#x60;allDay&#x60; is true, the date at midnight (2026-09-29T00:00:00.000000Z). An event stored without a time zone keeps its wall-clock time (09:00 is 09:00:00.000000Z). |
**end** | **\DateTime** | Exclusive end, same form as &#x60;start&#x60;. When &#x60;allDay&#x60; is true, midnight of the day after the last day of the event (2026-09-30T00:00:00.000000Z for a one-day event on 2026-09-29). |
**allDay** | **bool** |  |
**timeZone** | **string** | IANA time zone the event is stored in. Null when it has none. |
**editable** | **bool** | Whether &#x60;updateCalendarEvent&#x60;, &#x60;rescheduleCalendarEvent&#x60; and &#x60;deleteCalendarEvent&#x60; can change the event. |
**color** | **string** | Color of the event. The calendar color when the event has none or is an invitation from someone else. |
**participationStatus** | **string** | Answer of the mailbox to an invitation from someone else. Null for its own events. |
**status** | **string** | CANCELLED when the organizer cancelled the event, CONFIRMED otherwise. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
