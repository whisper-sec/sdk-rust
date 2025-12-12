# MonitorCheckResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**String**> | Unique identifier for the check | [optional]
**name** | Option<**String**> | Name of the monitoring check | [optional]
**url** | Option<**String**> | URL being monitored | [optional]
**r#type** | Option<**String**> | Type of check | [optional]
**status** | Option<**String**> | Current status | [optional]
**enabled** | Option<**bool**> | Whether the check is enabled | [optional]
**frequency** | Option<**i32**> | Check frequency in minutes | [optional]
**locations** | Option<**Vec<String>**> | Locations where check runs | [optional]
**muted** | Option<**bool**> | Whether the check is muted (no alerts) | [optional]
**method** | Option<**String**> | HTTP method used for API checks | [optional]
**assertions** | Option<[**models::MonitorAssertions**](MonitorAssertions.md)> | Assertions configured for this check | [optional]
**last_run_at** | Option<**String**> | Last time the check ran | [optional]
**created_at** | Option<**String**> | When the check was created | [optional]
**updated_at** | Option<**String**> | When the check was last updated | [optional]
**uptime24_hours** | Option<**f64**> | Uptime percentage over the last 24 hours | [optional]
**uptime7_days** | Option<**f64**> | Uptime percentage over the last 7 days | [optional]
**uptime30_days** | Option<**f64**> | Uptime percentage over the last 30 days | [optional]
**response_time** | Option<**i64**> | Average response time in milliseconds | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


