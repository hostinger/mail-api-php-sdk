# # V1CalendarEventsRecurrenceRule

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**frequency** | **string** | Unit of repetition. Only DAILY, WEEKLY, MONTHLY and YEARLY can be written; SECONDLY, MINUTELY and HOURLY appear only on events created by other calendar applications. |
**interval** | **int** | Repeat every this many units of &#x60;frequency&#x60;. 1 to 1000 when writing. |
**byDay** | [**\Hostinger\Model\V1CalendarEventsRecurrenceDay[]**](V1CalendarEventsRecurrenceDay.md) | Weekdays the event repeats on. Null when unused. |
**byMonthDay** | **int[]** | Days of the month, 1 to 31. Negative values count from the end of the month: -1 is the last day. Always null for a WEEKLY rule. |
**byMonth** | **int[]** | Months, 1 is January. Null when unused. |
**count** | **int** | Number of occurrences after which the series ends, at most 1000 when writing. Never set together with &#x60;until&#x60;. |
**until** | **\DateTime** | Moment after which the series ends, not before the start of the event. Never set together with &#x60;count&#x60;. |
**weekStart** | **string** | First day of the week used by the rule. Null when not set. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
