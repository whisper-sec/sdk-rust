# ScreenshotScheduleConfig

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**cron** | Option<**String**> | Cron expression for scheduling (advanced). Use frequency for simpler configuration. | [optional]
**frequency** | Option<**String**> | Frequency of captures. Use one of the preset values or provide a cron expression for custom schedules. | [optional]
**timezone** | Option<**String**> | Timezone for scheduled captures | [optional][default to UTC]
**retention_count** | Option<**i32**> | Maximum number of captures to retain | [optional][default to 30]
**enabled** | Option<**bool**> | Enable/disable the schedule | [optional][default to true]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


