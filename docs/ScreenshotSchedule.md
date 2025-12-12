# ScreenshotSchedule

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**String**> | Unique identifier for this schedule | [optional]
**url** | Option<**String**> | The URL to capture screenshots of | [optional]
**username** | Option<**String**> | Username/API key owner of this schedule | [optional]
**cron** | Option<**String**> | Cron expression for scheduling (mutually exclusive with frequency) | [optional]
**frequency** | Option<**String**> | Frequency preset (mutually exclusive with cron). Use one of the preset values for simplified scheduling. | [optional]
**timezone** | Option<**String**> | Timezone for the schedule | [optional]
**enabled** | Option<**bool**> | Whether this schedule is currently active | [optional]
**options** | Option<[**models::ScreenshotOptions**](ScreenshotOptions.md)> | Screenshot options (width, height, format, etc.) | [optional]
**created_at** | Option<**String**> | When this schedule was created | [optional]
**updated_at** | Option<**String**> | When this schedule was last updated | [optional]
**last_capture_at** | Option<**String**> | When the last screenshot was captured | [optional]
**next_capture_at** | Option<**String**> | When the next screenshot is scheduled | [optional]
**capture_count** | Option<**i32**> | Total number of screenshots captured by this schedule | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


