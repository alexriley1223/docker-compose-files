## Public-facing services
All public-facing web services are accessible through the Nginx Proxy Manager (npm) reverse proxy.

Assign to npm_proxy network and configure in NPM service:
```yaml
services:
  xyz:
    networks:
    - npm_proxy

networks:
  npm_proxy:
    external: true
```

NPM drives this network bridge via its compose file:
```yaml
networks:
  proxy:
    driver: bridge
```