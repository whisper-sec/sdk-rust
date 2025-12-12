# GraphNode

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**String**> | Unique identifier for the node (typically the domain name, IP address, or ASN) | [optional]
**r#type** | Option<**String**> | Type of infrastructure element this node represents | [optional]
**label** | Option<**String**> | Human-readable label for display (may differ from id) | [optional]
**properties** | Option<[**std::collections::HashMap<String, serde_json::Value>**](serde_json::Value.md)> | Additional properties for node styling or filtering | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


