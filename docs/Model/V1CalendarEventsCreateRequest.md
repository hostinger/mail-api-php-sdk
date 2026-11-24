# # V1CalendarEventsCreateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**title** | **string** | Title of the event. |
**start** | **string** | ISO 8601 date-time with offset; without an offset it is read as UTC. For an all-day event a date is enough (2026-09-28). |
**end** | **string** | Exclusive end, same format as &#x60;start&#x60;. Required for a timed event and not before &#x60;start&#x60;. For an all-day event the day after the last day (2026-09-29 for one day on 2026-09-28); omitted means one day. |
**allDay** | **bool** | &#x60;true&#x60; for an all-day event (dates only, &#x60;timeZone&#x60; ignored), &#x60;false&#x60; for an event at a time of day. |
**timeZone** | **string** | IANA time zone of the event. Required when &#x60;allDay&#x60; is false, ignored when &#x60;allDay&#x60; is true. |
**description** | **string** | Notes of the event. Omitted or null for none. |
**location** | **string** | Place of the event. Omitted or null for none. |
**meetingLink** | **string** | http or https URL of the online meeting. Omitted or null for none. |
**color** | **string** | Color of the event as #RRGGBB or #RRGGBBAA. Omitted or null uses the calendar color. |
**recurrenceRule** | [**\Hostinger\Model\V1CalendarEventsRecurrenceRule**](V1CalendarEventsRecurrenceRule.md) | Omitted or null for a one-off event. A repeating event sends every field of the rule, null when unused: &#x60;frequency&#x60; DAILY, WEEKLY, MONTHLY or YEARLY, &#x60;interval&#x60; 1 to 1000, and &#x60;count&#x60; or &#x60;until&#x60; to end it, not both. |
**reminder** | [**\Hostinger\Model\V1CalendarEventsReminder**](V1CalendarEventsReminder.md) | Alarm before the start: &#x60;value&#x60; 0 to 1000 and &#x60;unit&#x60;. Omitted or null for none. |
**attendees** | [**\Hostinger\Model\V1CalendarEventsAttendeeInput[]**](V1CalendarEventsAttendeeInput.md) | People to invite; each receives an email invitation. Unique addresses, at most 100 not counting the mailbox itself, across all occurrences. The own address of the mailbox is stored as accepted and not invited. Omitted, null or empty for none. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
