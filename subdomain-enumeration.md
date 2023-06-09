### Passive Subdomain Enumeration
  - Amass
```CSS
amass enum -passive -d <target.domain> -json <target.domain>.amass.json
```
  - Subfinder
```CSS
subfinder -d <target.domain> -all -oJ -o <target.domain>.sub.json
```
  - GitHub Subdomains
```CSS
github-subdomains -d <target.domain> -o <target.domain>.sub.github.data -t <github-token>
```

#### Extract Subdomains from Amass Output
  - JSON to TXT
```CSS
jq -r '.host' <target.domain>.sub.json >> <target.domain>.subs.data
```

#### Extract Subdomains from Subfinder Output
  - JSON to TXT
```CSS
jq -r '.host' <target.domain>.sub.json >> <target.domain>.subs.data
```

#### DNS Resolution
```CSS
puredns resolve <target.domain>.subs.data --resolvers ../../resolvers.txt --rate-limit 500 --rate-limit-trusted 100 --write resolved_<target.domain>.subs.data
```


#### Certificate Transparency
  - TLSX - Exract CName and SAN
```CSS
tlsx -list <target.domain>.subs.data -cn -san -json -output <target.domain>.subs.lst.json.tlsx
```

#### DNS Resolution
  - ShuffleDNS
```CSS
shuffledns -list <target.domain>.subs.data -t 1000 -output <target.domain>.sdns.out
```
OR
  - DNSX
```CSS
dnsx -list <target.domain>.subs.lst -a -threads 25 -rate-limit 50 -retry 5 -resolver resolvers.txt -wildcard-domain target.domain -output <target.domain>.dnsx.out
```

### Subdomain Resolution
  - HTTPX
  - Common HTTP and HTTPS ports: `http:80,81,3000,3001,8000,8080,9000,9090,https:443,3000,3001,8443,9443,10000`
```CSS
httpx -list <target-subdomains>.subs.lst -status-code -ip -rate-limit 50 -delay 1ms -timeout 10 -resolvers resolvers.txt -output <target-subdomains>.httpx.out
```

#### Extract Active Hosts [200]
  - HTTPX to TXT
```CSS
cat <target-subdomains>.httpx.out | grep "\[200\]" | awk '{print $1}'
```

