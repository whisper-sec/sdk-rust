# PivotRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicator** | **String** | Starting indicator (IP address, domain, or hash) for pivot analysis | 
**indicator_type** | **String** | Type of the starting indicator. Must be one of: ip, domain, hash | 
**depth** | Option<**i32**> | Pivot depth - how many hops to traverse from the starting indicator. Higher depth = more results but longer processing time. | [optional][default to 1]
**strategies** | Option<**Vec<String>**> | Pivot strategies to use. Possible values: dns (DNS relationships), whois (WHOIS data), ssl (SSL certificates), infrastructure (hosting), passive_dns (historical DNS) | [optional]
**max_nodes** | Option<**i32**> | Maximum number of related nodes/indicators to discover. Limits result size for performance. | [optional][default to 100]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


