<div align="center">
  <img src="Whisper_Logo.png" alt="Whisper Logo" width="400"/>

  # Whisper API SDK - Rust

[![CI](https://github.com/whisper-sec/sdk-rust/actions/workflows/ci.yml/badge.svg)](https://github.com/whisper-sec/sdk-rust/actions/workflows/ci.yml)
[![Crates.io](https://img.shields.io/crates/v/whisper_api_sdk.svg)](https://crates.io/crates/whisper_api_sdk)
[![Documentation](https://docs.rs/whisper_api_sdk/badge.svg)](https://docs.rs/whisper_api_sdk)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

> **Official Rust SDK for Whisper API** - Comprehensive threat intelligence and security operations for domains, IPs, and web infrastructure.

**[Website](https://www.whisper.security)** | **[Documentation](https://docs.whisper.security)** | **[API Reference](https://developer.whisper.security)** | **[API Playground](https://dash.whisper.security/playground)** | **[Contact Us](https://www.whisper.security/contactus)**

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
use whisper_api_sdk::apis::indicators_api;

#[tokio::main]
async fn main() -> Result<(), Box<dyn std::error::Error>> {
    let mut config = Configuration::new();
    config.bearer_access_token = Some("YOUR_API_KEY".to_string());

    // Enrich an IP address
    let response = indicators_api::get_indicator(&config, "ip", "8.8.8.8", None).await?;
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

### Indicators API
Enrich IPs and domains with comprehensive threat intelligence.

```rust
// Basic enrichment
let ip_data = indicators_api::get_indicator(&config, "ip", "8.8.8.8", None).await?;

// With additional data modules
let domain_data = indicators_api::get_indicator(&config, "domain", "example.com", Some("whois,dns_details")).await?;

// Get relationship graph
let graph = indicators_api::get_indicator_graph(&config, "ip", "8.8.8.8").await?;

// Predictive risk score
let risk = indicators_api::get_predictive_risk(&config, "ip", "8.8.8.8").await?;
```

### Location API
Geolocation lookups and network analysis.

```rust
use whisper_api_sdk::apis::location_api;

// Single IP geolocation
let location = location_api::get_ip_location(&config, "8.8.8.8").await?;

// Network/CIDR lookup
let network = location_api::get_network_location(&config, "8.8.8.0/24").await?;

// Search by attributes
let results = location_api::search_location(&config, Some("city"), Some("San Francisco"), Some(100)).await?;
```

### Operations API
Async operations for scanning, monitoring, and AI-powered analysis.

```rust
use whisper_api_sdk::apis::operations_api;

// Screenshot capture (async job)
let job = operations_api::create_screenshot(&config, screenshot_request).await?;

// Infrastructure scan
let scan_job = operations_api::create_infrastructure_scan(&config, scan_request).await?;

// Check job status
let status = operations_api::get_job(&config, &job.job_id).await?;

// AI-powered investigation
let investigation = operations_api::ai_investigate(&config, investigate_request).await?;
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
| Standard Enrichment | 100 req/min |
| Bulk Operations | 10 req/min |
| Search/Discovery | 5 req/min |
| Screenshots | 10 req/min |

Rate limits return HTTP 429 with a `Retry-After` header.

---

## Documentation

- **API Documentation**: [docs.whisper.security](https://docs.whisper.security)
- **API Reference**: [developer.whisper.security](https://developer.whisper.security)
- **Rust Docs**: [docs.rs/whisper_api_sdk](https://docs.rs/whisper_api_sdk)

---

## Support

- **Email**: [support@whisper.security](mailto:support@whisper.security)
- **Issues**: [github.com/whisper-sec/sdk-rust/issues](https://github.com/whisper-sec/sdk-rust/issues)

---

## License

MIT License - See [LICENSE](LICENSE) file for details.

---

*Built with Rust by Whisper Security*
