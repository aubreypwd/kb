# How to redirect uploads in NGINX for WordPress

```
set $production_domain example.com;
location @production_uploads {
    rewrite "^(.*)/wp-content/uploads/(.*)$" "https://$production_domain/wp-content/uploads/$2" break;
}
location ~ "^/wp-content/uploads/(.*)$" {
    try_files $uri @production_uploads;
}
```
