# # V1SendRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**to** | **string[]** |  |
**displayName** | **string** |  |
**cc** | **string[]** |  |
**bcc** | **string[]** |  |
**subject** | **string** |  |
**text** | **string** |  |
**html** | **string** |  |
**attachments** | [**\Hostinger\Model\V1SendAttachment[]**](V1SendAttachment.md) |  |
**inReplyTo** | [**\Hostinger\Model\V1SendMessageRef**](V1SendMessageRef.md) | Source message this is a reply to. Copies its Message-Id/References into In-Reply-To/References and flags it \\Answered. Mutually exclusive with forwardOf. |
**forwardOf** | [**\Hostinger\Model\V1SendMessageRef**](V1SendMessageRef.md) | Source message this forwards. Copies its Message-Id/References into In-Reply-To/References and flags it $forwarded. Mutually exclusive with inReplyTo. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
