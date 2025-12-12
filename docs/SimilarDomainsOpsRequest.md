# SimilarDomainsOpsRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain** | **String** | The target domain to generate variations for | 
**techniques** | Option<**String**> | Techniques to use for generating similar domains. Supported values: typosquatting, homoglyph, bitsquatting, tld_variation, sounding, prefix, suffix, contains, levenshtein. If not specified, defaults to typosquatting. | [optional]
**limit** | Option<**i32**> | Maximum number of similar domains to return per technique | [optional]
**options** | Option<[**serde_json::Value**](.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


