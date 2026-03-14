# Week 01 — Advanced Reconnaissance & Attack Surface Mapping

## Objective
Conduct thorough passive reconnaissance on a target domain 
to identify its digital footprint without being detected.

##  Target
- **Domain:** vulnbank.org
- **IP Address:** 172.67.134.11
- **CDN/Proxy:** Cloudflare (confirmed)
- **Registrar:** Cloudflare Inc.
- **Domain Age:** Created July 2025 (8 months old)

## Tools Used
| Tool | Purpose |
|------|---------|
| Whois | Domain registration & ownership info |
| Ping | Confirm target is alive, identify IP |
| Subfinder | Passive subdomain enumeration |
| Assetfinder | Subdomain discovery via passive sources |
| Amass | Deep attack surface mapping |
| CRT.sh | SSL certificate transparency logs |
| Dig | DNS record enumeration |

## Findings

### Whois Analysis
| Field | Value | Significance |
|-------|-------|-------------|
| Registrar | Cloudflare Inc | Domain behind Cloudflare proxy |
| Created | 2025-07-05 | Very new domain |
| Name Servers | lauryn.ns.cloudflare.com | Cloudflare DNS confirmed |

### Subdomain Enumeration Results
| Tool | Subdomains Found | Notes |
|------|-----------------|-------|
| Subfinder | 0 | Missing API keys, Cloudflare blocking |
| Assetfinder | 0 | New domain, minimal passive data |
| Amass | Pending | - |
| CRT.sh | Pending | - |

## Key Learnings
1. Cloudflare hides real origin IPs behind proxy ranges (172.64.0.0/13)
2. New domains have minimal historical data in passive databases
3. API keys significantly improve subfinder's coverage
4. No single tool is sufficient — cross-referencing is essential
5. 0 results IS a valid finding — it tells you about the target's security posture

## Challenges Encountered
- Subfinder returned 0 results due to missing API keys
- Cloudflare WAF blocking automated enumeration
- Domain too new for significant passive intelligence

##  Recommendations
Proceed to active enumeration techniques including:
- DNS brute forcing with dnsx
- Web crawling with gospider
- Shodan search for historical IP exposure
  
