# \IndicatorsApi

All URIs are relative to *http://api.whisper.security*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_indicator**](IndicatorsApi.md#get_indicator) | **GET** /v1/indicators/{type}/{value} | Enrich a Single Indicator (IP or Domain)
[**get_indicator_graph**](IndicatorsApi.md#get_indicator_graph) | **GET** /v1/indicators/{type}/{value}/graph | Get Infrastructure Relationship Graph
[**get_indicator_history**](IndicatorsApi.md#get_indicator_history) | **GET** /v1/indicators/{type}/{value}/history | Get Historical Data for Indicator
[**get_predictive_risk**](IndicatorsApi.md#get_predictive_risk) | **GET** /v1/indicators/{type}/{value}/predictive-risk | Get AI Predictive Risk Score
[**get_subdomains**](IndicatorsApi.md#get_subdomains) | **GET** /v1/indicators/domain/{domain}/subdomains | Get Domain Subdomains



## get_indicator

> models::IndicatorResponse get_indicator(r#type, value, include)
Enrich a Single Indicator (IP or Domain)

<p>Retrieves comprehensive intelligence for a single IP address or domain. This is the primary, high-performance endpoint for synchronous enrichment.</p> <p>It aggregates data from multiple sources, including geolocation, WHOIS, DNS, reputation scoring, and relationship mapping. Use the `include` parameter to request additional, deeper data sets that may have higher latency.</p> <h4>Performance:</h4> <ul>     <li><b>Base Response:</b> Typically under 500ms.</li>     <li><b>With `include=routing`:</b> First request may take up to 5 seconds; subsequent requests are cached for 5 minutes and respond in &lt;200ms.</li>     <li><b>With `include=ip_intelligence`:</b> Adds 200-500ms of latency for each IP address resolved from the domain.</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**r#type** | **String** | The type of indicator to enrich. | [required] |
**value** | **String** | The value of the indicator (e.g., an IPv4/IPv6 address or a domain name). | [required] |
**include** | Option<**String**> | A comma-separated list of additional data modules to include in the response. Requesting more modules may increase latency. |  |

### Return type

[**models::IndicatorResponse**](IndicatorResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_indicator_graph

> get_indicator_graph(r#type, value, limit)
Get Infrastructure Relationship Graph

<p>Returns graph visualization data showing relationships between the indicator and related infrastructure. Perfect for interactive network diagrams and threat actor infrastructure mapping.</p> <h4>Relationship Types Included:</h4> <ul>     <li><b>For Domains:</b>         <ul>             <li>Resolves to IPs</li>             <li>Shares nameservers with</li>             <li>Same SSL certificate as</li>             <li>Same registrant as</li>             <li>Links to/from other domains</li>         </ul>     </li>     <li><b>For IPs:</b>         <ul>             <li>Hosts domains</li>             <li>Same ASN as</li>             <li>Same network block as</li>             <li>Connected via routing</li>         </ul>     </li> </ul> <h4>Output Format:</h4> <p>Compatible with react-force-graph, vis.js, cytoscape.js:</p> <pre><code>{   \"nodes\": [     {\"id\": \"example.com\", \"type\": \"domain\", \"label\": \"example.com\"},     {\"id\": \"8.8.8.8\", \"type\": \"ip\", \"label\": \"8.8.8.8\"}   ],   \"links\": [     {\"source\": \"example.com\", \"target\": \"8.8.8.8\", \"type\": \"resolves_to\"}   ] }</code></pre> <h4>Performance:</h4> <ul>     <li>Response Time: 500ms-2s depending on graph complexity</li>     <li>Default: 100 nodes maximum (adjustable)</li> </ul> <h4>Use Cases:</h4> <ul>     <li>Interactive threat actor infrastructure visualization</li>     <li>Discovering related phishing campaigns</li>     <li>Mapping shadow IT and sprawl</li>     <li>Network topology visualization</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**r#type** | **String** | Type of indicator | [required] |
**value** | **String** | The indicator value (IP address or domain) | [required] |
**limit** | Option<**i32**> | Maximum number of nodes to return in the graph |  |[default to 100]

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_indicator_history

> models::HistoryResponse get_indicator_history(r#type, value, history_type)
Get Historical Data for Indicator

<p>Retrieves time-series historical data for an IP address or domain. Track how infrastructure changes over time for threat intelligence and forensic analysis.</p> <h4>History Types:</h4> <ul>     <li><b>whois:</b> Registration history - registrant changes, expiration updates, transfers</li>     <li><b>routing:</b> BGP routing history - prefix announcements, ASN changes, route hijacks</li>     <li><b>dns:</b> DNS resolution history - IP address changes, nameserver updates</li>     <li><b>ssl:</b> Certificate history - cert replacements, CA changes, expiration events</li>     <li><b>reputation:</b> Risk score history - blacklist appearances, reputation changes</li> </ul> <h4>Data Format:</h4> <p>Timeline with dated snapshots showing what changed and when:</p> <pre><code>{   \"history\": [     {       \"timestamp\": \"2025-01-15T10:00:00Z\",       \"field\": \"registrant_company\",       \"old_value\": \"Evil Corp\",       \"new_value\": \"Legitimate LLC\"     }   ] }</code></pre> <h4>Use Cases:</h4> <ul>     <li>Tracking domain ownership changes</li>     <li>Investigating IP reputation degradation</li>     <li>Forensic timeline reconstruction</li>     <li>Detecting infrastructure pivots by threat actors</li> </ul> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**r#type** | **String** | Type of indicator | [required] |
**value** | **String** | The indicator value (IP address or domain) | [required] |
**history_type** | Option<**String**> | Type of historical data to retrieve |  |

### Return type

[**models::HistoryResponse**](HistoryResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_predictive_risk

> models::PredictiveRiskResponse get_predictive_risk(r#type, value)
Get AI Predictive Risk Score

<p>Returns ML-based predictive risk assessment for an IP address or domain. Provides current risk scoring, 7-day and 30-day predictions, risk trajectory analysis, and contributing factors.</p> <h4>Response Includes:</h4> <ul>     <li><b>Current Assessment:</b> Risk score (0-100), risk level, and confidence</li>     <li><b>Predictions:</b> 7-day and 30-day risk forecasts with confidence intervals</li>     <li><b>Trajectory:</b> Trend direction (improving/stable/worsening), velocity, stability</li>     <li><b>Risk Factors:</b> Contributing factors with weights and descriptions</li>     <li><b>Early Warnings:</b> Signals indicating potential future risk changes</li>     <li><b>Similar Cases:</b> Historical indicators with similar profiles and their outcomes</li> </ul> <h4>Risk Levels:</h4> <ul>     <li><b>low:</b> Score 0-30 - Minimal observed risk</li>     <li><b>medium:</b> Score 31-60 - Moderate risk, warrants monitoring</li>     <li><b>high:</b> Score 61-80 - Elevated risk, investigation recommended</li>     <li><b>critical:</b> Score 81-100 - Severe risk, immediate action advised</li> </ul> <h4>Performance:</h4> <p>Pre-computed ML predictions. Response time typically under 500ms with 15-minute cache.</p> 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**r#type** | **String** | Type of indicator | [required] |
**value** | **String** | The indicator value (IP address or domain) | [required] |

### Return type

[**models::PredictiveRiskResponse**](PredictiveRiskResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_subdomains

> models::SubdomainResponse get_subdomains(domain, limit)
Get Domain Subdomains

Retrieves a list of discovered subdomains for a given root domain, based on passive DNS and other enumeration techniques.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**domain** | **String** | The root domain to query for subdomains. | [required] |
**limit** | Option<**i32**> | The maximum number of subdomains to return. |  |[default to 100]

### Return type

[**models::SubdomainResponse**](SubdomainResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

