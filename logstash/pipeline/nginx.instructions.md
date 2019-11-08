Modify file config

```
http {
    log_format apm '$remote_addr - $remote_user [$time_local] '
                             '"$request" $status $body_bytes_sent '
                             '"$http_referer" "$http_user_agent"'
                             'rt=$request_time rl=$request_length uct="$upstream_connect_time" uht="$upstream_header_time" urt="$upstream_response_time"';

    server {
        access_log /var/logs/nginx/access.log apm;
        ...
    }
}
```
