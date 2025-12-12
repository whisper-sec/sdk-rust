# ReputationInfo

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**risk_score** | Option<**f64**> | Composite risk score (0-10, higher = riskier) | [optional]
**blacklists** | Option<[**models::BlacklistScores**](BlacklistScores.md)> | Blacklist presence scores across various threat feeds | [optional]
**domain_reputation** | Option<[**models::DomainReputationScores**](DomainReputationScores.md)> | Domain reputation based on infrastructure IP scoring (domains only) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


