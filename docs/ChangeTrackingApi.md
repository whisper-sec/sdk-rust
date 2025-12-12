# \ChangeTrackingApi

All URIs are relative to *https://api.whisper.security*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_changes**](ChangeTrackingApi.md#get_changes) | **GET** /v1/ops/tracking/{type}/{value} | Get Detected Changes
[**list_tracked_indicators**](ChangeTrackingApi.md#list_tracked_indicators) | **GET** /v1/ops/tracking | List Tracked Indicators
[**start_change_tracking**](ChangeTrackingApi.md#start_change_tracking) | **POST** /v1/ops/tracking/{type}/{value} | Start Change Tracking
[**stop_change_tracking**](ChangeTrackingApi.md#stop_change_tracking) | **DELETE** /v1/ops/tracking/{type}/{value} | Stop Change Tracking
[**trigger_check**](ChangeTrackingApi.md#trigger_check) | **POST** /v1/ops/tracking/{type}/{value}/check | Trigger Immediate Check



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


## list_tracked_indicators

> models::TrackedIndicatorsResponse list_tracked_indicators()
List Tracked Indicators

<p>Get a list of all indicators currently being tracked for changes by the authenticated user.</p> 

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::TrackedIndicatorsResponse**](TrackedIndicatorsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
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

> models::GenericSuccessResponse stop_change_tracking(r#type, value, delete_history)
Stop Change Tracking

<p>Stop tracking changes for an indicator. Optionally delete all change history.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**r#type** | **String** | Indicator type: ip or domain | [required] |
**value** | **String** | Indicator value | [required] |
**delete_history** | Option<**bool**> | Delete change history as well |  |[default to false]

### Return type

[**models::GenericSuccessResponse**](GenericSuccessResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## trigger_check

> models::GenericSuccessResponse trigger_check(r#type, value)
Trigger Immediate Check

<p>Trigger an immediate check for changes on a tracked indicator. Creates a job to compare current data against the stored baseline.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**r#type** | **String** | Indicator type | [required] |
**value** | **String** | Indicator value | [required] |

### Return type

[**models::GenericSuccessResponse**](GenericSuccessResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

