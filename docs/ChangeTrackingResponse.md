# ChangeTrackingResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicator** | Option<**String**> | The indicator value (IP or domain) | [optional]
**r#type** | Option<**String**> | Indicator type: ip or domain | [optional]
**tracking** | Option<[**models::TrackingConfig**](TrackingConfig.md)> | Current tracking configuration | [optional]
**changes** | Option<[**Vec<models::ChangeEvent>**](ChangeEvent.md)> | List of detected changes | [optional]
**baseline** | Option<[**serde_json::Value**](.md)> |  | [optional]
**baseline_captured_at** | Option<**String**> | When the baseline was captured | [optional]
**total_changes** | Option<**i32**> | Total number of changes detected | [optional]
**error** | Option<**String**> | Error message if operation failed | [optional]
**success** | Option<**bool**> | Whether the operation was successful | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


