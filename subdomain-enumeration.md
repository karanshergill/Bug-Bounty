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
```CSS
httpx -list <target-subdomains>.lst -status-code -ip -cname -tech-detect -threads 25 -rate-limit 50 -delay 100ms -timeout 10 -resolvers resolvers.txt -output <target-subdomains>.httpx
```
