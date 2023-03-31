# SSRF

1. List of Hosts
  - https://pwnstuff.com
  - https://hackme.in
  - https://vulnweb.com
  
2. Get URLs
  - Katana
    - To increase crawling depth use the `depth` option.
    - For enumerating endpoints from JS code use `js-crawl` option.
  - GauPlus
```CSS
▶ katana -no-color -system-chrome -list hosts.txt -concurrency 50 -output urls-katana.tmp
▶ cat hosts.txt | gauplus -t 50 -o urls-gauplus.tmp
```

3. Combine and Filter URLs
  - URLDedupe
```CSS
▶ cat uls-katana.tmp urls-gau.tmp >> urls-all.tmp
▶ urldedupe -u urls-all.tmp | tee urls.txt
```

---

4. GREP Patterns
  - GF
```CSS
▶ cat urls.txt | gf ssrf | tee ssrf-urls.txt
```

5. Launch InteractSH

6. Replace Query Strings
  - QSReplace
    - Replace query strings with `{interatsh-url}`.
  ```CSS
  ▶ cat ssrf-urls.txt | qsreplace {interatsh-url} | tee ssrf-urls-interactsh.txt
  ```

