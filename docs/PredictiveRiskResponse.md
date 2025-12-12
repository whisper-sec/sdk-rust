# PredictiveRiskResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | Option<[**models::QueryInfo**](QueryInfo.md)> | Query metadata | [optional]
**current_assessment** | Option<[**models::CurrentAssessment**](CurrentAssessment.md)> | Current risk assessment | [optional]
**predictions** | Option<[**models::Predictions**](Predictions.md)> | Future risk predictions | [optional]
**trajectory** | Option<[**models::TrajectoryInfo**](TrajectoryInfo.md)> | Risk trajectory details | [optional]
**risk_factors** | Option<[**Vec<models::RiskFactor>**](RiskFactor.md)> | Contributing risk factors | [optional]
**pattern_matching** | Option<[**models::PatternMatching**](PatternMatching.md)> | Pattern matching insights | [optional]
**early_warnings** | Option<[**Vec<models::EarlyWarning>**](EarlyWarning.md)> | Early warning signals | [optional]
**similar_cases** | Option<[**Vec<models::SimilarCase>**](SimilarCase.md)> | Similar historical cases | [optional]
**model_info** | Option<[**models::ModelInfo**](ModelInfo.md)> | ML model information | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


