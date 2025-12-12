# TrackedIndicator

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | Option<**String**> | Indicator type: ip or domain | [optional]
**value** | Option<**String**> | Indicator value | [optional]
**enabled** | Option<**bool**> | Whether tracking is currently enabled | [optional]
**frequency** | Option<**String**> | Check frequency: hourly, daily, weekly | [optional]
**fields** | Option<**Vec<String>**> | Fields being tracked | [optional]
**created_at** | Option<**String**> | When tracking was started | [optional]
**last_check_at** | Option<**String**> | When the last check was performed | [optional]
**next_check_at** | Option<**String**> | When the next check is scheduled | [optional]
**total_changes** | Option<**i32**> | Total number of changes detected | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


