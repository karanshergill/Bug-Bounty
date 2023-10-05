[Autonomous System Numbers](https://www.iana.org/assignments/as-numbers/as-numbers.xhtml)

### I. ASN's
Search for AS Numbers belonging to an organization the below search engines can be used. I do this manually as automated tools often throw false positive results.
- https://bgp.he.net/
- https://asnlookup.com/
- https://asrank.caida.org/

Write to a text file.
```shell
vim asns.txt
```

---

### II. CIDR/IP Ranges 
Find CIDR/IP Ranges associated with ASN's.
- [ASNMap](https://github.com/projectdiscovery/asnmap)

Single AS Number:
```shell
asnmap -asn ASXXXXX -resolvers ${RESOLVERS_TRUSTED} | tee -a cidr.txt
```
List of AS Numbers:
```shell
while IFS= read -r ASN; do asnmap -asn "$ASN" -resolvers ${RESOLVERS_TRUSTED}; done < asns.txt | tee -a cidrs.txt
```

---

### III. IP's
Expand the CIDR/IP Ranges to IP addresses.
- [MapCIDR](https://github.com/projectdiscovery/mapcidr)
```
mapcidr -cl target-ip-ranges.txt -skip-base -skip-broadcast -o target-ipv4-addresses.txt
```

---
```
