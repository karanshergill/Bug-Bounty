[Autonomous System Numbers](https://www.iana.org/assignments/as-numbers/as-numbers.xhtml)

### ASN's
Search for AS Numbers belonging to an organization the below search engines can be used. I do this manually as automated tools often throw false positive results.
- https://bgp.he.net/
- https://asnlookup.com/
- https://asrank.caida.org/

### CIDR/IP Ranges 
Find CIDR/IP Ranges associated with ASN's.
- [ASNMap](https://github.com/projectdiscovery/asnmap)
```shell
asnmap -a ASXXXXX -r ${RESOLVERS_TRUSTED} -o target-ip-ranges.txt
```

### IP's
Expand the CIDR/IP Ranges to IP addresses.
- [MapCIDR](https://github.com/projectdiscovery/mapcidr)
```
mapcidr -cl target-ip-ranges.txt -skip-base -skip-broadcast -o target-ipv4-addresses.txt
```
