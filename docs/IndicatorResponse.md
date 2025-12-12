# IndicatorResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | Option<[**models::QueryInfo**](QueryInfo.md)> | Query metadata including the indicator type, value, and response timing | [optional]
**summary** | Option<[**models::SummaryInfo**](SummaryInfo.md)> | Executive summary with key facts about the indicator for quick decision-making | [optional]
**geolocation** | Option<[**serde_json::Value**](.md)> |  | [optional]
**network** | Option<[**serde_json::Value**](.md)> |  | [optional]
**routing** | Option<[**serde_json::Value**](.md)> |  | [optional]
**isp** | Option<[**serde_json::Value**](.md)> |  | [optional]
**registration** | Option<[**serde_json::Value**](.md)> |  | [optional]
**dns** | Option<[**models::DnsInfo**](DnsInfo.md)> | DNS records and resolution data | [optional]
**relationships** | Option<[**models::RelationshipInfo**](RelationshipInfo.md)> | Relationship data showing connections to other infrastructure | [optional]
**reputation** | Option<[**models::ReputationInfo**](ReputationInfo.md)> | Reputation and risk scoring information | [optional]
**security** | Option<[**serde_json::Value**](.md)> |  | [optional]
**rpki** | Option<[**serde_json::Value**](.md)> |  | [optional]
**ip_intelligence** | Option<[**std::collections::HashMap<String, serde_json::Value>**](serde_json::Value.md)> | When domain is queried with include=ip_intelligence, contains full intelligence for each resolved IP | [optional]
**metadata** | Option<[**models::MetadataInfo**](MetadataInfo.md)> | Response metadata including data sources, errors, and processing information | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


