# InvestigateContext

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**hypothesis** | Option<**String**> | Initial hypothesis or suspicion to focus the investigation. The AI will attempt to prove or disprove this theory. | [optional]
**related_indicators** | Option<**Vec<String>**> | Related indicators (IPs, domains, hashes) to include in the investigation scope. Helps identify connections between indicators. | [optional]
**time_range** | Option<**String**> | Time range for historical analysis. Format: number + unit (d=days, w=weeks, m=months). Examples: 7d, 2w, 3m, 90d | [optional]
**industry** | Option<**String**> | Industry sector for contextualized threat analysis. Helps identify industry-specific threats and attack patterns. | [optional]
**region** | Option<**String**> | Geographic region for localized threat intelligence. Helps identify region-specific threats. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


