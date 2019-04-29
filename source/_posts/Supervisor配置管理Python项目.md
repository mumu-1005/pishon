---
title: Supervisor配置管理Python项目
categories:
  - 'Server'
tags:
  - 'Supervisor'
  - 'Python'
comments: false
date: 2018-11-21 16:42:31
updated: 2018-11-21 16:42:31
---
<div hidden="true">Supervisor配置uwsgi基础示例，附加进程管理控制台常用命令</div>
<!-- more -->

## supervisord.conf
{% codeblock lang:ini hightlight:true %}
[unix_http_server]
file=/tmp/supervisor.sock   ; (the path to the socket file)
chmod=0700                 ; socket file mode (default 0700)

[inet_http_server]         ; inet (TCP) server disabled by default
port=*:8001
username=your_username              ; (default is no username (open server))
password=your_password              ; (default is no password (open server))

[supervisord]
logfile=/tmp/supervisord.log ; (main log file;default $CWD/supervisord.log)
logfile_maxbytes=50MB        ; (max main logfile bytes b4 rotation;default 50MB)
logfile_backups=10           ; (num of main logfile rotation backups;default 10)
loglevel=info                ; (log level;default info; others: debug,warn,trace)
pidfile=/tmp/supervisord.pid ; (supervisord pidfile;default supervisord.pid)
nodaemon=false               ; (start in foreground if true;default false)
minfds=1024                  ; (min. avail startup file descriptors;default 1024)
minprocs=200                 ; (min. avail process descriptors;default 200)
environment=MONGO_URL="mongodb://reminder:geN-aud-veff@127.0.0.1:27017/reminder"

[rpcinterface:supervisor]
supervisor.rpcinterface_factory = supervisor.rpcinterface:make_main_rpcinterface

[supervisorctl]
serverurl=unix:///tmp/supervisor.sock ; use a unix:// URL  for a unix socket

[program:program_name]
directory=/program_dir
command=uwsgi -w program_name_product --ini program_name.ini --uid role
startsecs=2
numproces=2
stopasgroup=true
autostart=false
autorestart=true
stderr_logfile=/tmp/log/program_name_error.log
stdout_logfile=/tmp/log/program_name_access.log

[program:program_name_n]
directory=/program_n_dir
command=command_n
startsecs=2
numproces=2
stopasgroup=true
autostart=false
autorestart=true
stderr_logfile=/tmp/log/program_name_n_error.log
stdout_logfile=/tmp/log/program_name_n_access.log
{% endcodeblock %}
<hr>



## 进程管理控制台常用命令
{% codeblock lang:yaml hightlight:true %}
- supervisorctl # 进入控制台

- start all   # 启动配置文件中的所有进程
- stop all    # 停止配置文件中的所有进程
- restart all # 重启配置文件中的所有进程

- start program_name   # 启动进程
- stop program_name    # 停止进程
- restart program_name # 重启进程

- start groupworker:   # 启动所有属于名为 groupworker 这个分组的进程
- stop groupworker:    # 结束所有属于名为 groupworker 这个分组的进程
- restart groupworker: # 重启所有属于名为 groupworker 这个分组的进程

- start groupworker:name1   # 启动 groupworker:name1 这个进程
- stop groupworker:name1    # 结束 groupworker:name1 这个进程 
- restart groupworker:name1 # 重启 groupworker:name1 这个进程

- reload # 载入最新的配置文件，停止原有进程并按新的配置启动、管理所有进程

- update # 根据最新的配置文件，启动新配置或有改动的进程，配置没有改动的进程不会受影响而重启遇到问题
注：start、restartUnlinking stale socket /tmp/supervisor.sock、stop 都不会载入最新的配置文件

- exit # 退出supervisor控制台
{% endcodeblock %}