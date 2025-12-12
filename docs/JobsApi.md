# \JobsApi

All URIs are relative to *https://api.whisper.security*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_job**](JobsApi.md#get_job) | **GET** /v1/ops/jobs/{jobId} | Get Asynchronous Job Status and Results
[**list_jobs**](JobsApi.md#list_jobs) | **GET** /v1/ops/jobs/list | List Recent Jobs



## get_job

> models::Job get_job(job_id)
Get Asynchronous Job Status and Results

<p>Retrieves the current status and results of an asynchronous job. Poll this endpoint to check job progress.</p> <h4>Polling Recommendations:</h4> <ul>     <li>For fast jobs (e.g., similar domains), poll every 1-2 seconds.</li>     <li>For slow jobs (e.g., WHOIS search, screenshots), poll every 5-10 seconds.</li>     <li>Implement an exponential backoff strategy for very long-running jobs.</li>     <li>Stop polling when the status is `COMPLETED`, `FAILED`, or `CANCELLED`.</li> </ul> <h4>Job Statuses:</h4> <ul>     <li><b>PENDING:</b> Job is queued and waiting to start.</li>     <li><b>PROCESSING:</b> Job is actively being processed.</li>     <li><b>COMPLETED:</b> Job finished successfully, results are available.</li>     <li><b>FAILED:</b> Job failed with an error.</li>     <li><b>CANCELLED:</b> Job was cancelled by user or system.</li> </ul> <h4>Result Schemas by Job Type:</h4> <ul>     <li><b>ai-investigate:</b> InvestigateResult - verdict, timeline, analysis, recommendations</li>     <li><b>ai-pivot:</b> PivotResult - related indicators, investigation paths, relationship graph</li>     <li><b>ai-attribute:</b> AttributeResult - actor identification, campaign clustering, TTP mapping</li>     <li><b>ai-correlate:</b> CorrelateResult - prevalence, industry breakdown, co-occurrence</li>     <li><b>ai-similar-cases:</b> SimilarCasesResult - similar cases with similarity scores</li>     <li><b>screenshot:</b> ScreenshotResult - screenshot URL, ID, capture time, metadata</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**job_id** | **String** | The unique ID of the job, returned from a `POST` operation. | [required] |

### Return type

[**models::Job**](Job.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_jobs

> models::JobListResponse list_jobs(status, limit, offset)
List Recent Jobs

<p>Retrieves a list of recent jobs for the authenticated user, optionally filtered by status.</p> <h4>Query Parameters:</h4> <ul>     <li><b>status:</b> Filter by job status (PENDING, PROCESSING, COMPLETED, FAILED, CANCELLED)</li>     <li><b>limit:</b> Maximum number of jobs to return (default: 50, max: 100)</li>     <li><b>offset:</b> Number of jobs to skip for pagination (default: 0)</li> </ul> <h4>Response Format:</h4> <p>Returns a JSON object with a \"jobs\" array containing job summaries.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**status** | Option<**String**> | Filter by job status |  |
**limit** | Option<**i32**> | Maximum number of jobs to return |  |[default to 50]
**offset** | Option<**i32**> | Number of jobs to skip |  |[default to 0]

### Return type

[**models::JobListResponse**](JobListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

