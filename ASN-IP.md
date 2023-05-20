```CSS
▶ sudo masscan <TARGET> --src-port 53 -p0-65535 --exclude 255.255.255.255 --rate 5000 --output-format json --output-filename iprange-masscan.json
```
  - Target Specification
    - IP
    - CIDR
