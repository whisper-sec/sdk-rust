# DomainReputationDetails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain_ips** | Option<**Vec<String>**> | Domain's A record IP addresses | [optional]
**domain_ip_scores** | Option<**std::collections::HashMap<String, f64>**> | Individual scores for each domain IP | [optional]
**nameserver_domains** | Option<**Vec<String>**> | Nameserver domain names | [optional]
**nameserver_ips** | Option<**Vec<String>**> | IP addresses of nameservers | [optional]
**nameserver_ip_scores** | Option<**std::collections::HashMap<String, f64>**> | Individual scores for each nameserver IP | [optional]
**mailserver_domains** | Option<**Vec<String>**> | Mail server domain names | [optional]
**mailserver_ips** | Option<**Vec<String>**> | IP addresses of mail servers | [optional]
**mailserver_ip_scores** | Option<**std::collections::HashMap<String, f64>**> | Individual scores for each mail server IP | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


