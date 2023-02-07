# HTTP to HTTPS proxy

A simple nginx config to proxy HTTP to HTTPS. This is only needed because esp8266 with micropython can not perform https requests with ECDH certificates.

## Usage

Given you deploy this app to `proxy.foo.com`, then instead of

- https://422ddcf9-red.onrender.com/api/...

you will use now
- http://422ddcf9-red.onrender.com.proxy.foo.com/api/...


## Deploy

```bash
# on the dokku server
dokku apps:create proxy
dokku domains:add proxy proxy.foo.com
```

```bash
# on your local machine
git remote add dokku dokku@<your-ip>:proxy
git push -u dokku
```