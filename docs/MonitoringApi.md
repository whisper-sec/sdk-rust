# \MonitoringApi

All URIs are relative to *https://api.whisper.security*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_monitor_check**](MonitoringApi.md#create_monitor_check) | **POST** /v1/ops/monitoring | Create Monitoring Check
[**create_monitoring_alert**](MonitoringApi.md#create_monitoring_alert) | **POST** /v1/ops/monitoring/{target}/alert | Configure Monitoring Alert
[**delete_monitor_check**](MonitoringApi.md#delete_monitor_check) | **DELETE** /v1/ops/monitoring/{checkId} | Delete Monitoring Check
[**get_monitor_check**](MonitoringApi.md#get_monitor_check) | **GET** /v1/ops/monitoring/{checkId} | Get Monitoring Check
[**get_monitor_dashboard**](MonitoringApi.md#get_monitor_dashboard) | **GET** /v1/ops/monitoring/dashboard | Get Monitoring Dashboard
[**get_monitor_results**](MonitoringApi.md#get_monitor_results) | **GET** /v1/ops/monitoring/{checkId}/results | Get Check Results
[**get_monitoring_status**](MonitoringApi.md#get_monitoring_status) | **GET** /v1/ops/monitoring/status/{target} | Get Monitoring Status
[**list_monitor_checks**](MonitoringApi.md#list_monitor_checks) | **GET** /v1/ops/monitoring | List Monitoring Checks
[**trigger_monitor_check**](MonitoringApi.md#trigger_monitor_check) | **POST** /v1/ops/monitoring/{checkId}/trigger | Trigger Manual Check
[**update_monitor_check**](MonitoringApi.md#update_monitor_check) | **PUT** /v1/ops/monitoring/{checkId} | Update Monitoring Check



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
Configure Monitoring Alert

<p>Configure alert notifications for a monitored target. Set up notifications for downtime, SSL expiry, DNS changes, and more.</p> <h4>Alert Types:</h4> <ul>     <li><b>downtime:</b> Alert when target becomes unreachable</li>     <li><b>dns_change:</b> Alert when DNS records change</li>     <li><b>whois_change:</b> Alert when WHOIS data changes</li>     <li><b>ssl_expiring:</b> Alert when SSL certificate is expiring (within threshold days)</li>     <li><b>content_change:</b> Alert when page content changes significantly</li>     <li><b>technology_change:</b> Alert when detected technologies change</li> </ul> <h4>Notification Channels:</h4> <ul>     <li><b>email:</b> Send alerts via email</li>     <li><b>slack:</b> Post to Slack webhook</li>     <li><b>webhook:</b> POST to custom webhook URL</li>     <li><b>pagerduty:</b> Create PagerDuty incident</li> </ul> 

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


## delete_monitor_check

> serde_json::Value delete_monitor_check(check_id)
Delete Monitoring Check

Delete a monitoring check and stop all monitoring for the target.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**check_id** | **String** | Check ID | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*, application/json

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

> models::MonitorResultListResponse get_monitor_results(check_id, limit)
Get Check Results

<p>Get the execution history for a monitoring check.</p> <h4>Response includes for each result:</h4> <ul>     <li>Timestamp of execution</li>     <li>Success/failure status</li>     <li>Response time</li>     <li>HTTP status code (for API checks)</li>     <li>Error message (if failed)</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**check_id** | **String** | Check ID | [required] |
**limit** | Option<**i32**> | Maximum number of results to return |  |[default to 10]

### Return type

[**models::MonitorResultListResponse**](MonitorResultListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_monitoring_status

> models::MonitoringStatusResponse get_monitoring_status(target)
Get Monitoring Status

<p>Get the current monitoring status and metrics for a domain or IP address.</p> <h4>Metrics Returned:</h4> <ul>     <li>Uptime percentage (last 30 days)</li>     <li>Average response time</li>     <li>SSL certificate expiration countdown</li>     <li>DNS change events</li>     <li>WHOIS change events</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**target** | **String** | The domain or IP address to check monitoring status for. | [required] |

### Return type

[**models::MonitoringStatusResponse**](MonitoringStatusResponse.md)

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


## trigger_monitor_check

> models::GenericSuccessResponse trigger_monitor_check(check_id)
Trigger Manual Check

Trigger an immediate execution of a monitoring check.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**check_id** | **String** | Check ID | [required] |

### Return type

[**models::GenericSuccessResponse**](GenericSuccessResponse.md)

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

