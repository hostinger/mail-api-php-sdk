# # V1QuotaQuota

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**quotas** | [**\Hostinger\Model\V1QuotaQuotaResource[]**](V1QuotaQuotaResource.md) | Per-resource quota breakdown reported by the IMAP server. |
**totalUsage** | **int** | Aggregate storage usage across all resources, in bytes. |
**totalLimit** | **int** | Aggregate storage limit across all resources, in bytes. |
**totalPercentage** | **int** | Aggregate storage usage as a percentage of the total limit. |
**supported** | **bool** | Whether the IMAP server reports quota information for this mailbox. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
