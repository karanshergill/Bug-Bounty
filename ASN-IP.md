**Discovering IP Space**
- Obtaining the ASN Number from [BGP](https://bgp.he.net/) for a target domain.
- Find out the IP ranges that reside inside an ASN.
- Reverse DNS lookup using PTR records.

```CSS
while read -r asn; do whois -h whois.radb.net -- "-i origin $asn" | grep -Eo "([0-9.]+){4}/[0-9]+"; done < asns.txt | tee ip-ranges.txt
```


**Full Port Scan**
```CSS
▶ sudo masscan <TARGET> --src-port 53 -p0-65535 --exclude 255.255.255.255 --rate 5000 --output-format json --output-filename iprange-masscan.json
```
  - Target Specification
    - IP
    - CIDR

**Parse Masscan JSON Output**
```CSS
▶ cat iprange-masscan.json | !%!jq -r '.[] | "\(.ip):\(.ports[0].port)"':write ip-ports.txt
```

