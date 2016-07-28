# Nginx Secure proxy

### Info:

This templates creates a nginx proxy that automatically proxy in a secure way other container in the machine.

Images are the offical images from:
  * [jwilder/nginx-proxy](https://github.com/jwilder/nginx-proxy)
  * [JrCs/docker-letsencrypt-nginx-proxy-companion](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion)

### Usage:

  * Select Nginx Secure proxy from catalog.
  * Click deploy.
  * then you just have to set some env variable in the other container you launch and they will be automatically proxyfied with letsencrypt

For example :

```
rancher:
  image: rancher/server
  environment:
    - "VIRTUAL_PORT=8080"
    - "VIRTUAL_HOST=rancher.example.com"
    - "LETSENCRYPT_HOST=rancher.example.com"
    - "LETSENCRYPT_EMAIL=dev@example.com"
```