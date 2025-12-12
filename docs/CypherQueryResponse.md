# CypherQueryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**results** | Option<[**Vec<std::collections::HashMap<String, serde_json::Value>>**](std::collections::HashMap.md)> | Query results as a list of records. Each record is a map of column name to value. | [optional]
**execution_time_ms** | Option<**i64**> | Query execution time in milliseconds | [optional]
**row_count** | Option<**i32**> | Number of rows returned | [optional]
**columns** | Option<**Vec<String>**> | Column names in the result set | [optional]
**truncated** | Option<**bool**> | Whether the result was truncated due to limit | [optional]
**error** | Option<**String**> | Error message if the query failed | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


