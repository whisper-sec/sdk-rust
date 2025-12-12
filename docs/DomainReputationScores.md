# DomainReputationScores

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**overall_score** | Option<**f64**> | Overall reputation score (0-100, higher = more suspicious) | [optional]
**risk_level** | Option<**String**> | Risk classification based on overall score | [optional]
**domain_ip_score** | Option<**f64**> | Average IP reputation score for domain's A records | [optional]
**nameserver_ip_score** | Option<**f64**> | Average IP reputation score for nameserver IPs | [optional]
**mailserver_ip_score** | Option<**f64**> | Average IP reputation score for mail server IPs | [optional]
**details** | Option<[**models::DomainReputationDetails**](DomainReputationDetails.md)> | Detailed breakdown of infrastructure and individual scores | [optional]
**scoring_method** | Option<**String**> | Scoring methodology used | [optional]
**weights** | Option<**std::collections::HashMap<String, f64>**> | Weighting strategy applied to infrastructure components | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


