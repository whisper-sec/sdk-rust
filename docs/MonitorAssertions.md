# MonitorAssertions

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**headers** | Option<**std::collections::HashMap<String, String>**> | Expected response headers | [optional]
**status_code** | Option<**i32**> | Expected HTTP status code | [optional]
**max_response_time** | Option<**i64**> | Maximum response time in milliseconds | [optional]
**contains_text** | Option<**String**> | Text that must be present in response body | [optional]
**not_contains_text** | Option<**String**> | Text that must NOT be present in response body | [optional]
**ssl_days_until_expiry** | Option<**i32**> | Minimum SSL certificate days until expiry (for ssl checks) | [optional]
**dns_record_value** | Option<**String**> | Expected DNS record value (for dns checks) | [optional]
**dns_record_type** | Option<**String**> | DNS record type (for dns checks) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


