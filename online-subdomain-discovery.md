# Find Subdomains Online

- https://subdomainfinder.c99.nl/
- http://api.subdomain.center/?domain=pwnstuff.com
- https://seckrd.com/subdomain-finder.php
- https://rapiddns.io/subdomain


# Parse RapidDNS Data
```CSS
cat rapiddns_data.csv | grep -i "cname" | awk -F ',' '{print $2}' > cname.data
```
```CSS
cat rapiddns_data.csv | grep -i "cname" | awk -F ',' '{print $3}' | sed 's/\.$//' >> cname.data 
```
```CSS
cat rapiddns_data.csv | grep -i -v "cname" | awk -F ',' '{print $2}' >> a.data
```
