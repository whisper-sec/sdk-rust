# SimilarDomainRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**techniques** | Option<**Vec<String>**> | Types of domain variations to generate | [optional]
**limit** | Option<**i32**> | Maximum number of similar domains to generate | [optional][default to 100]
**check_registration** | Option<**bool**> | Check if generated domains are registered | [optional][default to false]
**include_dns** | Option<**bool**> | Include DNS resolution data for registered domains | [optional][default to false]
**include_risk_score** | Option<**bool**> | Calculate risk scores for each variation | [optional][default to true]
**technique_config** | Option<[**models::TechniqueConfig**](TechniqueConfig.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


