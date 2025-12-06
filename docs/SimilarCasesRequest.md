# SimilarCasesRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicators** | **Vec<String>** | List of indicators for the current case | 
**behavior_description** | Option<**String**> | Description of observed behavior | [optional]
**observed_ttps** | Option<**Vec<String>**> | Observed MITRE ATT&CK TTPs | [optional]
**min_similarity** | Option<**f64**> | Confidence threshold for matches (0-1) | [optional]
**limit** | Option<**i32**> | Maximum number of similar cases to return | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


