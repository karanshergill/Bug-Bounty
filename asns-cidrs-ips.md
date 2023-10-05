[Autonomous System Numbers](https://www.iana.org/assignments/as-numbers/as-numbers.xhtml)

Search for ASN's belonging to an organization:
- https://bgp.he.net/
- https://asnlookup.com/
- https://asrank.caida.org/

Search for CIDR/IP Ranges belonging to an organization:
- [SPK](https://github.com/dhn/spk)




```shell
root@kali# spk -silent -json -s "Organization Name" | tee cidrs.json | jq -r .cidr | tee cidrs.txt
```
