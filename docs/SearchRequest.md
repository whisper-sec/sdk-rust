# SearchRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**effective_page** | Option<**i32**> |  | [optional]
**query** | Option<**String**> | Search query using field:value syntax (alternative to individual field parameters). If individual field parameters are provided, they take precedence.  **Supported Syntax:** - Single field: `registrantCompany:Google` - Multiple fields: `registrantCompany:Google registrantCountry:US`  **Note:** For new integrations, prefer using individual field parameters instead of query syntax.  | [optional]
**field** | Option<**String**> | Field to search in when using simple query mode. Use with `query` parameter. | [optional]
**tld** | Option<**String**> | Top-Level Domain to filter by (exact match). Examples: com, org, net, io | [optional]
**registrar_name** | Option<**String**> | Domain registrar name to filter by (exact match) | [optional]
**registrar_iana_id** | Option<**String**> | IANA registrar ID to filter by (exact match) | [optional]
**registrant_name** | Option<**String**> | Registrant name to search for (text search, partial match) | [optional]
**registrant_company** | Option<**String**> | Registrant company/organization to search for (text search, partial match) | [optional]
**registrant_email** | Option<**String**> | Registrant email to search for (text search). Supports wildcards like *@example.com | [optional]
**registrant_phone** | Option<**String**> | Registrant phone number to search for (text search) | [optional]
**registrant_country** | Option<**String**> | Registrant country code to filter by (2-letter ISO code) | [optional]
**registrant_city** | Option<**String**> | Registrant city to search for (text search) | [optional]
**name_server** | Option<**String**> | Name server hostname to search for (text search) | [optional]
**domain_status** | Option<**String**> | Domain status flag to search for (text search). E.g., clientTransferProhibited | [optional]
**created_date** | Option<**String**> | Domain creation date to filter by (exact match, format: YYYY-MM-DD) | [optional]
**updated_date** | Option<**String**> | Domain last update date to filter by (exact match, format: YYYY-MM-DD) | [optional]
**expiry_date** | Option<**String**> | Domain expiry date to filter by (exact match, format: YYYY-MM-DD) | [optional]
**limit** | Option<**i32**> | Maximum number of results to return per page (max 100 for WHOIS searches) | [optional][default to 100]
**page** | Option<**i32**> | Page number for pagination (0-indexed). Alternative to offset. | [optional][default to 0]
**offset** | Option<**i32**> | Number of results to skip for pagination. Converted to page internally. | [optional][default to 0]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


