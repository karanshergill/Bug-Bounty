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
```https
curl -s "https://stat.ripe.net/data/announced-prefixes/data.json?resource=AS12345" | jq '.data.prefixes[].prefix'
```

- Returns only IPv4 prefixes
```javascript
curl -s "https://stat.ripe.net/data/announced-prefixes/data.json?resource=AS31004" | jq -r '.data.prefixes[] | select(.prefix | contains(":") | not) | .prefix'
```

---

### IP's
Expand the CIDR/IP Ranges to IP addresses.

```javascript
cat cidrs.txt | xargs -n 1 prips > expanded_ips.txt
```
---