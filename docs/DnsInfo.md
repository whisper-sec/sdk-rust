# DnsInfo

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**arecords** | Option<**Vec<String>**> |  | [optional]
**a_records** | Option<**Vec<String>**> | A records (IPv4 addresses) | [optional]
**aaaa_records** | Option<**Vec<String>**> | AAAA records (IPv6 addresses) | [optional]
**mx_records** | Option<[**Vec<serde_json::Value>**](serde_json::Value.md)> | MX records (mail servers) with priority and hostname | [optional]
**ns_records** | Option<**Vec<String>**> | NS records (name servers) | [optional]
**txt_records** | Option<**Vec<String>**> | TXT records (text records for SPF, DKIM, etc.) | [optional]
**cname_records** | Option<**Vec<String>**> | CNAME records (canonical name aliases) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


