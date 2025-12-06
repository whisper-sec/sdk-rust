# \OperationsApi

All URIs are relative to *http://api.whisper.security*

Method | HTTP request | Description
------------- | ------------- | -------------
[**ai_attribute**](OperationsApi.md#ai_attribute) | **POST** /v1/ops/ai/attribute | Threat Actor Attribution (Asynchronous)
[**ai_correlate**](OperationsApi.md#ai_correlate) | **POST** /v1/ops/ai/correlate | Global Indicator Correlation (Asynchronous)
[**ai_investigate**](OperationsApi.md#ai_investigate) | **POST** /v1/ops/ai/investigate | AI Threat Investigation (Asynchronous)
[**ai_pivot**](OperationsApi.md#ai_pivot) | **POST** /v1/ops/ai/pivot | AI Infrastructure Pivot (Asynchronous)
[**bulk_enrichment**](OperationsApi.md#bulk_enrichment) | **POST** /v1/ops/enrichment/bulk | Bulk Indicator Enrichment (Asynchronous)
[**create_infrastructure_map**](OperationsApi.md#create_infrastructure_map) | **POST** /v1/ops/scans/map | Map Infrastructure Relationships (Asynchronous)
[**create_infrastructure_scan**](OperationsApi.md#create_infrastructure_scan) | **POST** /v1/ops/scans/infrastructure | Infrastructure Security Scan (Asynchronous)
[**create_monitor_check**](OperationsApi.md#create_monitor_check) | **POST** /v1/ops/monitoring | Create Monitoring Check
[**create_monitoring_alert**](OperationsApi.md#create_monitoring_alert) | **POST** /v1/ops/monitoring/{target}/alert | Configure Monitoring Alerts (Asynchronous)
[**create_screenshot**](OperationsApi.md#create_screenshot) | **POST** /v1/ops/screenshots/capture | Capture a Website Screenshot (Asynchronous)
[**delete_monitor_check**](OperationsApi.md#delete_monitor_check) | **DELETE** /v1/ops/monitoring/{checkId} | Delete Monitoring Check
[**find_similar_cases**](OperationsApi.md#find_similar_cases) | **POST** /v1/ops/ai/similar-cases | Find Similar Cases (Asynchronous)
[**get_changes**](OperationsApi.md#get_changes) | **GET** /v1/ops/tracking/{type}/{value} | Get Detected Changes
[**get_industry_benchmark**](OperationsApi.md#get_industry_benchmark) | **GET** /v1/ops/ai/benchmark/{industry} | Get Industry Security Benchmark (Synchronous)
[**get_job**](OperationsApi.md#get_job) | **GET** /v1/ops/jobs/{jobId} | Get Asynchronous Job Status and Results
[**get_monitor_check**](OperationsApi.md#get_monitor_check) | **GET** /v1/ops/monitoring/{checkId} | Get Monitoring Check
[**get_monitor_dashboard**](OperationsApi.md#get_monitor_dashboard) | **GET** /v1/ops/monitoring/dashboard | Get Monitoring Dashboard
[**get_monitor_results**](OperationsApi.md#get_monitor_results) | **GET** /v1/ops/monitoring/{checkId}/results | Get Check Results
[**get_monitoring_status**](OperationsApi.md#get_monitoring_status) | **GET** /v1/ops/monitoring/status/{target} | Get Monitoring Status and Metrics
[**get_screenshot_history**](OperationsApi.md#get_screenshot_history) | **GET** /v1/ops/screenshots/history | Get Screenshot History
[**list_jobs**](OperationsApi.md#list_jobs) | **GET** /v1/ops/jobs/list | List Recent Jobs
[**list_monitor_checks**](OperationsApi.md#list_monitor_checks) | **GET** /v1/ops/monitoring | List Monitoring Checks
[**list_tracked_indicators**](OperationsApi.md#list_tracked_indicators) | **GET** /v1/ops/tracking | List Tracked Indicators
[**schedule_screenshot**](OperationsApi.md#schedule_screenshot) | **POST** /v1/ops/screenshots/schedule | Schedule Recurring Screenshots (Asynchronous)
[**search_indicators**](OperationsApi.md#search_indicators) | **POST** /v1/ops/enrichment/search | Search Indicators (Asynchronous)
[**similar_domains**](OperationsApi.md#similar_domains) | **POST** /v1/ops/enrichment/similar-domains | Find Similar Domains (Asynchronous)
[**start_change_tracking**](OperationsApi.md#start_change_tracking) | **POST** /v1/ops/tracking/{type}/{value} | Start Change Tracking
[**stop_change_tracking**](OperationsApi.md#stop_change_tracking) | **DELETE** /v1/ops/tracking/{type}/{value} | Stop Change Tracking
[**trigger_check**](OperationsApi.md#trigger_check) | **POST** /v1/ops/tracking/{type}/{value}/check | Trigger Immediate Check
[**trigger_monitor_check**](OperationsApi.md#trigger_monitor_check) | **POST** /v1/ops/monitoring/{checkId}/trigger | Trigger Manual Check
[**update_monitor_check**](OperationsApi.md#update_monitor_check) | **PUT** /v1/ops/monitoring/{checkId} | Update Monitoring Check



## ai_attribute

> models::JobResponse ai_attribute(attribute_request)
Threat Actor Attribution (Asynchronous)

<p>Analyzes indicators and context to identify potential threat actors and campaigns. Uses ML clustering and TTP matching against known threat actor profiles.</p> <h4>Attribution Analysis:</h4> <ul>     <li><b>Actor Identification:</b> Potential threat actor matches with confidence</li>     <li><b>Campaign Clustering:</b> Groups indicators into potential campaigns</li>     <li><b>TTP Mapping:</b> MITRE ATT&CK technique mapping</li>     <li><b>Historical Context:</b> Known actor activity patterns</li> </ul> <h4>Limitations:</h4> <p>Maximum 500 indicators per request. Attribution is probabilistic and should be validated.</p> <h4>Performance:</h4> <p>Campaign clustering and analysis. Expected: 60-300 seconds.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**attribute_request** | [**AttributeRequest**](AttributeRequest.md) | Attribution request | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## ai_correlate

> models::JobResponse ai_correlate(correlate_request)
Global Indicator Correlation (Asynchronous)

<p>Correlates your indicators against anonymized global threat data from all customers. Identifies shared campaigns, widespread threats, and prevalence across industries.</p> <h4>Correlation Analysis:</h4> <ul>     <li><b>Prevalence:</b> How common are these indicators across our customer base</li>     <li><b>Industry Breakdown:</b> Which industries are seeing these indicators</li>     <li><b>Campaign Detection:</b> Are these part of a broader campaign</li>     <li><b>First/Last Seen:</b> Global timeline of indicator activity</li>     <li><b>Co-occurrence:</b> Indicators frequently seen together</li> </ul> <h4>Limitations:</h4> <p>Maximum 100 indicators per request.</p> <h4>Performance:</h4> <p>Cross-customer correlation. Expected: 10-60 seconds.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**correlate_request** | [**CorrelateRequest**](CorrelateRequest.md) | Correlation request | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## ai_investigate

> models::JobResponse ai_investigate(investigate_request)
AI Threat Investigation (Asynchronous)

<p>Initiates a comprehensive AI-powered threat investigation for an indicator. Uses large language models to analyze threat intelligence, generate insights, and provide actionable recommendations.</p> <h4>Investigation Output:</h4> <ul>     <li><b>Verdict:</b> Threat assessment with confidence score</li>     <li><b>Timeline:</b> Activity timeline reconstruction</li>     <li><b>Analysis:</b> Detailed findings from multiple data sources</li>     <li><b>Related Indicators:</b> Discovered related infrastructure</li>     <li><b>Recommendations:</b> Suggested response actions</li> </ul> <h4>Performance:</h4> <p>LLM-based analysis. Expected completion: 30-180 seconds depending on complexity.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**investigate_request** | [**InvestigateRequest**](InvestigateRequest.md) | Investigation request | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## ai_pivot

> models::JobResponse ai_pivot(pivot_request)
AI Infrastructure Pivot (Asynchronous)

<p>Performs intelligent infrastructure pivoting starting from an indicator. Uses ML to identify the most relevant relationships and suggest investigation paths.</p> <h4>Pivot Strategies:</h4> <ul>     <li><b>infrastructure:</b> Shared hosting, nameservers, certificates</li>     <li><b>registration:</b> Same registrant, registration patterns</li>     <li><b>behavioral:</b> Similar traffic patterns, communication</li>     <li><b>temporal:</b> Co-occurrence within time windows</li> </ul> <h4>Response Includes:</h4> <ul>     <li>Discovered related indicators with relevance scores</li>     <li>Suggested investigation paths ranked by priority</li>     <li>Relationship graph data</li> </ul> <h4>Performance:</h4> <p>Graph traversal with ML ranking. Expected: 10-120 seconds based on depth.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**pivot_request** | [**PivotRequest**](PivotRequest.md) | Pivot request | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## bulk_enrichment

> models::JobResponse bulk_enrichment(bulk_request)
Bulk Indicator Enrichment (Asynchronous)

<p>Process multiple indicators (IPs and/or domains) in a single request. This endpoint is optimized for batch processing and can handle up to 100 indicators per request.</p> <p><b>Performance:</b> Processing time depends on batch size and requested data modules. Expect 5-30 seconds for typical batches.</p> <p><b>Rate Limits:</b> Limited to 10 requests per minute due to the resource-intensive nature of bulk operations.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**bulk_request** | [**BulkRequest**](BulkRequest.md) | List of indicators and processing options. | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_infrastructure_map

> models::JobResponse create_infrastructure_map(infrastructure_map_request)
Map Infrastructure Relationships (Asynchronous)

<p>Creates a comprehensive map of infrastructure relationships starting from a domain or IP. Discovers connected assets through shared hosting, DNS, certificates, and network relationships.</p> <h4>Mapping Depth Levels:</h4> <ul>     <li><b>Depth 1:</b> Direct relationships only (~30 seconds, 10-50 assets)</li>     <li><b>Depth 2:</b> 2 hops out (~2-5 minutes, 50-500 assets)</li>     <li><b>Depth 3:</b> 3 hops out (~10-30 minutes, 500-5000 assets)</li> </ul> <h4>Relationship Types Discovered:</h4> <ul>     <li>Domains on same IP</li>     <li>Domains sharing nameservers</li>     <li>Domains with same SSL certificate</li>     <li>IPs in same ASN</li>     <li>Domains with same registrant</li> </ul> <h4>Output Format:</h4> <p>Results returned as graph data compatible with visualization libraries (nodes and edges).</p> <h4>Use Cases:</h4> <ul>     <li>Threat actor infrastructure mapping</li>     <li>Discovering related phishing domains</li>     <li>Finding shadow IT and forgotten assets</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**infrastructure_map_request** | [**InfrastructureMapRequest**](InfrastructureMapRequest.md) | Mapping configuration. Example: ```json {   \"startPoint\": \"example.com\",   \"depth\": 2 } ```  | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_infrastructure_scan

> models::JobResponse create_infrastructure_scan(scan_request)
Infrastructure Security Scan (Asynchronous)

<p>Initiates a comprehensive security scan of a domain's infrastructure. Performs reconnaissance, port scanning, service detection, and vulnerability assessment.</p> <h4>Scan Types:</h4> <ul>     <li><b>comprehensive:</b> Full scan including all modules (recommended for complete assessment)</li>     <li><b>subdomains:</b> Subdomain enumeration only</li>     <li><b>ports:</b> Port scanning and service detection</li>     <li><b>technologies:</b> Technology stack detection</li>     <li><b>vulnerabilities:</b> Known vulnerability checks</li>     <li><b>ssl:</b> SSL/TLS configuration and certificate analysis</li>     <li><b>dns:</b> DNS configuration and zone transfer tests</li>     <li><b>whois:</b> Registration and ownership information</li> </ul> <h4>Performance:</h4> <ul>     <li><b>Quick scans:</b> 30-60 seconds (subdomains, dns, whois)</li>     <li><b>Comprehensive scan:</b> 5-15 minutes depending on infrastructure size</li> </ul> <h4>Use Cases:</h4> <ul>     <li>Pre-engagement reconnaissance for penetration testing</li>     <li>Attack surface assessment</li>     <li>Infrastructure inventory and mapping</li>     <li>Vulnerability management</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**scan_request** | [**ScanRequest**](ScanRequest.md) | Scan configuration including target domain and scan type. | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_monitor_check

> models::MonitorCheckResponse create_monitor_check(monitor_check_request)
Create Monitoring Check

<p>Create a new monitoring check to track uptime and performance of a URL or endpoint.</p> <h4>Check Types:</h4> <ul>     <li><b>api:</b> HTTP/HTTPS endpoint monitoring - checks status code, response time, content</li>     <li><b>ssl:</b> SSL certificate monitoring - validates certificate and tracks expiry</li>     <li><b>dns:</b> DNS record monitoring - validates DNS resolution and record values</li> </ul> <h4>Frequency Options:</h4> <p>Check frequency in minutes: 1, 5, 10, 15, 30, 60, 1440 (daily)</p> <h4>Locations:</h4> <p>Checks can run from multiple global locations: us-east-1, us-west-1, eu-west-1, ap-southeast-1</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**monitor_check_request** | [**MonitorCheckRequest**](MonitorCheckRequest.md) | Monitoring check configuration | [required] |

### Return type

[**models::MonitorCheckResponse**](MonitorCheckResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_monitoring_alert

> models::JobResponse create_monitoring_alert(target, monitoring_alert_request)
Configure Monitoring Alerts (Asynchronous)

<p>Create alert rules for a monitored asset. Get notified via webhook, email, or Slack when specific conditions are met.</p> <h4>Alert Types:</h4> <ul>     <li><b>downtime:</b> Site becomes unreachable</li>     <li><b>dns_change:</b> DNS records modified</li>     <li><b>whois_change:</b> Registration details updated</li>     <li><b>ssl_expiring:</b> Certificate expires soon (7, 14, 30 days)</li>     <li><b>content_change:</b> Page content modified</li>     <li><b>technology_change:</b> Tech stack changes detected</li> </ul> <h4>Notification Channels:</h4> <ul>     <li>Webhook (POST to your endpoint)</li>     <li>Email</li>     <li>Slack</li>     <li>PagerDuty</li> </ul> <h4>Example Configuration:</h4> <pre><code>{   \"type\": \"ssl_expiring\",   \"threshold_days\": 14,   \"channels\": [\"email\", \"slack\"],   \"email\": \"alerts@example.com\",   \"slack_webhook\": \"https://hooks.slack.com/...\" }</code></pre> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**target** | **String** | The domain or IP address to configure alerts for. | [required] |
**monitoring_alert_request** | [**MonitoringAlertRequest**](MonitoringAlertRequest.md) | Alert configuration including type, thresholds, and notification channels. | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_screenshot

> models::JobResponse create_screenshot(screenshot_request)
Capture a Website Screenshot (Asynchronous)

<p>Initiates an asynchronous job to capture a screenshot of a website. Supports various viewport sizes, full-page captures, and JavaScript rendering.</p> <p><b>Performance Note:</b> A typical screenshot capture takes 10-30 seconds. Poll the `/v1/ops/jobs/{jobId}` endpoint to retrieve the URL of the final image.</p> <p><b>Output:</b> The job result will contain a URL to download the screenshot image in the specified format (PNG, JPEG, or WebP).</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**screenshot_request** | [**ScreenshotRequest**](ScreenshotRequest.md) | The URL and options for the screenshot capture. | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_monitor_check

> delete_monitor_check(check_id)
Delete Monitoring Check

Delete a monitoring check and stop all monitoring for the target.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**check_id** | **String** | Check ID | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## find_similar_cases

> models::JobResponse find_similar_cases(similar_cases_request)
Find Similar Cases (Asynchronous)

<p>Uses ML to find historical threat cases similar to the current investigation. Helps analysts understand attack patterns and expected outcomes.</p> <h4>Matching Criteria:</h4> <ul>     <li>Indicator overlap and relationships</li>     <li>Behavioral patterns and TTPs</li>     <li>Infrastructure characteristics</li>     <li>Attack progression similarities</li> </ul> <h4>Response Includes:</h4> <ul>     <li>Similar cases with similarity scores</li>     <li>Case outcomes and verdicts</li>     <li>Common patterns across matches</li> </ul> <h4>Performance:</h4> <p>ML similarity matching. Expected completion: 5-30 seconds.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**similar_cases_request** | [**SimilarCasesRequest**](SimilarCasesRequest.md) | Similar cases request | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_changes

> models::ChangeTrackingResponse get_changes(r#type, value, since)
Get Detected Changes

<p>Retrieve detected changes for a tracked indicator. Returns the current tracking configuration, baseline snapshot, and list of all detected changes.</p> <h4>Response Includes:</h4> <ul>     <li><b>tracking:</b> Current tracking configuration (enabled, frequency, fields, next check)</li>     <li><b>baseline:</b> The stored baseline snapshot data</li>     <li><b>changes:</b> Array of detected changes with timestamps, old/new values</li>     <li><b>totalChanges:</b> Total number of changes detected</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**r#type** | **String** | Indicator type: ip or domain | [required] |
**value** | **String** | Indicator value | [required] |
**since** | Option<**String**> | ISO 8601 timestamp to get changes from |  |

### Return type

[**models::ChangeTrackingResponse**](ChangeTrackingResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_industry_benchmark

> models::BenchmarkResponse get_industry_benchmark(industry, size, region)
Get Industry Security Benchmark (Synchronous)

<p>Returns anonymized, aggregated security metrics for your industry vertical. Compare your security posture against peers.</p> <h4>Available Industries:</h4> <ul>     <li>financial_services, healthcare, technology, retail, manufacturing</li>     <li>energy, telecommunications, government, education, media</li> </ul> <h4>Metrics Included:</h4> <ul>     <li><b>Risk Scores:</b> Average risk score, percentiles (25th, 50th, 75th, 90th)</li>     <li><b>Response Metrics:</b> Mean time to detect (MTTD), mean time to respond (MTTR)</li>     <li><b>Detection Metrics:</b> Detection rate, false positive rate</li>     <li><b>Threat Profile:</b> Top threats, common attack vectors, targeted assets</li>     <li><b>Trends:</b> 30-day risk trend direction and change percentage</li> </ul> <h4>Performance:</h4> <p>Pre-aggregated data. Response time typically under 500ms with 1-hour cache.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**industry** | **String** | Industry vertical code | [required] |
**size** | Option<**String**> | Organization size filter |  |
**region** | Option<**String**> | Geographic region filter |  |

### Return type

[**models::BenchmarkResponse**](BenchmarkResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_job

> models::Job get_job(job_id)
Get Asynchronous Job Status and Results

<p>Retrieves the current status and results of an asynchronous job. Poll this endpoint to check job progress.</p> <h4>Polling Recommendations:</h4> <ul>     <li>For fast jobs (e.g., similar domains), poll every 1-2 seconds.</li>     <li>For slow jobs (e.g., WHOIS search, screenshots), poll every 5-10 seconds.</li>     <li>Implement an exponential backoff strategy for very long-running jobs.</li>     <li>Stop polling when the status is `COMPLETED`, `FAILED`, or `CANCELLED`.</li> </ul> <h4>Job Statuses:</h4> <ul>     <li><b>PENDING:</b> Job is queued and waiting to start.</li>     <li><b>PROCESSING:</b> Job is actively being processed.</li>     <li><b>COMPLETED:</b> Job finished successfully, results are available.</li>     <li><b>FAILED:</b> Job failed with an error.</li>     <li><b>CANCELLED:</b> Job was cancelled by user or system.</li> </ul> 

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


## get_monitor_check

> models::MonitorCheckResponse get_monitor_check(check_id)
Get Monitoring Check

Get details of a specific monitoring check including uptime metrics.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**check_id** | **String** | Check ID | [required] |

### Return type

[**models::MonitorCheckResponse**](MonitorCheckResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_monitor_dashboard

> models::MonitorDashboardResponse get_monitor_dashboard()
Get Monitoring Dashboard

<p>Get aggregated dashboard statistics for all monitoring checks.</p> <h4>Includes:</h4> <ul>     <li>Total, passing, failing, and degraded check counts</li>     <li>Average uptime percentages (24h, 7d, 30d)</li>     <li>Average response time</li>     <li>Checks grouped by type and status</li> </ul> 

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::MonitorDashboardResponse**](MonitorDashboardResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_monitor_results

> get_monitor_results(check_id, limit)
Get Check Results

<p>Get the execution history for a monitoring check.</p> <h4>Response includes for each result:</h4> <ul>     <li>Timestamp of execution</li>     <li>Success/failure status</li>     <li>Response time</li>     <li>HTTP status code (for API checks)</li>     <li>Error message (if failed)</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**check_id** | **String** | Check ID | [required] |
**limit** | Option<**i32**> | Maximum number of results to return |  |[default to 10]

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_monitoring_status

> get_monitoring_status(target)
Get Monitoring Status and Metrics

<p>Retrieves current monitoring configuration and historical metrics for a domain or IP address.</p> <h4>Status Information:</h4> <ul>     <li><b>Monitoring State:</b> Active, paused, or not monitored</li>     <li><b>Check Frequency:</b> How often checks are performed</li>     <li><b>Active Alerts:</b> Currently triggered alert conditions</li>     <li><b>Last Check:</b> Timestamp of most recent check</li> </ul> <h4>Metrics Included:</h4> <ul>     <li>Uptime percentage (last 30 days)</li>     <li>Average response time</li>     <li>SSL certificate expiration countdown</li>     <li>DNS change events</li>     <li>WHOIS change events</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**target** | **String** | The domain or IP address to check monitoring status for. | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_screenshot_history

> get_screenshot_history(target, limit)
Get Screenshot History

<p>Retrieve all previously captured screenshots for a specific URL, ordered by capture time (newest first). Includes download URLs and metadata for each capture.</p> <h4>Response Includes:</h4> <ul>     <li><b>Download URL:</b> Direct link to screenshot image</li>     <li><b>Capture Time:</b> Timestamp when screenshot was taken</li>     <li><b>Dimensions:</b> Image width and height</li>     <li><b>Format:</b> Image format (PNG, JPEG, WebP)</li>     <li><b>File Size:</b> Size in bytes</li> </ul> <h4>Use Cases:</h4> <ul>     <li>Review website evolution over time</li>     <li>Compare screenshots for change detection</li>     <li>Download historical screenshots for reporting</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**target** | **String** | The target domain or URL to retrieve screenshot history for. | [required] |
**limit** | Option<**i32**> | Maximum number of screenshots to return. |  |[default to 10]

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_jobs

> list_jobs(status, limit, offset)
List Recent Jobs

<p>Retrieves a list of recent jobs for the authenticated user, optionally filtered by status.</p> <h4>Query Parameters:</h4> <ul>     <li><b>status:</b> Filter by job status (PENDING, PROCESSING, COMPLETED, FAILED, CANCELLED)</li>     <li><b>limit:</b> Maximum number of jobs to return (default: 50, max: 100)</li>     <li><b>offset:</b> Number of jobs to skip for pagination (default: 0)</li> </ul> <h4>Response Format:</h4> <p>Returns a JSON object with a \"jobs\" array containing job summaries.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**status** | Option<**String**> | Filter by job status |  |
**limit** | Option<**i32**> | Maximum number of jobs to return |  |[default to 50]
**offset** | Option<**i32**> | Number of jobs to skip |  |[default to 0]

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_monitor_checks

> models::MonitorListResponse list_monitor_checks(r#type, status)
List Monitoring Checks

<p>Get a list of all monitoring checks created by the authenticated user.</p> <h4>Filtering:</h4> <ul>     <li><b>type:</b> Filter by check type (api, ssl, dns)</li>     <li><b>status:</b> Filter by status (passing, failing, degraded, pending)</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**r#type** | Option<**String**> | Filter by check type |  |
**status** | Option<**String**> | Filter by status |  |

### Return type

[**models::MonitorListResponse**](MonitorListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_tracked_indicators

> list_tracked_indicators()
List Tracked Indicators

<p>Get a list of all indicators currently being tracked for changes by the authenticated user.</p> 

### Parameters

This endpoint does not need any parameter.

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*, application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## schedule_screenshot

> models::JobResponse schedule_screenshot(screenshot_request)
Schedule Recurring Screenshots (Asynchronous)

<p>Create a recurring job to capture website screenshots at regular intervals. Essential for monitoring website changes, detecting defacements, and tracking competitor updates.</p> <h4>Schedule Options:</h4> <ul>     <li><b>Cron Expression:</b> Full cron syntax support (e.g., `0 0 * * * *` = hourly)</li>     <li><b>Frequency Presets:</b> hourly, daily, weekly, monthly</li>     <li><b>Timezone:</b> Specify timezone for accurate scheduling</li>     <li><b>Retention:</b> Auto-cleanup old screenshots (default: keep last 30)</li> </ul> <h4>Performance:</h4> <ul>     <li><b>Setup Time:</b> ~2 seconds to create schedule</li>     <li><b>Screenshot Time:</b> 10-30 seconds per capture</li> </ul> <h4>Use Cases:</h4> <ul>     <li>Automated defacement detection</li>     <li>Compliance monitoring and archival</li>     <li>Competitor website tracking</li>     <li>Visual regression testing</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**screenshot_request** | [**ScreenshotRequest**](ScreenshotRequest.md) | Schedule configuration including URL, schedule timing, and screenshot options. | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## search_indicators

> models::JobResponse search_indicators(search_request)
Search Indicators (Asynchronous)

<p>Initiates an asynchronous job to search for indicators matching specific criteria. This endpoint is extremely powerful for infrastructure discovery and threat hunting.</p> <p><b>Performance Note:</b> Searches on WHOIS fields (like `registrantCompany`) are data-intensive and can take over 50 seconds to complete. This endpoint is therefore asynchronous by design. Poll the `/v1/ops/jobs/{jobId}` endpoint to retrieve results.</p> <h4>Example Search Queries:</h4> <ul>     <li>`registrantCompany:EvilCorp` - Find all domains registered by EvilCorp</li>     <li>`asn:15169` - Find all IPs in Google's ASN</li>     <li>`city:\"San Francisco\"` - Find all IPs geolocated to San Francisco</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**search_request** | [**SearchRequest**](SearchRequest.md) | The search query and configuration. | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## similar_domains

> models::JobResponse similar_domains(similar_domains_ops_request)
Find Similar Domains (Asynchronous)

<p>Generates potential lookalike, typosquatting, and homoglyph domains for brand protection and threat hunting.</p> <h4>Detection Methods:</h4> <ul>     <li>Typosquatting (keyboard proximity)</li>     <li>Homoglyph attacks (visually similar characters)</li>     <li>Combosquatting (brand + keyword)</li>     <li>TLD variations</li> </ul> <h4>Performance:</h4> <p>Typically completes in 5-15 seconds depending on options.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**similar_domains_ops_request** | [**SimilarDomainsOpsRequest**](SimilarDomainsOpsRequest.md) | Similar domains request with domain and options. | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## start_change_tracking

> models::JobResponse start_change_tracking(r#type, value, change_tracking_request)
Start Change Tracking

<p>Start tracking changes for an IP or domain. When tracking is started, a baseline snapshot is captured. Subsequent checks will compare against this baseline and record any detected changes.</p> <h4>Trackable Fields for Domains:</h4> <ul>     <li><b>dns:</b> A, AAAA, MX, NS, TXT, CNAME records</li>     <li><b>whois:</b> Registrant, registrar, dates, nameservers</li>     <li><b>ssl:</b> Certificate issuer, expiry, SAN</li>     <li><b>subdomains:</b> Discovered subdomains</li>     <li><b>ips:</b> Resolved IP addresses</li> </ul> <h4>Trackable Fields for IPs:</h4> <ul>     <li><b>geolocation:</b> Country, city, coordinates</li>     <li><b>asn:</b> ASN number, organization</li>     <li><b>routing:</b> BGP routing status</li>     <li><b>rpki:</b> RPKI validation status</li>     <li><b>reverse_dns:</b> PTR records</li> </ul> <h4>Frequencies:</h4> <ul>     <li><b>hourly:</b> Check every hour</li>     <li><b>daily:</b> Check once per day (default)</li>     <li><b>weekly:</b> Check once per week</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**r#type** | **String** | Indicator type: ip or domain | [required] |
**value** | **String** | Indicator value (IP address or domain name) | [required] |
**change_tracking_request** | [**ChangeTrackingRequest**](ChangeTrackingRequest.md) | Tracking configuration | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## stop_change_tracking

> stop_change_tracking(r#type, value, delete_history)
Stop Change Tracking

<p>Stop tracking changes for an indicator. Optionally delete all change history.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**r#type** | **String** | Indicator type: ip or domain | [required] |
**value** | **String** | Indicator value | [required] |
**delete_history** | Option<**bool**> | Delete change history as well |  |[default to false]

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## trigger_check

> models::JobResponse trigger_check(r#type, value)
Trigger Immediate Check

<p>Trigger an immediate check for changes on a tracked indicator. Creates a job to compare current data against the stored baseline.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**r#type** | **String** | Indicator type | [required] |
**value** | **String** | Indicator value | [required] |

### Return type

[**models::JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*, application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## trigger_monitor_check

> trigger_monitor_check(check_id)
Trigger Manual Check

Trigger an immediate execution of a monitoring check.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**check_id** | **String** | Check ID | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_monitor_check

> models::MonitorCheckResponse update_monitor_check(check_id, monitor_check_request)
Update Monitoring Check

Update an existing monitoring check configuration.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**check_id** | **String** | Check ID | [required] |
**monitor_check_request** | [**MonitorCheckRequest**](MonitorCheckRequest.md) | Updated check configuration | [required] |

### Return type

[**models::MonitorCheckResponse**](MonitorCheckResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

