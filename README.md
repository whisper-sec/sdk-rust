<div align="center">
  <img src="Whisper_Logo.png" alt="Whisper Logo" width="400"/>

  # Whisper API SDK - Rust

[![CI](https://github.com/whisper-sec/sdk-rust/actions/workflows/ci.yml/badge.svg)](https://github.com/whisper-sec/sdk-rust/actions/workflows/ci.yml)
[![Crates.io](https://img.shields.io/crates/v/whisper_api_sdk.svg)](https://crates.io/crates/whisper_api_sdk)
[![Documentation](https://docs.rs/whisper_api_sdk/badge.svg)](https://docs.rs/whisper_api_sdk)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

> **Official Rust SDK for Whisper API** - Comprehensive threat intelligence and security operations for domains, IPs, and web infrastructure.

**[Website](https://whisper.security)** | **[Dashboard](https://dash.whisper.security)** | **[Documentation](https://docs.whisper.security)** | **[API Reference](https://developer.whisper.security)** | **[API Playground](https://dash.whisper.security/playground)** | **[Contact Us](https://whisper.security/contactus)**

</div>

---

## Quick Start

### Installation

Add to your `Cargo.toml`:

```toml
[dependencies]
whisper_api_sdk = "0.1.0"
tokio = { version = "1", features = ["full"] }
```

### Get Your API Key

Sign up at [dash.whisper.security](https://dash.whisper.security) to get your API key.

### First Request

```rust
use whisper_api_sdk::apis::configuration::Configuration;
use whisper_api_sdk::apis::enrichment_api;

#[tokio::main]
async fn main() -> Result<(), Box<dyn std::error::Error>> {
    let mut config = Configuration::new();
    config.bearer_access_token = Some("YOUR_API_KEY".to_string());

    // Enrich an IP address
    let response = enrichment_api::get_indicator(&config, "ip", "8.8.8.8", None).await?;
    println!("Response: {:?}", response);

    Ok(())
}
```

---

## Key Features

- **Async/Await** - Built on tokio and reqwest for non-blocking I/O
- **Type Safe** - Strongly typed models with serde serialization
- **Comprehensive** - IP, Domain, DNS, WHOIS, Routing, Geolocation, Screenshots, AI/ML
- **Fast** - Sub-500ms typical response times with strategic caching
- **Production Ready** - Error handling, retries, and timeout configuration

---

## API Overview

### Enrichment API
Enrich IPs and domains with comprehensive threat intelligence.

```rust
use whisper_api_sdk::apis::enrichment_api;

// Basic enrichment
let ip_data = enrichment_api::get_indicator(&config, "ip", "8.8.8.8", None).await?;

// With additional data modules
let domain_data = enrichment_api::get_indicator(
    &config, "domain", "example.com", Some("whois,dns_details,routing,rpki")
).await?;

// Get relationship graph
let graph = enrichment_api::get_indicator_graph(&config, "ip", "8.8.8.8").await?;

// Historical data
let history = enrichment_api::get_indicator_history(&config, "domain", "example.com", Some(10)).await?;

// Predictive risk score (AI-powered)
let risk = enrichment_api::get_predictive_risk(&config, "ip", "8.8.8.8").await?;

// Subdomain discovery
let subdomains = enrichment_api::get_subdomains(&config, "example.com", Some(100)).await?;

// Bulk enrichment (async job)
let job = enrichment_api::bulk_enrichment(&config, bulk_request).await?;

// Search by WHOIS fields
let search_job = enrichment_api::search_indicators(&config, search_request).await?;

// Similar/typosquat domain generation
let similar_job = enrichment_api::similar_domains(&config, similar_request).await?;
```

### Location API
Geolocation lookups and network analysis.

```rust
use whisper_api_sdk::apis::location_api;

// Single IP geolocation
let location = location_api::get_ip_location(&config, "8.8.8.8").await?;

// Bulk geolocation (up to 1000 IPs)
let bulk_result = location_api::get_bulk_ip_location(&config, bulk_request).await?;

// Network/CIDR lookup
let network = location_api::get_network_location(&config, "8.8.8.0/24").await?;

// Search by attributes
let results = location_api::search_location(&config, Some("city"), Some("San Francisco"), Some(100)).await?;

// Location statistics
let stats = location_api::get_location_stats(&config).await?;
```

### Screenshots API
Capture and schedule website screenshots.

```rust
use whisper_api_sdk::apis::screenshots_api;

// Screenshot capture (returns job ID)
let job = screenshots_api::create_screenshot(&config, screenshot_request).await?;

// Schedule recurring screenshots
let schedule = screenshots_api::schedule_screenshot(&config, schedule_request).await?;

// Get screenshot history
let history = screenshots_api::get_screenshot_history(&config, Some("https://example.com"), None, None).await?;

// List scheduled screenshots
let schedules = screenshots_api::list_screenshot_schedules(&config).await?;
```

### AI Intelligence API
AI-powered threat investigation and analysis.

```rust
use whisper_api_sdk::apis::ai_intelligence_api;

// Industry security benchmark (synchronous)
let benchmark = ai_intelligence_api::get_industry_benchmark(&config, "financial_services", Some("enterprise"), None).await?;

// AI-powered investigation (async job)
let investigation = ai_intelligence_api::ai_investigate(&config, investigate_request).await?;

// Find similar threat cases
let cases = ai_intelligence_api::find_similar_cases(&config, similar_cases_request).await?;

// Infrastructure pivoting
let pivot = ai_intelligence_api::ai_pivot(&config, pivot_request).await?;

// Threat actor attribution
let attribution = ai_intelligence_api::ai_attribute(&config, attribute_request).await?;

// Global indicator correlation
let correlation = ai_intelligence_api::ai_correlate(&config, correlate_request).await?;
```

### Infrastructure Scanning API
Discover and analyze infrastructure.

```rust
use whisper_api_sdk::apis::infrastructure_scanning_api;

// Infrastructure scan (SSL, technologies, subdomains, ports)
let scan_job = infrastructure_scanning_api::create_infrastructure_scan(&config, scan_request).await?;

// Infrastructure relationship mapping
let map_job = infrastructure_scanning_api::create_infrastructure_map(&config, map_request).await?;
```

### Monitoring API
Uptime and availability monitoring.

```rust
use whisper_api_sdk::apis::monitoring_api;

// Create monitoring check
let check = monitoring_api::create_monitor_check(&config, monitor_request).await?;

// List monitoring checks
let checks = monitoring_api::list_monitor_checks(&config).await?;

// Get dashboard summary
let dashboard = monitoring_api::get_monitor_dashboard(&config).await?;

// Configure alerts
monitoring_api::create_monitoring_alert(&config, check_id, alert_request).await?;
```

### Change Tracking API
Monitor indicators for changes.

```rust
use whisper_api_sdk::apis::change_tracking_api;

// Start tracking an indicator
change_tracking_api::start_change_tracking(&config, "domain", "example.com", tracking_request).await?;

// Get detected changes
let changes = change_tracking_api::get_changes(&config, "domain", "example.com").await?;

// List tracked indicators
let tracked = change_tracking_api::list_tracked_indicators(&config).await?;

// Trigger immediate check
change_tracking_api::trigger_check(&config, "domain", "example.com").await?;
```

### Graph Database API
Direct access to the threat intelligence graph.

```rust
use whisper_api_sdk::apis::graph_database_api;

// Execute Cypher query
let result = graph_database_api::execute_cypher_query(&config, cypher_request).await?;

// Execute GraphQL query
let graphql_result = graph_database_api::execute_graph_ql(&config, graphql_request).await?;

// Get graph schema
let schema = graph_database_api::get_schema(&config).await?;

// Check graph health
let health = graph_database_api::get_health(&config).await?;
```

### Jobs API
Manage async operations.

```rust
use whisper_api_sdk::apis::jobs_api;

// Get job status and results
let job = jobs_api::get_job(&config, &job_id).await?;

// List your jobs
let jobs = jobs_api::list_jobs(&config).await?;
```

---

## Authentication

All endpoints require Bearer token authentication:

```rust
let mut config = Configuration::new();
config.bearer_access_token = Some(std::env::var("WHISPER_API_KEY")?);
```

---

## Rate Limits

| Category | Limit |
|----------|-------|
| Indicators (`/v1/indicators/*`) | 100 req/sec |
| Location (`/v1/location/*`) | 100 req/sec |
| Jobs (`/v1/ops/jobs/*`) | 100 req/sec |
| Bulk Operations | 10 req/sec |
| Screenshots | 10 req/sec |
| Scans | 10 req/sec |
| Monitoring | 10 req/sec |
| Change Tracking | 10 req/sec |
| AI Operations | 5 req/min |

Rate limits return HTTP 429 with a `Retry-After` header.

---

## Documentation

- **API Documentation**: [docs.whisper.security](https://docs.whisper.security)
- **API Reference**: [developer.whisper.security](https://developer.whisper.security)
- **Rust Docs**: [docs.rs/whisper_api_sdk](https://docs.rs/whisper_api_sdk)

---

## Other SDKs

- **Python**: [github.com/whisper-sec/sdk-python](https://github.com/whisper-sec/sdk-python)
- **TypeScript/JavaScript**: [github.com/whisper-sec/sdk-typescript](https://github.com/whisper-sec/sdk-typescript)
- **Java**: [github.com/whisper-sec/sdk-java](https://github.com/whisper-sec/sdk-java)
- **C#/.NET**: [github.com/whisper-sec/sdk-csharp](https://github.com/whisper-sec/sdk-csharp)

---

## Support

- **Email**: [support@whisper.security](mailto:support@whisper.security)
- **Issues**: [github.com/whisper-sec/sdk-rust/issues](https://github.com/whisper-sec/sdk-rust/issues)

---

## License

MIT License - See [LICENSE](LICENSE) file for details.

---

*Built with Rust by [Whisper Security](https://whisper.security)*
