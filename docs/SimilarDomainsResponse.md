# SimilarDomainsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain** | **String** | The input domain that was analyzed | 
**status** | **String** | Job completion status | 
**similar_domains** | [**Vec<models::SimilarDomainEntry>**](SimilarDomainEntry.md) | List of similar domains found | 
**total_count** | **i32** | Total number of similar domains found | 
**analysis** | [**models::AnalysisMetadata**](AnalysisMetadata.md) | Analysis metadata about the search | 
**error** | Option<**bool**> | Error flag, present only when status is 'failed' | [optional]
**message** | Option<**String**> | Error message, present only when status is 'failed' | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


