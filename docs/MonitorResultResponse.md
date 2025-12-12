# MonitorResultResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**timestamp** | Option<**String**> | When the check was executed | [optional]
**success** | Option<**bool**> | Whether the check passed | [optional]
**location** | Option<**String**> | Location where check ran | [optional]
**attempt** | Option<**i32**> | Check attempt number (for retries) | [optional]
**check_id** | Option<**String**> | ID of the check this result belongs to | [optional]
**result_id** | Option<**String**> | Unique result ID | [optional]
**response_time** | Option<**i64**> | Response time in milliseconds | [optional]
**status_code** | Option<**i32**> | HTTP status code received | [optional]
**error_message** | Option<**String**> | Error message if check failed | [optional]
**has_errors** | Option<**bool**> | Whether check ran from all locations | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


