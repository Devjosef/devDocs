# NGINX

## Introduction
NGINX is a high-performance HTTP server, reverse proxy, and IMAP/POP3 proxy server. It is known for its stability, rich feature set, simple configuration, and low resource consumption.

## Basic Syntax
```nginx
# Example of a basic NGINX configuration
server {
    listen 80;
    server_name example.com;

    location / {
        proxy_pass http://localhost:3000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

## Common Use Cases
- Serving static content
- Reverse proxying
- Load balancing
- SSL termination

## Advanced Features
- **Load Balancing**: Distribute traffic across multiple servers.
- **Caching**: Cache responses to improve performance.
- **Security**: Implement security features like rate limiting and access control.
- **Modules**: Extend NGINX functionality with various modules.

## Code Snippets
### Load Balancing
```nginx
# Example of a load balancing configuration
upstream backend {
    server backend1.example.com;
    server backend2.example.com;
}

server {
    listen 80;
    server_name example.com;

    location / {
        proxy_pass http://backend;
    }
}
```

### Caching
```nginx
# Example of a caching configuration
proxy_cache_path /data/nginx/cache levels=1:2 keys_zone=my_cache:10m max_size=1g inactive=60m use_temp_path=off;

server {
    listen 80;
    server_name example.com;

    location / {
        proxy_cache my_cache;
        proxy_pass http://localhost:3000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

### SSL Termination
```nginx
# Example of an SSL termination configuration
server {
    listen 443 ssl;
    server_name example.com;

    ssl_certificate /etc/nginx/ssl/example.com.crt;
    ssl_certificate_key /etc/nginx/ssl/example.com.key;

    location / {
        proxy_pass http://localhost:3000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

## Tips & Best Practices
- **Use Upstreams**: Use upstream blocks to manage backend servers.
- **Enable Gzip Compression**: Enable gzip compression to reduce response sizes.
- **Monitor Performance**: Use tools like NGINX Amplify to monitor performance.
- **Security**: Implement security best practices like rate limiting and access control.
- **Configuration Management**: Use configuration management tools to manage NGINX configurations.

## External Resources
- [NGINX Official Documentation](https://nginx.org/en/docs/)
- [NGINX Configuration Guide](https://www.digitalocean.com/community/tutorials/understanding-the-nginx-configuration-file-structure-and-configuration-contexts)
- [NGINX Best Practices](https://www.nginx.com/resources/wiki/start/topics/tutorials/config_pitfalls/)
- [NGINX GitHub Repository](https://github.com/nginx/nginx)