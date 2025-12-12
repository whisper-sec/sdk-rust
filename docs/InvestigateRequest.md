# InvestigateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicator** | **String** | The indicator to investigate (IP address, domain name, or file hash) | 
**indicator_type** | **String** | Type of indicator being investigated | 
**depth** | Option<**String**> | Investigation depth level. 'quick' (30-60s) for basic checks, 'standard' (60-120s) for typical investigations, 'comprehensive' (120-300s) for deep analysis. | [optional][default to Standard]
**context** | Option<[**models::InvestigateContext**](InvestigateContext.md)> | Optional context object to guide the investigation. Provides additional information like hypothesis, related indicators, and time range. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


