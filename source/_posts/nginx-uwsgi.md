---
title: Nginx+uWSGI部署多个Django项目
categories:
  - 'server'
tags:
  - 'Nginx'
  - 'uWSGI'
comments: false
date: 2018-11-21 11:02:33
updated: 2018-11-21 11:12:33
---

## uWSGI配置
### project_1 的 uWSGI 的配置文件  project_1.ini
{% codeblock %}
[uwsgi]

chdir           = /project_1/

module          = project_1.wsgi

master          = true

processes       = 10

socket          = /project_1/project_1.sock

chmod-socket    = 666
chown-socket    = role_1:role_1

enable-threads=true

die-on-term = true
{% endcodeblock %}

### project_n 的 uWSGI 的配置文件  project_n.ini
{% codeblock %}
[uwsgi]

chdir           = /project_n/

module          = project_n.wsgi

master          = true

processes       = 10

socket          = /project_n/project_n.sock

chmod-socket    = 666
chown-socket    = role_n:role_n

enable-threads=true

die-on-term = true
{% endcodeblock %}
<hr>

## Nginx配置
### nginx.conf
{% codeblock %}
server {
    listen   80; 

    root /usr/share/nginx/www/public;
    index index.php index.html index.htm;

    server_name 127.0.0.1 x.x.x.x;
    include blocksip.conf;
    location / {
        try_files $uri $uri/ /index.html;
    }

    error_page 404 /404.html;

    location /project_1 {
        include     uwsgi_params; # the uwsgi_params file you installed
        uwsgi_pass  unix:/project_1/project_1.sock;
        uwsgi_param SCRIPT_NAME         /project_1;
        uwsgi_param UWSGI_SCRIPT        project_1.wsgi;
        uwsgi_modifier1                 30;
        uwsgi_read_timeout 1800s;
        uwsgi_send_timeout 1800s;
    }

    location /project_1/media/ {
        alias /usr/share/nginx/www/django_static/project_1/media/;
    }

    location /project_1/static/ {
        alias /usr/share/nginx/www/django_static/project_1/;
    }

    location /apk/ {
        alias /usr/share/nginx/www/django_static/project_1/apk/online/;
    }
    
    location /project_n {
        include     uwsgi_params; # the uwsgi_params file you installed
        uwsgi_pass  unix:/project_n/project_n.sock;
        uwsgi_param SCRIPT_NAME         /project_n;
        uwsgi_param UWSGI_SCRIPT        project_n.wsgi;
        uwsgi_modifier1                 30;
        uwsgi_read_timeout 1800s;
        uwsgi_send_timeout 1800s;
    }

    location /project_n/media/ {
        alias /usr/share/nginx/www/django_static/project_n/media/;
    }

    location /project_n/static/ {
        alias /usr/share/nginx/www/django_static/project_n/;
    }

    location /apk_project_n/ {
        alias /usr/share/nginx/www/django_static/project_n/apk/online/;
    }
}
{% endcodeblock %}
