# JobResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**job_id** | **String** | Unique identifier for the job. Use this ID to poll for job status and results. | 
**status** | **String** | Current status of the job | 
**status_url** | **String** | URL endpoint to poll for job status and results. Typically `/v1/ops/jobs/{jobId}`. | 
**message** | Option<**String**> | Human-readable message describing the job acceptance or current state | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


