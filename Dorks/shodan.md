# Shodan Dorks

- `ssl.cert.subject.CN:`"*.target.com" `http.title:`"index of/"
- `ssl.cert.subject.CN:`"*.target.com" `http.title:`"gitlab"
- `ssl.cert.subject.CN:`"*.target.com" "230 login successful" port:"21"
- `ssl.cert.subject.CN:`"*.target.com" 200 `http.title:`"Admin"

### Search using hostname
- `hostname:"*.target.com"

### Search using AS Number
- `asn:31337`

### Others
- `"set-cookie: webvpn;"` `org:pwnstuff`
- `"230 login successful"` `port:"21"`
- `"vsftpd 2.3.4" "port:21"`
- `230 'anonymous@' login ok`
