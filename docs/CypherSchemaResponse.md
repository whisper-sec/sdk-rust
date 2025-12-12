# CypherSchemaResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**node_labels** | Option<**Vec<String>**> | Available node labels in the graph.  Common node types: - `DomainName`: Domain names (e.g., google.com) - `A_ADDRESS`: IPv4 addresses - `AAAA_ADDRESS`: IPv6 addresses - `ASN`: Autonomous System Numbers - `ANNOUNCED_PREFIX_4`: IPv4 prefixes announced via BGP - `ANNOUNCED_PREFIX_6`: IPv6 prefixes announced via BGP - `Organisation`: Organisations owning ASNs - `Country`: Country information - `LIST`: Blocklist/whitelist entries - `LISTCATEGORY`: Categories of lists - `TLD`: Top-level domains - `TLSCA`: TLS Certificate Authorities - `TLSCert`: TLS Certificates  | [optional]
**relationship_types** | Option<**Vec<String>**> | Available relationship types in the graph.  Common relationships: - `hasIP`: Domain → A_ADDRESS (DNS A record) - `hasIPv6`: Domain → AAAA_ADDRESS (DNS AAAA record) - `hasNameserver`: Domain → DomainName (NS record) - `hasMailHost`: Domain → DomainName (MX record) - `hasTLD`: Domain → TLD - `announces`: ASN → ANNOUNCED_PREFIX - `inASN`: IP_PREFIX → ASN - `isListed`: IP/Domain → LIST (blocklist membership) - `hasCA`: TLSCert → TLSCA - `isIssuer`: TLSCA → TLSCert - `isSubjectOf`: DomainName → TLSCert  | [optional]
**node_properties** | Option<[**std::collections::HashMap<String, Vec<String>>**](Vec.md)> | Properties available on each node type, keyed by node label | [optional]
**relationship_properties** | Option<[**std::collections::HashMap<String, Vec<String>>**](Vec.md)> | Properties available on each relationship type, keyed by relationship type | [optional]
**node_count** | Option<**i64**> | Total number of nodes in the graph | [optional]
**relationship_count** | Option<**i64**> | Total number of relationships in the graph | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


