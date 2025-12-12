# CorrelateOptions

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**time_window** | Option<**String**> | Time window for temporal correlation. Format: number + unit (d=days, w=weeks, m=months). Examples: 7d, 2w, 3m | [optional]
**correlation_types** | Option<**Vec<String>**> | Types of correlation to analyze. Possible values: infrastructure, campaign, actor, malware, technique | [optional]
**min_confidence** | Option<**f64**> | Minimum confidence threshold for correlations (0.0 to 1.0). Higher values return fewer but more confident results. | [optional]
**include_industry_breakdown** | Option<**bool**> | Include breakdown of indicator prevalence by industry sector in the response. | [optional]
**include_campaign_detection** | Option<**bool**> | Include campaign detection analysis to identify coordinated threat activity. | [optional]
**include_geographic_spread** | Option<**bool**> | Include geographic spread analysis showing indicator distribution across regions. | [optional]
**include_attack_patterns** | Option<**bool**> | Include attack pattern analysis based on MITRE ATT&CK framework. | [optional]
**anonymization_level** | Option<**String**> | Level of data anonymization. Values: none, standard, strict | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


