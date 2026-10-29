# # V1SendRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**to** | **string[]** | Primary recipient email addresses. |
**displayName** | **string** | Sender display name shown in the From header alongside the mailbox address. |
**cc** | **string[]** | Carbon-copy recipient email addresses. |
**bcc** | **string[]** | Blind-carbon-copy recipient email addresses. Not visible to other recipients. |
**subject** | **string** | Message subject line. |
**text** | **string** | Plain-text body. Optional; if both text and html are omitted the message is sent without a body. |
**html** | **string** | HTML body. Optional; if both text and html are omitted the message is sent without a body. Inline images are referenced via cid: URLs matching attachment cid values. |
**attachments** | [**\Hostinger\Model\V1SendAttachment[]**](V1SendAttachment.md) | Files to attach. Inline images set cid; regular attachments omit it. |
**inReplyTo** | [**\Hostinger\Model\V1SendMessageRef**](V1SendMessageRef.md) | Source message this is a reply to, as an object {uid, folder} — not the Message-ID header string. Copies its Message-Id/References into In-Reply-To/References and flags it \\Answered. Mutually exclusive with forwardOf. |
**forwardOf** | [**\Hostinger\Model\V1SendMessageRef**](V1SendMessageRef.md) | Source message this forwards, as an object {uid, folder} — not the Message-ID header string. Copies its Message-Id/References into In-Reply-To/References and flags it $forwarded. Mutually exclusive with inReplyTo. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
