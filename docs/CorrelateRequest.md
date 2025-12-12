# CorrelateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicators** | **Vec<String>** | List of indicators (IPs, domains, hashes) to correlate across global threat intelligence. Maximum 100 indicators per request. | 
**options** | Option<[**models::CorrelateOptions**](CorrelateOptions.md)> | Optional configuration object for correlation analysis. NOT a string - must be an object with fields like timeWindow, minConfidence, etc. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


