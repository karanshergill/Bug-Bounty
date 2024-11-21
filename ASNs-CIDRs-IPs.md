[Autonomous System Numbers](https://www.iana.org/assignments/as-numbers/as-numbers.xhtml) (ASN)

### ASN's
AS Numbers belonging to an organization the below search engines can be used.
I do this manually as automated tools often throw false positive results.

- https://bgp.he.net/
- https://asnlookup.com/
- https://asrank.caida.org/

---

### CIDR/IP Ranges 
CIDR/IP Ranges associated with ASN's.

- Returns IPv4 and IPv6 prefixes
```http
curl -s "https://stat.ripe.net/data/announced-prefixes/data.json?resource=AS12345" | jq '.data.prefixes[].prefix'
```

- Returns only IPv4 prefixes
```http
curl -s "https://stat.ripe.net/data/announced-prefixes/data.json?resource=AS31004" | jq -r '.data.prefixes[] | select(.prefix | contains(":") | not) | .prefix'
```

---

### IP's
Expand the CIDR/IP Ranges to IP addresses.
- [MapCIDR](https://github.com/projectdiscovery/mapcidr)

Single CIDR Range:
```shell
mapcidr -cidr 0.0.0.0/24 -skip-base -skip-broadcast | tee -a ips.txt
```
List of CIDR Ranges:
```shell
while IFS= read -r CIDR; do mapcidr -cidr "$CIDR" -skip-base -skip-broadcast; done < cidrs.txt | tee -a ips.txt
```

---

