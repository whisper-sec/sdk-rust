# MonitorDashboardResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total_checks** | Option<**i32**> | Total number of checks | [optional]
**passing_checks** | Option<**i32**> | Number of passing checks | [optional]
**failing_checks** | Option<**i32**> | Number of failing checks | [optional]
**degraded_checks** | Option<**i32**> | Number of degraded checks | [optional]
**overall_status** | Option<**String**> | Overall status | [optional]
**avg_uptime24_hours** | Option<**f64**> | Average uptime percentage over the last 24 hours | [optional]
**avg_uptime7_days** | Option<**f64**> | Average uptime percentage over the last 7 days | [optional]
**avg_uptime30_days** | Option<**f64**> | Average uptime percentage over the last 30 days | [optional]
**avg_response_time** | Option<**i64**> | Average response time across all checks in milliseconds | [optional]
**checks_by_type** | Option<**std::collections::HashMap<String, i32>**> | Count of checks by type | [optional]
**checks_by_status** | Option<**std::collections::HashMap<String, i32>**> | Count of checks by status | [optional]
**last_updated** | Option<**String**> | When this dashboard data was last updated | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


