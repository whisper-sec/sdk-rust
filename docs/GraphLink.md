# GraphLink

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**source** | Option<**String**> | ID of the source node (where the relationship originates) | [optional]
**target** | Option<**String**> | ID of the target node (where the relationship points to) | [optional]
**r#type** | Option<**String**> | Type of relationship between the nodes | [optional]
**weight** | Option<**f64**> | Weight or strength of the relationship (for layout algorithms) | [optional]
**properties** | Option<[**std::collections::HashMap<String, serde_json::Value>**](serde_json::Value.md)> | Additional properties for link styling or filtering | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


