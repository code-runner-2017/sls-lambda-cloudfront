How to use CloudFront to cache API GW / Lambda REST API.

Source: https://medium.com/yld-blog/caching-in-with-cloudfront-using-serverless-5a174651ab14

```
sls deploy
```
```
curl -i https://<API_GW_ENDPOINT>/dev/my/cool/path
```

You always get: `X-Cache: Miss from cloudfront`

```
curl -i https://<YOUR_CLOUDFRONT_DISTRIBUTION>.cloudfront.net/my/cool/path
```

*NOTE*: the `/dev` prefix must be removed.

First time, you get: `X-Cache: Miss from cloudfront`.
Next calls, you get: `X-Cache: Hit from cloudfront` until the cache expires.

