# PredictiveRiskResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | Option<[**models::QueryInfo**](QueryInfo.md)> |  | [optional]
**current_assessment** | Option<[**models::CurrentAssessment**](CurrentAssessment.md)> |  | [optional]
**predictions** | Option<[**models::Predictions**](Predictions.md)> |  | [optional]
**trajectory** | Option<[**models::TrajectoryInfo**](TrajectoryInfo.md)> |  | [optional]
**risk_factors** | Option<[**Vec<models::RiskFactor>**](RiskFactor.md)> | Contributing risk factors | [optional]
**pattern_matching** | Option<[**models::PatternMatching**](PatternMatching.md)> |  | [optional]
**early_warnings** | Option<[**Vec<models::EarlyWarning>**](EarlyWarning.md)> | Early warning signals | [optional]
**similar_cases** | Option<[**Vec<models::SimilarCase>**](SimilarCase.md)> | Similar historical cases | [optional]
**model_info** | Option<[**models::ModelInfo**](ModelInfo.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


