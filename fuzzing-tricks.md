#### Find Hidden Endpoints
 - Append `_` before the payload.
```css
▶ ffuf -w wordlist.txt -u target.com/_FUZZ
```

- Append `_/` before the payload.
```css
▶ ffuf -w wordlist.txt -u target.com/_/FUZZ
```
