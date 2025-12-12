# AttributionContext

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**observed_ttps** | Option<**Vec<String>**> | Observed MITRE ATT&CK technique IDs. See https://attack.mitre.org for reference. | [optional]
**targeted_sector** | Option<**String**> | Targeted industry sector. Common values: financial, healthcare, government, technology, energy, retail, manufacturing | [optional]
**target_region** | Option<**String**> | Geographic region of targets. Use ISO country codes or region names. | [optional]
**timeframe** | Option<**String**> | Campaign timeframe for attribution. Format: 'YYYY-MM-DD to YYYY-MM-DD' or descriptive like 'Q1 2024' | [optional]
**malware_families** | Option<**Vec<String>**> | Known malware families observed in the campaign. Helps narrow down threat actor candidates. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


