### Passive Enumeration
  - Subfinder
```CSS
subfinder -d <target.domain> -all -collect-sources -oJ <target.domain>.sub.json
```

### Subdomain Resolution
```CSS
httpx -list <target-subdomains>.lst -status-code -ip -cname -tech-detect -threads 25 -rate-limit 50 -delay 100ms -timeout 10 -resolvers resolvers.txt -output <target-subdomains>.httpx
```
