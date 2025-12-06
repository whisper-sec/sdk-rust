# IndicatorResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | Option<[**models::QueryInfo**](QueryInfo.md)> |  | [optional]
**summary** | Option<[**models::SummaryInfo**](SummaryInfo.md)> |  | [optional]
**geolocation** | Option<[**serde_json::Value**](.md)> |  | [optional]
**network** | Option<[**serde_json::Value**](.md)> |  | [optional]
**routing** | Option<[**serde_json::Value**](.md)> |  | [optional]
**isp** | Option<[**serde_json::Value**](.md)> |  | [optional]
**registration** | Option<[**serde_json::Value**](.md)> |  | [optional]
**dns** | Option<[**models::DnsInfo**](DnsInfo.md)> |  | [optional]
**relationships** | Option<[**models::RelationshipInfo**](RelationshipInfo.md)> |  | [optional]
**reputation** | Option<[**models::ReputationInfo**](ReputationInfo.md)> |  | [optional]
**security** | Option<[**serde_json::Value**](.md)> |  | [optional]
**rpki** | Option<[**serde_json::Value**](.md)> |  | [optional]
**ip_intelligence** | Option<[**std::collections::HashMap<String, serde_json::Value>**](serde_json::Value.md)> | When domain is queried with include=ip_intelligence, contains full intelligence for each resolved IP | [optional]
**metadata** | Option<[**models::MetadataInfo**](MetadataInfo.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


