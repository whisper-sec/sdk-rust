# ChangeEvent

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**timestamp** | Option<**String**> | When the change was detected | [optional]
**field** | Option<**String**> | Field that changed (dot notation, e.g., 'dns.a_record') | [optional]
**old_value** | Option<[**serde_json::Value**](.md)> |  | [optional]
**new_value** | Option<[**serde_json::Value**](.md)> |  | [optional]
**category** | Option<**String**> | Category of the change (dns, whois, ssl, etc.) | [optional]
**severity** | Option<**String**> | Severity of the change: low, medium, high | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


