

### Subdomain Resolution
```CSS
httpx -list target-subdomains.txt -status-code -ip -cname -tech-detect --threads 25 -rate-limit 50 -delay 100ms -timeout 10 -resolvers resolvers.txt -output target-subdomains.httpx
```
