# CypherQueryRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | **String** | The Cypher query to execute. Must be a read-only query (MATCH/RETURN).  Use `$paramName` syntax to reference parameters from the `parameters` map.  | 
**parameters** | Option<[**std::collections::HashMap<String, serde_json::Value>**](serde_json::Value.md)> | Query parameters as key-value pairs. Use `$key` in the query to reference these.  Supported value types: String, Number, Boolean, List, Map.  | [optional]
**limit** | Option<**i32**> | Maximum number of results to return. Overrides any LIMIT clause in the query. | [optional][default to 100]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


