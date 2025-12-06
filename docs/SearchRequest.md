# SearchRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | **String** | Search query using field:value syntax. Supports multiple fields combined with logical operators.  **Supported Fields:** - WHOIS: `registrantCompany`, `registrantName`, `registrantEmail`, `registrar` - Network: `asn`, `network`, `country_code`, `city` - Domain: `tld`, `domain_length`, `creation_date`  **Examples:** - `registrantCompany:EvilCorp` - Find domains by registrant - `asn:15169 AND country_code:US` - Complex query with AND - `registrantEmail:admin@example.com` - Find domains by email  | 
**field** | Option<**String**> | Specific field to search in. If provided, the query is interpreted as a value for this field. | [optional]
**filters** | Option<**std::collections::HashMap<String, String>**> | Additional filters to narrow down search results. Applied after query matching. | [optional]
**limit** | Option<**i32**> | Maximum number of results to return per page | [optional][default to 100]
**offset** | Option<**i32**> | Number of results to skip for pagination. Use with limit for paginated results. | [optional][default to 0]
**sort_by** | Option<**String**> | Field to sort results by | [optional]
**sort_order** | Option<**String**> | Sort order | [optional][default to Asc]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


