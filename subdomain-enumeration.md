### Passive Subdomain Enumeration
  - Subfinder
```CSS
subfinder -d <target.domain> -all -collect-sources -oJ -o <target.domain>.sub.json
```

#### Extract Subdomains
  - JSON to TXT
```CSS
jq -r '.host' <target.domain>.sub.json >> <target.domain>.subs.lst
```

### Subdomain Resolution
  - HTTPX
```CSS
httpx -list <target-subdomains>.subs.lst -status-code -ip -rate-limit 50 -delay 1ms -timeout 10 -resolvers resolvers.txt -output <target-subdomains>.httpx
```

