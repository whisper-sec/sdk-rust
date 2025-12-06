# ErrorResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | **i32** | The HTTP status code of the error | 
**error** | **String** | A short, machine-readable error code | 
**message** | **String** | A human-readable error message providing more detail | 
**details** | Option<[**serde_json::Value**](.md)> | Additional details about the error, including field-specific validation errors | [optional]
**timestamp** | **String** | The timestamp when the error occurred | 
**trace_id** | Option<**String**> | A unique trace ID for this request, useful for debugging | [optional]
**path** | Option<**String**> | The API path that generated this error | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


