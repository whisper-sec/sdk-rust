# SimilarCasesRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicators** | **Vec<String>** | List of indicators (IPs, domains, hashes, URLs) associated with the current case. This is the primary matching criteria. | 
**behavior_description** | Option<**String**> | Free-text description of observed malicious behavior or incident details. Improves matching accuracy by considering behavioral patterns. | [optional]
**observed_ttps** | Option<**Vec<String>**> | Observed MITRE ATT&CK technique IDs. Helps find cases with similar attack techniques. See https://attack.mitre.org for reference. | [optional]
**min_similarity** | Option<**f64**> | Minimum similarity score threshold (0.0 to 1.0). Higher values return fewer but more precise matches. Default: 0.5 | [optional][default to 0.5]
**limit** | Option<**i32**> | Maximum number of similar cases to return. Higher limits may increase processing time. | [optional][default to 10]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


