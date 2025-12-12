# MonitoringAlertRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | **String** | Type of alert condition to monitor | 
**threshold_days** | Option<**i32**> | Threshold in days (for ssl_expiring alerts). Alert triggers when SSL cert expires within this many days. | [optional]
**channels** | Option<**Vec<String>**> | Notification channels to use for alerts | [optional]
**email** | Option<**String**> | Email address for alert notifications | [optional]
**slack_webhook** | Option<**String**> | Slack webhook URL for notifications | [optional]
**webhook_url** | Option<**String**> | Custom webhook URL for notifications (will receive POST with alert data) | [optional]
**pagerduty_key** | Option<**String**> | PagerDuty integration key for incident creation | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


