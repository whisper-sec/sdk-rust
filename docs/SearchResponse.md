# SearchResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**source** | **String** | The data source that was searched | 
**query_type** | **String** | The type of query that was performed | 
**items** | [**Vec<models::DomainItem>**](DomainItem.md) | List of matching domains | 
**total** | **i32** | Total number of matching records across all pages | 
**page_number** | **i32** | Current page number (0-indexed) | 
**page_size** | **i32** | Number of results per page | 
**total_pages** | **i32** | Total number of pages available | 
**error** | Option<**bool**> | Error flag, present only when the search failed | [optional]
**message** | Option<**String**> | Error message, present only when the search failed | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


