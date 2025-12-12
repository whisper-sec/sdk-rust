# BulkRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicators** | **Vec<String>** | List of indicators (IP addresses or domains) to enrich. Mix of IPs and domains is supported. The indicator type is auto-detected. | 
**include** | Option<**Vec<String>**> | Additional data modules to include for each indicator. By default, base enrichment includes geolocation, ASN, reputation, and relationships. For domains, WHOIS (registration) and DNS data are included by default.  <b>Available options:</b> <ul>   <li><code>routing</code> - BGP routing data, prefix visibility, route origins (IPs only)</li>   <li><code>rpki</code> - RPKI validation status (IPs only)</li>   <li><code>historical</code> - Historical data for the indicator</li>   <li><code>whois</code> - WHOIS registration data (domains only, included by default)</li>   <li><code>dns</code> - DNS records (domains only, included by default)</li>   <li><code>ip_intelligence</code> - Full IP enrichment for resolved domain IPs (domains only, significantly increases processing time)</li> </ul>  Note: Adding more include options increases processing time per indicator.  | [optional]
**options** | Option<[**models::BulkOptions**](BulkOptions.md)> | Advanced processing options for bulk operations. Customize batch size, timeouts, and error handling. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


