# SubdomainResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain** | **String** | The root domain that was queried | 
**total_count** | **i32** | Total number of subdomains discovered | 
**subdomains** | [**Vec<models::SubdomainInfo>**](SubdomainInfo.md) | List of discovered subdomains | 
**timestamp** | **String** | Timestamp of when the data was retrieved | 
**sources** | Option<**Vec<String>**> | Data sources used for subdomain discovery | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


