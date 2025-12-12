# BulkOptions

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**parallel_processing** | Option<**bool**> | Enable parallel processing of indicators for faster results | [optional][default to true]
**batch_size** | Option<**i32**> | Number of indicators to process in each batch. Smaller batches = more frequent progress updates | [optional][default to 10]
**timeout_per_indicator** | Option<**i32**> | Maximum time in milliseconds to wait for each indicator before timing out. Domain enrichment and ip_intelligence require longer timeouts. | [optional][default to 30000]
**continue_on_error** | Option<**bool**> | Continue processing remaining indicators if one fails. Recommended for large batches. | [optional][default to true]
**include_failed** | Option<**bool**> | Include failed indicators in the response with error details | [optional][default to false]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


