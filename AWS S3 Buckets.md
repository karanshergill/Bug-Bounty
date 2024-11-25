## URL format for S3 buckets:
- `http://[bucket_name].s3.amazonaws.com/`
- `http://s3.amazonaws.com/[bucket_name]/`

## Identifying S3 buckets:
- Hardcoded URLs of buckets in the HTML
- Search Engine Dorking (Google/ Bing/ DuckDuckGo/ Brave)
- Reverse IP lookup (Bing reverse IP)
- Brute-Force
- DNS Caching

## Examine HTTP response headers and body:
- HTTP response headers contains any of the below headers.
```javascript
x-amz-bucket-region
x-amz-request-id
x-amz-id-2
```

- References and Links included in the body to load images etc.
```javascript
\.s3\.amazonaws\.com\/?
```

## Testing and Abusing Permissions:
- Read Permission
- Write Permission
- Read Access Control Lists (ACP)
- Write Access Control Lists (ACP)
- Full Control



## Practice:
- http://flaws.cloud.s3-website-us-west-2.amazonaws.com/