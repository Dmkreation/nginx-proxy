# nginx-proxy and ssl certificates
Thanks to :
- @jwilder for [jwilder/nginx-proxy](https://github.com/nginx-proxy/nginx-proxy)
- @nginxproxy for [nginxproxy/acme-companion](https://github.com/nginx-proxy/acme-companion)

## Usage
Do following to setup proxy and ssl certificates auto manger
```shell
git clone git@github.com:Dmkreation/nginx-proxy.git
cd nginx-proxy
docker compose up -d
```

Then, just add following config to all services do you want to expose and start them
```yaml
version: '3.4'

services:
  service-name:
    environment:
      VIRTUAL_HOST: mydomain.com
      LETSENCRYPT_HOST: mydomain.com
      VIRTUAL_PORT: 3000

networks:
  default:
    name: nginx-proxy
```