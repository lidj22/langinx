# LANginx

LAN-only Docker applications with basic self-signed, HTTPS Nginx configuration. Intended as templates/starting points for LAN-based applications.

Basic Nginx server configuration:
```nginx
server {
    listen 443 ssl;
    server_name $SERVER_NAME;

    ssl_certificate /certs/staging/$SERVER_CERTIFICATE;
    ssl_certificate_key /certs/staging/$SERVER_CERTIFICATE_KEY;
    add_header Strict-Transport-Security "max-age=31536000; includeSubDomains; preload";

    location / {
        proxy_pass http://$SERVER:$SERVER_PORT;
        proxy_set_header Host $host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_set_header X-Forwarded-Host $host;
    }
}
```