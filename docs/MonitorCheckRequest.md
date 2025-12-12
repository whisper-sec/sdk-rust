# MonitorCheckRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **String** | Name of the monitoring check | 
**url** | **String** | URL to monitor | 
**r#type** | Option<**String**> | Type of check: api, ssl, or dns | [optional]
**frequency** | Option<**i32**> | Check frequency in minutes | [optional]
**locations** | Option<**Vec<String>**> | Locations to run checks from | [optional]
**assertions** | Option<[**models::MonitorAssertions**](MonitorAssertions.md)> | Assertions for the check | [optional]
**enabled** | Option<**bool**> | Whether the check is enabled | [optional]
**method** | Option<**String**> | HTTP method for API checks | [optional]
**headers** | Option<**std::collections::HashMap<String, String>**> | Request headers for API checks | [optional]
**body** | Option<**String**> | Request body for POST/PUT API checks | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


