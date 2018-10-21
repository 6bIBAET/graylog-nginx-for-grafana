# Graylog content pack for nginx for analysis in Grafana
This is partially based on the [Graylog content pack for nginx] https://github.com/graylog-labs/graylog-contentpack-nginx

Grafana Dashboard: https://grafana.com/dashboards/8486

How-to on Russian: https://itcrowd.top/graylog-nginx-grafana



### Configuring nginx
Add this in "/etc/nginx/nginx.conf" and restart server.

Replace IP-Address to own: 

log_format graylog2_format '$remote_addr - $remote_user [$time_local] "$request" $status $body_bytes_sent "$http_referer" "$http_user_agent" "$http_x_forwarded_for" $

access_log syslog:server=Graylog IP-Address:11004 graylog2_format;

error_log syslog:server=Graylog IP-Address:11005;