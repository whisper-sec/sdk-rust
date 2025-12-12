# BulkEnrichmentResult

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | Option<**String**> | Status of the bulk enrichment | [optional]
**results** | Option<[**Vec<serde_json::Value>**](serde_json::Value.md)> | Array of successfully enriched indicator results. Each item contains: - `indicator`: The original indicator value (e.g., \"8.8.8.8\" or \"google.com\") - `type`: \"ip\" or \"domain\" - `query`: Request metadata with type, value, timestamp, and response_time_ms - `summary`: Key information summary (organization, location, ASN, risk_score, etc.)  For IP indicators: - `geolocation`: Country, city, coordinates, ISP details - `network`: BGP routing data if requested (visibility, origins, prefix info) - `isp`: ISP name, organization, ASN - `reputation`: Risk score and blacklist scores - `relationships`: Related domains and shared infrastructure  For domain indicators: - `registration`: WHOIS data (registrar, dates, nameservers, status, registrant info) - `dns`: DNS records (A, AAAA, MX, NS, TXT, CNAME) - `reputation`: Domain reputation with infrastructure scores - `relationships`: Related domains, incoming/outgoing links  | [optional]
**errors** | Option<[**Vec<serde_json::Value>**](serde_json::Value.md)> | Array of failed enrichment attempts. Each item contains: - `indicator`: The indicator that failed enrichment - `type`: \"ip\" or \"domain\" - `error`: true (boolean flag indicating this is an error entry) - `message`: Human-readable error description (e.g., \"Timeout or error during enrichment\")  | [optional]
**total_processed** | Option<**i32**> | Total number of indicators processed | [optional]
**total_failed** | Option<**i32**> | Total number of failed enrichments | [optional]
**total_indicators** | Option<**i32**> | Total number of indicators in the request | [optional]
**success_rate** | Option<**f64**> | Percentage of successful enrichments | [optional]
**message** | Option<**String**> | Error message if the entire job failed | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


