# JobSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**job_id** | Option<**String**> | Unique job identifier | [optional]
**r#type** | Option<**String**> | Type of job | [optional]
**status** | Option<**String**> | Current job status | [optional]
**created_at** | Option<**String**> | Job creation timestamp | [optional]
**completed_at** | Option<**String**> | Job completion timestamp (if completed) | [optional]
**progress** | Option<[**models::ProgressInfo**](ProgressInfo.md)> | Job progress information | [optional]
**error** | Option<[**models::ErrorInfo**](ErrorInfo.md)> | Error information (if failed) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


