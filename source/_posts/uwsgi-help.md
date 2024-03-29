---
title: uwsgi命令
categories:
  - SERVER
tags:
  - server
  - uwsgi
  - help
comments: false
date: 2018-05-05 11:00:38
updated: 2019-02-05 21:00:02
img:
---
### UWSGI-CORE                                                               
``` sh
NAME
  - uwsgi-core - fast (pure C), self-healing, developer-friendly WSGI server
```

### User Commands
``` sh
       -s|--socket
              bind to the specified UNIX/TCP socket using default protocol
              指定socket，使用默认协议

       -s|--uwsgi-socket
              bind to the specified UNIX/TCP socket using uwsgi protocol
              指定socket，使用uwsgi协议

       --suwsgi-socket
              bind to the specified UNIX/TCP socket using uwsgi protocol over SSL
              指定socket，使用uwsgi绑定通过SSL安全套接字层

       --ssl-socket
              bind to the specified UNIX/TCP socket using uwsgi protocol over SSL
              指定socket，使用uwsgi协议通过SSL安全套接字层

       --http-socket
              bind to the specified UNIX/TCP socket using HTTP protocol
              指定socket，使用HTTP协议

       --http-socket-modifier1
              force the specified modifier1 when using HTTP protocol

       --http-socket-modifier2
              force the specified modifier2 when using HTTP protocol

       --https-socket
              bind to the specified UNIX/TCP socket using HTTPS protocol

       --https-socket-modifier1
              force the specified modifier1 when using HTTPS protocol

       --https-socket-modifier2
              force the specified modifier2 when using HTTPS protocol

       --fastcgi-socket
              bind to the specified UNIX/TCP socket using FastCGI protocol

       --fastcgi-nph-socket
              bind to the specified UNIX/TCP socket using FastCGI protocol (nph mode)

       --fastcgi-modifier1
              force the specified modifier1 when using FastCGI protocol

       --fastcgi-modifier2
              force the specified modifier2 when using FastCGI protocol

       --scgi-socket
              bind to the specified UNIX/TCP socket using SCGI protocol

       --scgi-nph-socket
              bind to the specified UNIX/TCP socket using SCGI protocol (nph mode)

       --scgi-modifier1
              force the specified modifier1 when using SCGI protocol

       --scgi-modifier2
              force the specified modifier2 when using SCGI protocol

       --raw-socket
              bind to the specified UNIX/TCP socket using RAW protocol

       --raw-modifier1
              force the specified modifier1 when using RAW protocol

       --raw-modifier2
              force the specified modifier2 when using RAW protocol

       --puwsgi-socket
              bind to the specified UNIX/TCP socket using persistent uwsgi protocol (puwsgi)

       --protocol
              force the specified protocol for default sockets

       --socket-protocol
              force the specified protocol for default sockets

       --shared-socket
              create a shared socket for advanced jailing or ipc

       --undeferred-shared-socket
              create a shared socket for advanced jailing or ipc (undeferred mode)

       -p|--processes
              spawn the specified number of workers/processes

       -p|--workers
              spawn the specified number of workers/processes

       --thunder-lock
              serialize accept() usage (if possible)

       -t|--harakiri
              set harakiri timeout

       --harakiri-verbose
              enable verbose mode for harakiri

       --harakiri-no-arh
              do not enable harakiri during after-request-hook

       --no-harakiri-arh
              do not enable harakiri during after-request-hook

       --no-harakiri-after-req-hook
              do not enable harakiri during after-request-hook

       --backtrace-depth
              set backtrace depth

       --mule-harakiri
              set harakiri timeout for mule tasks

       -x|--xmlconfig
              load config from xml file

       -x|--xml
              load config from xml file

       --config
              load configuration using the pluggable system

       --fallback-config
              re-exec uwsgi with the specified config when exit code is 1

       --strict
              enable strict mode (placeholder cannot be used)

       --skip-zero
              skip check of file descriptor 0

       --skip-atexit
              skip atexit hooks (ignored by the master)

       --skip-atexit-teardown
              skip atexit teardown (ignored by the master)

       -S|--set
              set a placeholder or an option

       --set-placeholder
              set a placeholder

       --set-ph
              set a placeholder

       --get  print the specified option value and exit

       --declare-option
              declare a new uWSGI custom option

       --declare-option2
              declare a new uWSGI custom option (non-immediate)

       --resolve
              place  the  result  of  a dns query in the specified placeholder, sytax: placeholder=name
              (immediate option)

       --for  (opt logic) for cycle

       --for-glob
              (opt logic) for cycle (expand glob)

       --for-times
              (opt logic) for cycle (expand the specified num to a list starting from 1)

       --for-readline
              (opt logic) for cycle (expand the specified file to a list of lines)

       --endfor
              (opt logic) end for cycle

       --end-for
              (opt logic) end for cycle

       --if-opt
              (opt logic) check for option

       --if-not-opt
              (opt logic) check for option

       --if-env
              (opt logic) check for environment variable

       --if-not-env
              (opt logic) check for environment variable

       --ifenv
              (opt logic) check for environment variable

       --if-reload
              (opt logic) check for reload

       --if-not-reload
              (opt logic) check for reload

       --if-hostname
              (opt logic) check for hostname

       --if-not-hostname
              (opt logic) check for hostname

       --if-hostname-match
              (opt logic) try to match hostname against a regular expression

       --if-not-hostname-match
              (opt logic) try to match hostname against a regular expression

       --if-exists
              (opt logic) check for file/directory existence

       --if-not-exists
              (opt logic) check for file/directory existence

       --ifexists
              (opt logic) check for file/directory existence

       --if-plugin
              (opt logic) check for plugin

       --if-not-plugin
              (opt logic) check for plugin

       --ifplugin
              (opt logic) check for plugin

       --if-file
              (opt logic) check for file existance

       --if-not-file
              (opt logic) check for file existance

       --if-dir
              (opt logic) check for directory existance

       --if-not-dir
              (opt logic) check for directory existance

       --ifdir
              (opt logic) check for directory existance

       --if-directory
              (opt logic) check for directory existance

       --endif
              (opt logic) end if

       --end-if
              (opt logic) end if

       --blacklist
              set options blacklist context

       --end-blacklist
              clear options blacklist context

       --whitelist
              set options whitelist context

       --end-whitelist
              clear options whitelist context

       --ignore-sigpipe
              do not report (annoying) SIGPIPE

       --ignore-write-errors
              do not report (annoying) write()/writev() errors

       --write-errors-tolerance
              set the maximum number of allowed write errors (default: no tolerance)

       --write-errors-exception-only
              only raise an exception on write errors giving control to the app itself

       --disable-write-exception
              disable exception generation on write()/writev()

       --inherit
              use the specified file as config template

       --include
              include the specified file as immediate configuration

       --inject-before
              inject a text file before the config file (advanced templating)

       --inject-after
              inject a text file after the config file (advanced templating)

       -d|--daemonize
              daemonize uWSGI

       --daemonize2
              daemonize uWSGI after app loading

       --stop stop an instance

       --reload
              reload an instance

       --pause
              pause an instance

       --suspend
              suspend an instance

       --resume
              resume an instance

       --connect-and-read
              connect to a socket and wait for data from it

       --extract
              fetch/dump any supported address to stdout

       -l|--listen
              set the socket listen queue size

       -v|--max-vars
              set the amount of internal iovec/vars structures

       --max-apps
              set the maximum number of per-worker applications

       -b|--buffer-size
              set internal buffer size

       -m|--memory-report
              enable memory report

       --profiler
              enable the specified profiler

       -c|--cgi-mode
              force CGI-mode for plugins supporting it

       -a|--abstract-socket
              force UNIX socket in abstract mode (Linux only)

       -C|--chmod-socket
              chmod-socket

       -C|--chmod
              chmod-socket

       --chown-socket
              chown unix sockets

       --umask
              set umask

       --freebind
              put socket in freebind mode

       --map-socket
              map sockets to specific workers

       -T|--enable-threads
              enable threads

       --no-threads-wait
              do not wait for threads cancellation on quit/reload

       --auto-procname
              automatically set processes name to something meaningful

       --procname-prefix
              add a prefix to the process names

       --procname-prefix-spaced
              add a spaced prefix to the process names

       --procname-append
              append a string to process names

       --procname
              set process names

       --procname-master
              set master process name

       -i|--single-interpreter
              do not use multiple interpreters (where available)

       --need-app
              exit if no app can be loaded

       -M|--master
              enable master process

       --honour-stdin
              do not remap stdin to /dev/null

       --emperor
              run the Emperor

       --emperor-proxy-socket
              force the vassal to became an Emperor proxy

       --emperor-wrapper
              set a binary wrapper for vassals

       --emperor-wrapper-override
              set a binary wrapper for vassals to try before the default one

       --emperor-wrapper-fallback
              set a binary wrapper for vassals to try as a last resort

       --emperor-nofollow
              do not follow symlinks when checking for mtime

       --emperor-procname
              set the Emperor process name

       --emperor-freq
              set the Emperor scan frequency (default 3 seconds)

       --emperor-required-heartbeat
              set the Emperor tolerance about heartbeats

       --emperor-curse-tolerance
              set the Emperor tolerance about cursed vassals

       --emperor-pidfile
              write the Emperor pid in the specified file

       --emperor-tyrant
              put the Emperor in Tyrant mode

       --emperor-tyrant-nofollow
              do not follow symlinks when checking for uid/gid in Tyrant mode

       --emperor-stats
              run the Emperor stats server

       --emperor-stats-server
              run the Emperor stats server

       --early-emperor
              spawn the emperor as soon as possibile

       --emperor-broodlord
              run the emperor in BroodLord mode

       --emperor-throttle
              set throttling level (in milliseconds) for bad behaving vassals (default 1000)

       --emperor-max-throttle
              set max throttling level (in milliseconds) for bad behaving vassals (default 3 minutes)

       --emperor-magic-exec
              prefix vassals config files with exec:// if they have the executable bit

       --emperor-on-demand-extension
              search for text file (vassal name + extension) containing the on demand socket name

       --emperor-on-demand-ext
              search for text file (vassal name + extension) containing the on demand socket name

       --emperor-on-demand-directory
              enable on demand mode binding to the unix socket in the specified  directory  named  like
              the vassal + .socket

       --emperor-on-demand-dir
              enable  on  demand  mode binding to the unix socket in the specified directory named like
              the vassal + .socket

       --emperor-on-demand-exec
              use the output of the specified command as on demand socket  name  (the  vassal  name  is
              passed as the only argument)

       --emperor-extra-extension
              allows the specified extension in the Emperor (vassal will be called with --config)

       --emperor-extra-ext
              allows the specified extension in the Emperor (vassal will be called with --config)

       --emperor-no-blacklist
              disable Emperor blacklisting subsystem

       --emperor-use-clone
              use clone() instead of fork() passing the specified unshare() flags

       --emperor-cap
              set vassals capability

       --vassals-cap
              set vassals capability

       --vassal-cap
              set vassals capability

       --imperial-monitor-list
              list enabled imperial monitors

       --imperial-monitors-list
              list enabled imperial monitors

       --vassals-inherit
              add config templates to vassals config (uses --inherit)

       --vassals-include
              include config templates to vassals config (uses --include instead of --inherit)

       --vassals-inherit-before
              add config templates to vassals config (uses --inherit, parses before the vassal file)

       --vassals-include-before
              include  config  templates to vassals config (uses --include instead of --inherit, parses
              before the vassal file)

       --vassals-start-hook
              run the specified command before each vassal starts

       --vassals-stop-hook
              run the specified command after vassal's death

       --vassal-sos
              ask emperor for reinforcement when overloaded

       --vassal-sos-backlog
              ask emperor for sos if backlog queue has more items than the value specified

       --vassals-set
              automatically set the specified option (via --set) for every vassal

       --vassal-set
              automatically set the specified option (via --set) for every vassal

       --heartbeat
              announce healthiness to the emperor

       --reload-mercy
              set the maximum time (in seconds) we wait for workers and other processes to  die  during
              reload/shutdown

       --worker-reload-mercy
              set the maximum time (in seconds) a worker can take to reload/shutdown (default is 60)

       --mule-reload-mercy
              set the maximum time (in seconds) a mule can take to reload/shutdown (default is 60)

       --exit-on-reload
              force exit even if a reload is requested

       --die-on-term
              exit instead of brutal reload on SIGTERM

       --force-gateway
              force the spawn of the first registered gateway without a master

       -h|--help
              show this help

       -h|--usage
              show this help

       --print-sym
              print content of the specified binary symbol

       --print-symbol
              print content of the specified binary symbol

       -r|--reaper
              call waitpid(-1,...) after each request to get rid of zombies

       -R|--max-requests
              reload workers after the specified amount of managed requests

       --min-worker-lifetime
              number of seconds worker must run before being reloaded (default is 60)

       --max-worker-lifetime
              reload workers after the specified amount of seconds (default is disabled)

       -z|--socket-timeout
              set internal sockets timeout

       --no-fd-passing
              disable file descriptor passing

       --locks
              create the specified number of shared locks

       --lock-engine
              set the lock engine

       --ftok set the ipcsem key via ftok() for avoiding duplicates

       --persistent-ipcsem
              do not remove ipcsem's on shutdown

       -A|--sharedarea
              create a raw shared memory area of specified pages (note: it supports keyval too)

       --safe-fd
              do not close the specified file descriptor

       --fd-safe
              do not close the specified file descriptor

       --cache
              create a shared cache containing given elements

       --cache-blocksize
              set cache blocksize

       --cache-store
              enable persistent cache to disk

       --cache-store-sync
              set frequency of sync for persistent cache

       --cache-no-expire
              disable auto sweep of expired items

       --cache-expire-freq
              set the frequency of cache sweeper scans (default 3 seconds)

       --cache-report-freed-items
              constantly report the cache item freed by the sweeper (use only for debug)

       --cache-udp-server
              bind the cache udp server (used only for set/update/delete) to the specified socket

       --cache-udp-node
              send cache update/deletion to the specified cache udp server

       --cache-sync
              copy the whole content of another uWSGI cache server on server startup

       --cache-use-last-modified
              update last_modified_at timestamp on every cache item modification (default is disabled)

       --add-cache-item
              add an item in the cache

       --load-file-in-cache
              load a static file in the cache

       --load-file-in-cache-gzip
              load a static file in the cache with gzip compression

       --cache2
              create a new generation shared cache (keyval syntax)

       --queue
              enable shared queue

       --queue-blocksize
              set queue blocksize

       --queue-store
              enable persistent queue to disk

       --queue-store-sync
              set frequency of sync for persistent queue

       -Q|--spooler
              run a spooler on the specified directory

       --spooler-external
              map spoolers requests to a spooler directory managed by an external instance

       --spooler-ordered
              try to order the execution of spooler tasks

       --spooler-chdir
              chdir() to specified directory before each spooler task

       --spooler-processes
              set the number of processes for spoolers

       --spooler-quiet
              do not be verbose with spooler tasks

       --spooler-max-tasks
              set the maximum number of tasks to run before recycling a spooler

       --spooler-harakiri
              set harakiri timeout for spooler tasks

       --spooler-frequency
              set spooler frequency

       --spooler-freq
              set spooler frequency

       --mule add a mule

       --mules
              add the specified number of mules

       --farm add a mule farm

       --mule-msg-size
              set mule message buffer size

       --signal
              send a uwsgi signal to a server

       --signal-bufsize
              set buffer size for signal queue

       --signals-bufsize
              set buffer size for signal queue

       --signal-timer
              add a timer (syntax: <signal> <seconds>)

       --timer
              add a timer (syntax: <signal> <seconds>)

       --signal-rbtimer
              add a redblack timer (syntax: <signal> <seconds>)

       --rbtimer
              add a redblack timer (syntax: <signal> <seconds>)

       --rpc-max
              maximum number of rpc slots (default: 64)

       -L|--disable-logging
              disable request logging

       --flock
              lock the specified file before starting, exit if locked

       --flock-wait
              lock the specified file before starting, wait if locked

       --flock2
              lock the specified file after logging/daemon setup, exit if locked

       --flock-wait2
              lock the specified file after logging/daemon setup, wait if locked

       --pidfile
              create pidfile (before privileges drop)

       --pidfile2
              create pidfile (after privileges drop)

       --chroot
              chroot() to the specified directory

       --pivot-root
              pivot_root()  to the specified directories (new_root and put_old must be separated with a
              space)

       --pivot_root
              pivot_root() to the specified directories (new_root and put_old must be separated with  a
              space)

       --uid  setuid to the specified user/uid

       --gid  setgid to the specified group/gid

       --add-gid
              add the specified group id to the process credentials

       --immediate-uid
              setuid to the specified user/uid IMMEDIATELY

       --immediate-gid
              setgid to the specified group/gid IMMEDIATELY

       --no-initgroups
              disable additional groups set via initgroups()

       --cap  set process capability

       --unshare
              unshare() part of the processes and put it in a new namespace

       --unshare2
              unshare() part of the processes and put it in a new namespace after rootfs change

       --setns-socket
              expose a unix socket returning namespace fds from /proc/self/ns

       --setns-socket-skip
              skip the specified entry when sending setns file descriptors

       --setns-skip
              skip the specified entry when sending setns file descriptors

       --setns
              join a namespace created by an external uWSGI instance

       --setns-preopen
              open /proc/self/ns as soon as possible and cache fds

       --jailed
              mark the instance as jailed (force the execution of post_jail hooks)

       --refork
              fork() again after privileges drop. Useful for jailing systems

       --re-fork
              fork() again after privileges drop. Useful for jailing systems

       --refork-as-root
              fork() again before privileges drop. Useful for jailing systems

       --re-fork-as-root
              fork() again before privileges drop. Useful for jailing systems

       --refork-post-jail
              fork() again after jailing. Useful for jailing systems

       --re-fork-post-jail
              fork() again after jailing. Useful for jailing systems

       --hook-asap
              run the specified hook as soon as possible

       --hook-pre-jail
              run the specified hook before jailing

       --hook-post-jail
              run the specified hook after jailing

       --hook-in-jail
              run the specified hook in jail after initialization

       --hook-as-root
              run the specified hook before privileges drop

       --hook-as-user
              run the specified hook after privileges drop

       --hook-as-user-atexit
              run the specified hook before app exit and reload

       --hook-pre-app
              run the specified hook before app loading

       --hook-post-app
              run the specified hook after app loading

       --hook-post-fork
              run the specified hook after each fork

       --hook-accepting
              run the specified hook after each worker enter the accepting phase

       --hook-accepting1
              run the specified hook after the first worker enters the accepting phase

       --hook-accepting-once
              run the specified hook after each worker enter the accepting phase (once per-instance)

       --hook-accepting1-once
              run  the  specified  hook  after  the  first  worker enters the accepting phase (once per
              instance)

       --hook-master-start
              run the specified hook when the Master starts

       --hook-touch
              run the specified hook when the specified file is touched (syntax: <file> <action>)

       --hook-emperor-start
              run the specified hook when the Emperor starts

       --hook-emperor-stop
              run the specified hook when the Emperor send a stop message

       --hook-emperor-reload
              run the specified hook when the Emperor send a reload message

       --hook-emperor-lost
              run the specified hook when the Emperor connection is lost

       --hook-as-vassal
              run the specified hook before exec()ing the vassal

       --hook-as-emperor
              run the specified hook in the emperor after the vassal has been started

       --hook-as-mule
              run the specified hook in each mule

       --hook-as-gateway
              run the specified hook in each gateway

       --after-request-hook
              run the specified function/symbol after each request

       --after-request-call
              run the specified function/symbol after each request

       --exec-asap
              run the specified command as soon as possible

       --exec-pre-jail
              run the specified command before jailing

       --exec-post-jail
              run the specified command after jailing

       --exec-in-jail
              run the specified command in jail after initialization

       --exec-as-root
              run the specified command before privileges drop

       --exec-as-user
              run the specified command after privileges drop

       --exec-as-user-atexit
              run the specified command before app exit and reload

       --exec-pre-app
              run the specified command before app loading

       --exec-post-app
              run the specified command after app loading

       --exec-as-vassal
              run the specified command before exec()ing the vassal

       --exec-as-emperor
              run the specified command in the emperor after the vassal has been started

       --mount-asap
              mount filesystem as soon as possible

       --mount-pre-jail
              mount filesystem before jailing

       --mount-post-jail
              mount filesystem after jailing

       --mount-in-jail
              mount filesystem in jail after initialization

       --mount-as-root
              mount filesystem before privileges drop

       --mount-as-vassal
              mount filesystem before exec()ing the vassal

       --mount-as-emperor
              mount filesystem in the emperor after the vassal has been started

       --umount-asap
              unmount filesystem as soon as possible

       --umount-pre-jail
              unmount filesystem before jailing

       --umount-post-jail
              unmount filesystem after jailing

       --umount-in-jail
              unmount filesystem in jail after initialization

       --umount-as-root
              unmount filesystem before privileges drop

       --umount-as-vassal
              unmount filesystem before exec()ing the vassal

       --umount-as-emperor
              unmount filesystem in the emperor after the vassal has been started

       --wait-for-interface
              wait for the specified network interface to come up before running root hooks

       --wait-for-interface-timeout
              set the timeout for wait-for-interface

       --wait-interface
              wait for the specified network interface to come up before running root hooks

       --wait-interface-timeout
              set the timeout for wait-for-interface

       --wait-for-iface
              wait for the specified network interface to come up before running root hooks

       --wait-for-iface-timeout
              set the timeout for wait-for-interface

       --wait-iface
              wait for the specified network interface to come up before running root hooks

       --wait-iface-timeout
              set the timeout for wait-for-interface

       --wait-for-fs
              wait for the specified filesystem item to appear before running root hooks

       --wait-for-file
              wait for the specified file to appear before running root hooks

       --wait-for-dir
              wait for the specified directory to appear before running root hooks

       --wait-for-mountpoint
              wait for the specified mountpoint to appear before running root hooks

       --wait-for-fs-timeout
              set the timeout for wait-for-fs/file/dir

       --wait-for-socket
              wait for the specified socket to be ready before loading apps

       --wait-for-socket-timeout
              set the timeout for wait-for-socket

       --call-asap
              call the specified function as soon as possible

       --call-pre-jail
              call the specified function before jailing

       --call-post-jail
              call the specified function after jailing

       --call-in-jail
              call the specified function in jail after initialization

       --call-as-root
              call the specified function before privileges drop

       --call-as-user
              call the specified function after privileges drop

       --call-as-user-atexit
              call the specified function before app exit and reload

       --call-pre-app
              call the specified function before app loading

       --call-post-app
              call the specified function after app loading

       --call-as-vassal
              call the specified function() before exec()ing the vassal

       --call-as-vassal1
              call the specified function(char *) before exec()ing the vassal

       --call-as-vassal3
              call the specified function(char *, uid_t, gid_t) before exec()ing the vassal

       --call-as-emperor
              call the specified function() in the emperor after the vassal has been started

       --call-as-emperor1
              call the specified function(char *) in the emperor after the vassal has been started

       --call-as-emperor2
              call the specified function(char *, pid_t) in the  emperor  after  the  vassal  has  been
              started

       --call-as-emperor4
              call  the specified function(char *, pid_t, uid_t, gid_t) in the emperor after the vassal
              has been started

       --ini  load config from ini file

       -y|--yaml
              load config from yaml file

       -y|--yml
              load config from yaml file

       -j|--json
              load config from json file

       -j|--js
              load config from json file

       --weight
              weight of the instance (used by clustering/lb/subscriptions)

       --auto-weight
              set weight of the instance (used by clustering/lb/subscriptions) automatically

       --no-server
              force no-server mode

       --command-mode
              force command mode

       --no-defer-accept
              disable deferred-accept on sockets

       --tcp-nodelay
              enable TCP NODELAY on each request

       --so-keepalive
              enable TCP KEEPALIVEs

       --so-send-timeout
              set SO_SNDTIMEO

       --socket-send-timeout
              set SO_SNDTIMEO

       --so-write-timeout
              set SO_SNDTIMEO

       --socket-write-timeout
              set SO_SNDTIMEO

       --socket-sndbuf
              set SO_SNDBUF

       --socket-rcvbuf
              set SO_RCVBUF

       --limit-as
              limit processes address space/vsz

       --limit-nproc
              limit the number of spawnable processes

       --reload-on-as
              reload if address space is higher than specified megabytes

       --reload-on-rss
              reload if rss memory is higher than specified megabytes

       --evil-reload-on-as
              force the master to reload a worker  if  its  address  space  is  higher  than  specified
              megabytes

       --evil-reload-on-rss
              force the master to reload a worker if its rss memory is higher than specified megabytes

       --mem-collector-freq
              set the memory collector frequency when evil reloads are in place

       --reload-on-fd
              reload if the specified file descriptor is ready

       --brutal-reload-on-fd
              brutal reload if the specified file descriptor is ready

       --ksm  enable Linux KSM

       --pcre-jit
              enable pcre jit (if available)

       --never-swap
              lock all memory pages avoiding swapping

       --touch-reload
              reload uWSGI if the specified file is modified/touched

       --touch-workers-reload
              trigger reload of (only) workers if the specified file is modified/touched

       --touch-mules-reload
              reload mules if the specified file is modified/touched

       --touch-spoolers-reload
              reload spoolers if the specified file is modified/touched

       --touch-chain-reload
              trigger chain reload if the specified file is modified/touched

       --touch-logrotate
              trigger logrotation if the specified file is modified/touched

       --touch-logreopen
              trigger log reopen if the specified file is modified/touched

       --touch-exec
              run command when the specified file is modified/touched (syntax: file command)

       --touch-signal
              signal when the specified file is modified/touched (syntax: file signal)

       --fs-reload
              graceful reload when the specified filesystem object is modified

       --fs-brutal-reload
              brutal reload when the specified filesystem object is modified

       --fs-signal
              raise  a uwsgi signal when the specified filesystem object is modified (syntax: file sig‐
              nal)

       --check-mountpoint
              destroy the instance if a filesystem is no more reachable (useful for reliable Fuse  man‐
              agement)

       --mountpoint-check
              destroy  the instance if a filesystem is no more reachable (useful for reliable Fuse man‐
              agement)

       --check-mount
              destroy the instance if a filesystem is no more reachable (useful for reliable Fuse  man‐
              agement)

       --mount-check
              destroy  the instance if a filesystem is no more reachable (useful for reliable Fuse man‐
              agement)

       --propagate-touch
              over-engineering option for system with flaky signal management

       --limit-post
              limit request body

       --no-orphans
              automatically kill workers if master dies (can be dangerous for availability)

       --prio set processes/threads priority

       --cpu-affinity
              set cpu affinity

       --post-buffering
              set size in bytes after which will buffer to disk instead of memory

       --post-buffering-bufsize
              set buffer size for read() in post buffering mode

       --body-read-warning
              set the amount of allowed memory allocation (in megabytes) for request body before start‐
              ing printing a warning

       --upload-progress
              enable creation of .json files in the specified directory during a file upload

       --no-default-app
              do not fallback to default app

       --manage-script-name
              automatically rewrite SCRIPT_NAME and PATH_INFO

       --ignore-script-name
              ignore SCRIPT_NAME

       --catch-exceptions
              report exception as http output (discouraged, use only for testing)

       --reload-on-exception
              reload a worker when an exception is raised

       --reload-on-exception-type
              reload a worker when a specific exception type is raised

       --reload-on-exception-value
              reload a worker when a specific exception value is raised

       --reload-on-exception-repr
              reload a worker when a specific exception type+value (language-specific) is raised

       --exception-handler
              add an exception handler

       --enable-metrics
              enable metrics subsystem

       --metric
              add a custom metric

       --metric-threshold
              add a metric threshold/alarm

       --metric-alarm
              add a metric threshold/alarm

       --alarm-metric
              add a metric threshold/alarm

       --metrics-dir
              export metrics as text files to the specified directory

       --metrics-dir-restore
              restore last value taken from the metrics dir

       --metric-dir
              export metrics as text files to the specified directory

       --metric-dir-restore
              restore last value taken from the metrics dir

       --metrics-no-cores
              disable generation of cores-related metrics

       --udp  run the udp server on the specified address

       --stats
              enable the stats server on the specified address

       --stats-server
              enable the stats server on the specified address

       --stats-http
              prefix stats server json output with http headers

       --stats-minified
              minify statistics json output

       --stats-min
              minify statistics json output

       --stats-push
              push the stats json to the specified destination

       --stats-pusher-default-freq
              set the default frequency of stats pushers

       --stats-pushers-default-freq
              set the default frequency of stats pushers

       --stats-no-cores
              disable generation of cores-related stats

       --stats-no-metrics
              do not include metrics in stats output

       --multicast
              subscribe to specified multicast group

       --multicast-ttl
              set multicast ttl

       --multicast-loop
              set multicast loop (default 1)

       --master-fifo
              enable the master fifo

       --notify-socket
              enable the notification socket

       --subscription-notify-socket
              set the notification socket for subscriptions

       --legion
              became a member of a legion

       --legion-mcast
              became a member of a legion (shortcut for multicast)

       --legion-node
              add a node to a legion

       --legion-freq
              set the frequency of legion packets

       --legion-tolerance
              set the tolerance of legion subsystem

       --legion-death-on-lord-error
              declare  itself  as  a  dead  node for the specified amount of seconds if one of the lord
              hooks fails

       --legion-skew-tolerance
              set the clock skew tolerance of legion subsystem (default 30 seconds)

       --legion-lord
              action to call on Lord election

       --legion-unlord
              action to call on Lord dismiss

       --legion-setup
              action to call on legion setup

       --legion-death
              action to call on legion death (shutdown of the instance)

       --legion-join
              action to call on legion join (first time quorum is reached)

       --legion-node-joined
              action to call on new node joining legion

       --legion-node-left
              action to call node leaving legion

       --legion-quorum
              set the quorum of a legion

       --legion-scroll
              set the scroll of a legion

       --legion-scroll-max-size
              set max size of legion scroll buffer

       --legion-scroll-list-max-size
              set max size of legion scroll list buffer

       --subscriptions-sign-check
              set digest algorithm and certificate directory for secured subscription system

       --subscriptions-sign-check-tolerance
              set the maximum tolerance (in seconds) of clock skew for secured subscription system

       --subscriptions-sign-skip-uid
              skip signature check for the specified uid when using unix sockets credentials

       --subscriptions-credentials-check
              add a directory to search for subscriptions key credentials

       --subscriptions-use-credentials
              enable management of SCM_CREDENTIALS in subscriptions UNIX sockets

       --subscription-algo
              set load balancing algorithm for the subscription system

       --subscription-dotsplit
              try to fallback to the next part (dot based) in subscription key

       --subscribe-to
              subscribe to the specified subscription server

       --st   subscribe to the specified subscription server

       --subscribe
              subscribe to the specified subscription server

       --subscribe2
              subscribe to the specified subscription server using advanced keyval syntax

       --subscribe-freq
              send subscription announce at the specified interval

       --subscription-tolerance
              set tolerance for subscription servers

       --unsubscribe-on-graceful-reload
              force unsubscribe request even during graceful reload

       --start-unsubscribed
              configure subscriptions but do not send them (useful with master fifo)

       --subscribe-with-modifier1
              force the specififed modifier1 when subscribing

       --snmp enable the embedded snmp server

       --snmp-community
              set the snmp community string

       --ssl-verbose
              be verbose about SSL errors

       --sni  add an SNI-governed SSL context

       --sni-dir
              check for cert/key/client_ca file in the specified directory and create a sni/ssl context
              on demand

       --sni-dir-ciphers
              set ssl ciphers for sni-dir option

       --ssl-enable3
              enable SSLv3 (insecure)

       --ssl-option
              set a raw ssl option (numeric value)

       --sni-regexp
              add an SNI-governed SSL context (the key is a regexp)

       --ssl-tmp-dir
              store ssl-related temp files in the specified directory

       --check-interval
              set the interval (in seconds) of master checks

       --forkbomb-delay
              sleep for the specified number of seconds when a forkbomb is detected

       --binary-path
              force binary path

       --privileged-binary-patch
              patch the uwsgi binary with a new command (before privileges drop)

       --unprivileged-binary-patch
              patch the uwsgi binary with a new command (after privileges drop)

       --privileged-binary-patch-arg
              patch the uwsgi binary with a new command and arguments (before privileges drop)

       --unprivileged-binary-patch-arg
              patch the uwsgi binary with a new command and arguments (after privileges drop)

       --async
              enable async mode with specified cores

       --max-fd
              set maximum number of file descriptors (requires root privileges)

       --logto
              set logfile/udp address

       --logto2
              log to specified file or udp address after privileges drop

       --log-format
              set advanced format for request logging

       --logformat
              set advanced format for request logging

       --logformat-strftime
              apply strftime to logformat output

       --log-format-strftime
              apply strftime to logformat output

       --logfile-chown
              chown logfiles

       --logfile-chmod
              chmod logfiles

       --log-syslog
              log to syslog

       --log-socket
              send logs to the specified socket

       --req-logger
              set/append a request logger

       --logger-req
              set/append a request logger

       --logger
              set/append a logger

       --logger-list
              list enabled loggers

       --loggers-list
              list enabled loggers

       --threaded-logger
              offload log writing to a thread

       --log-encoder
              add an item in the log encoder chain

       --log-req-encoder
              add an item in the log req encoder chain

       --log-drain
              drain (do not show) log lines matching the specified regexp

       --log-filter
              show only log lines matching the specified regexp

       --log-route
              log to the specified named logger if regexp applied on logline matches

       --log-req-route
              log requests to the specified named logger if regexp applied on logline matches

       --use-abort
              call abort() on segfault/fpe, could be useful for generating a core dump

       --alarm
              create a new alarm, syntax: <alarm> <plugin:args>

       --alarm-cheap
              use main alarm thread rather than create dedicated threads for curl-based alarms

       --alarm-freq
              tune the anti-loop alarm system (default 3 seconds)

       --alarm-fd
              raise  the specified alarm when an fd is read for read (by default it reads 1 byte, set 8
              for eventfd)

       --alarm-segfault
              raise the specified alarm when the segmentation fault handler is executed

       --segfault-alarm
              raise the specified alarm when the segmentation fault handler is executed

       --alarm-backlog
              raise the specified alarm when the socket backlog queue is full

       --backlog-alarm
              raise the specified alarm when the socket backlog queue is full

       --lq-alarm
              raise the specified alarm when the socket backlog queue is full

       --alarm-lq
              raise the specified alarm when the socket backlog queue is full

       --alarm-listen-queue
              raise the specified alarm when the socket backlog queue is full

       --listen-queue-alarm
              raise the specified alarm when the socket backlog queue is full

       --log-alarm
              raise the specified  alarm  when  a  log  line  matches  the  specified  regexp,  syntax:
              <alarm>[,alarm...] <regexp>

       --alarm-log
              raise  the  specified  alarm  when  a  log  line  matches  the  specified regexp, syntax:
              <alarm>[,alarm...] <regexp>

       --not-log-alarm
              skip the  specified  alarm  when  a  log  line  matches  the  specified  regexp,  syntax:
              <alarm>[,alarm...] <regexp>

       --not-alarm-log
              skip  the  specified  alarm  when  a  log  line  matches  the  specified  regexp, syntax:
              <alarm>[,alarm...] <regexp>

       --alarm-list
              list enabled alarms

       --alarms-list
              list enabled alarms

       --alarm-msg-size
              set the max size of an alarm message (default 8192)

       --log-master
              delegate logging to master process

       --log-master-bufsize
              set the buffer size for the master logger. bigger log messages will be truncated

       --log-master-stream
              create the master logpipe as SOCK_STREAM

       --log-master-req-stream
              create the master requests logpipe as SOCK_STREAM

       --log-reopen
              reopen log after reload

       --log-truncate
              truncate log on startup

       --log-maxsize
              set maximum logfile size

       --log-backupname
              set logfile name after rotation

       --logdate
              prefix logs with date or a strftime string

       --log-date
              prefix logs with date or a strftime string

       --log-prefix
              prefix logs with a string

       --log-zero
              log responses without body

       --log-slow
              log requests slower than the specified number of milliseconds

       --log-4xx
              log requests with a 4xx response

       --log-5xx
              log requests with a 5xx response

       --log-big
              log requestes bigger than the specified size

       --log-sendfile
              log sendfile requests

       --log-ioerror
              log requests with io errors

       --log-micros
              report response time in microseconds instead of milliseconds

       --log-x-forwarded-for
              use the ip from X-Forwarded-For header instead of REMOTE_ADDR

       --master-as-root
              leave master process running as root

       --drop-after-init
              run privileges drop after plugin initialization, superseded by drop-after-apps

       --drop-after-apps
              run privileges drop after apps loading, superseded by master-as-root

       --force-cwd
              force the initial working directory to the specified value

       --binsh
              override /bin/sh (used by exec hooks, it always fallback to /bin/sh)

       --chdir
              chdir to specified directory before apps loading

       --chdir2
              chdir to specified directory after apps loading

       --lazy set lazy mode (load apps in workers instead of master)

       --lazy-apps
              load apps in each worker instead of the master

       --cheap
              set cheap mode (spawn workers only after the first request)

       --cheaper
              set cheaper mode (adaptive process spawning)

       --cheaper-initial
              set the initial number of processes to spawn in cheaper mode

       --cheaper-algo
              choose to algorithm used for adaptive process spawning

       --cheaper-step
              number of additional processes to spawn at each overload

       --cheaper-overload
              increase workers after specified overload

       --cheaper-algo-list
              list enabled cheapers algorithms

       --cheaper-algos-list
              list enabled cheapers algorithms

       --cheaper-list
              list enabled cheapers algorithms

       --cheaper-rss-limit-soft
              don't spawn new workers if total resident memory usage of all workers is higher than this
              limit

       --cheaper-rss-limit-hard
              if total workers resident memory usage is higher try to stop workers

       --idle set idle mode (put uWSGI in cheap mode after inactivity)

       --die-on-idle
              shutdown uWSGI when idle

       --mount
              load application under mountpoint

       --worker-mount
              load application under mountpoint in the specified worker or after workers spawn

       --threads
              run each worker in prethreaded mode with the specified number of threads

       --thread-stacksize
              set threads stacksize

       --threads-stacksize
              set threads stacksize

       --thread-stack-size
              set threads stacksize

       --threads-stack-size
              set threads stacksize

       --vhost
              enable virtualhosting mode (based on SERVER_NAME variable)

       --vhost-host
              enable virtualhosting mode (based on HTTP_HOST variable)

       --route
              add a route

       --route-host
              add a route based on Host header

       --route-uri
              add a route based on REQUEST_URI

       --route-qs
              add a route based on QUERY_STRING

       --route-remote-addr
              add a route based on REMOTE_ADDR

       --route-user-agent
              add a route based on HTTP_USER_AGENT

       --route-remote-user
              add a route based on REMOTE_USER

       --route-referer
              add a route based on HTTP_REFERER

       --route-label
              add a routing label (for use with goto)

       --route-if
              add a route based on condition

       --route-if-not
              add a route based on condition (negate version)

       --route-run
              always run the specified route action

       --final-route
              add a final route

       --final-route-status
              add a final route for the specified status

       --final-route-host
              add a final route based on Host header

       --final-route-uri
              add a final route based on REQUEST_URI

       --final-route-qs
              add a final route based on QUERY_STRING

       --final-route-remote-addr
              add a final route based on REMOTE_ADDR

       --final-route-user-agent
              add a final route based on HTTP_USER_AGENT

       --final-route-remote-user
              add a final route based on REMOTE_USER

       --final-route-referer
              add a final route based on HTTP_REFERER

       --final-route-label
              add a final routing label (for use with goto)

       --final-route-if
              add a final route based on condition

       --final-route-if-not
              add a final route based on condition (negate version)

       --final-route-run
              always run the specified final route action

       --error-route
              add an error route

       --error-route-status
              add an error route for the specified status

       --error-route-host
              add an error route based on Host header

       --error-route-uri
              add an error route based on REQUEST_URI

       --error-route-qs
              add an error route based on QUERY_STRING

       --error-route-remote-addr
              add an error route based on REMOTE_ADDR

       --error-route-user-agent
              add an error route based on HTTP_USER_AGENT

       --error-route-remote-user
              add an error route based on REMOTE_USER

       --error-route-referer
              add an error route based on HTTP_REFERER

       --error-route-label
              add an error routing label (for use with goto)

       --error-route-if
              add an error route based on condition

       --error-route-if-not
              add an error route based on condition (negate version)

       --error-route-run
              always run the specified error route action

       --response-route
              add a response route

       --response-route-status
              add a response route for the specified status

       --response-route-host
              add a response route based on Host header

       --response-route-uri
              add a response route based on REQUEST_URI

       --response-route-qs
              add a response route based on QUERY_STRING

       --response-route-remote-addr
              add a response route based on REMOTE_ADDR

       --response-route-user-agent
              add a response route based on HTTP_USER_AGENT

       --response-route-remote-user
              add a response route based on REMOTE_USER

       --response-route-referer
              add a response route based on HTTP_REFERER

       --response-route-label
              add a response routing label (for use with goto)

       --response-route-if
              add a response route based on condition

       --response-route-if-not
              add a response route based on condition (negate version)

       --response-route-run
              always run the specified response route action

       --router-list
              list enabled routers

       --routers-list
              list enabled routers

       --error-page-403
              add an error page (html) for managed 403 response

       --error-page-404
              add an error page (html) for managed 404 response

       --error-page-500
              add an error page (html) for managed 500 response

       --websockets-ping-freq
              set the frequency (in seconds) of websockets automatic ping packets

       --websocket-ping-freq
              set the frequency (in seconds) of websockets automatic ping packets

       --websockets-pong-tolerance
              set the tolerance (in seconds) of websockets ping/pong subsystem

       --websocket-pong-tolerance
              set the tolerance (in seconds) of websockets ping/pong subsystem

       --websockets-max-size
              set the max allowed size of websocket messages (in Kbytes, default 1024)

       --websocket-max-size
              set the max allowed size of websocket messages (in Kbytes, default 1024)

       --chunked-input-limit
              set the max size of a chunked input part (default 1MB, in bytes)

       --chunked-input-timeout
              set default timeout for chunked input

       --clock
              set a clock source

       --clock-list
              list enabled clocks

       --clocks-list
              list enabled clocks

       --add-header
              automatically add HTTP headers to response

       --rem-header
              automatically remove specified HTTP header from the response

       --del-header
              automatically remove specified HTTP header from the response

       --collect-header
              store the specified response header in a request var (syntax: header var)

       --response-header-collect
              store the specified response header in a request var (syntax: header var)

       --pull-header
              store  the  specified  response  header  in a request var and remove it from the response
              (syntax: header var)

       --check-static
              check for static files in the specified directory

       --check-static-docroot
              check for static files in the requested DOCUMENT_ROOT

       --static-check
              check for static files in the specified directory

       --static-map
              map mountpoint to static directory (or file)

       --static-map2
              like static-map but completely appending the requested resource to the docroot

       --static-skip-ext
              skip specified extension from staticfile checks

       --static-index
              search for specified file if a directory is requested

       --static-safe
              skip security checks if the file is under the specified path

       --static-cache-paths
              put resolved paths in the uWSGI cache for the specified amount of seconds

       --static-cache-paths-name
              use the specified cache for static paths

       --mimefile
              set mime types file path (default /etc/mime.types)

       --mime-file
              set mime types file path (default /etc/mime.types)

       --static-expires-type
              set the Expires header based on content type

       --static-expires-type-mtime
              set the Expires header based on content type and file mtime

       --static-expires
              set the Expires header based on filename regexp

       --static-expires-mtime
              set the Expires header based on filename regexp and file mtime

       --static-expires-uri
              set the Expires header based on REQUEST_URI regexp

       --static-expires-uri-mtime
              set the Expires header based on REQUEST_URI regexp and file mtime

       --static-expires-path-info
              set the Expires header based on PATH_INFO regexp

       --static-expires-path-info-mtime
              set the Expires header based on PATH_INFO regexp and file mtime

       --static-gzip
              if the supplied regexp matches the static file translation it will search for a gzip ver‐
              sion

       --static-gzip-all
              check for a gzip version of all requested static files

       --static-gzip-dir
              check for a gzip version of all requested static files in the specified dir/prefix

       --static-gzip-prefix
              check for a gzip version of all requested static files in the specified dir/prefix

       --static-gzip-ext
              check for a gzip version of all requested static files with the specified ext/suffix

       --static-gzip-suffix
              check for a gzip version of all requested static files with the specified ext/suffix

       --honour-range
              enable support for the HTTP Range header

       --offload-threads
              set the number of offload threads to spawn (per-worker, default 0)

       --offload-thread
              set the number of offload threads to spawn (per-worker, default 0)

       --file-serve-mode
              set static file serving mode

       --fileserve-mode
              set static file serving mode

       --disable-sendfile
              disable sendfile() and rely on boring read()/write()

       --check-cache
              check for response data in the specified cache (empty for default cache)

       --close-on-exec
              set  close-on-exec  on  connection  sockets  (could be required for spawning processes in
              requests)

       --close-on-exec2
              set close-on-exec on  server  sockets  (could  be  required  for  spawning  processes  in
              requests)

       --mode set uWSGI custom mode

       --env  set environment variable

       --envdir
              load a daemontools compatible envdir

       --early-envdir
              load a daemontools compatible envdir ASAP

       --unenv
              unset environment variable

       --vacuum
              try to remove all of the generated file/sockets

       --file-write
              write  the specified content to the specified file (syntax: file=value) before privileges
              drop

       --cgroup
              put the processes in the specified cgroup

       --cgroup-opt
              set value in specified cgroup option

       --cgroup-dir-mode
              set permission for cgroup directory (default is 700)

       --namespace
              run in a new namespace under the specified rootfs

       --namespace-keep-mount
              keep the specified mountpoint in your namespace

       --ns   run in a new namespace under the specified rootfs

       --namespace-net
              add network namespace

       --ns-net
              add network namespace

       --enable-proxy-protocol
              enable PROXY1 protocol support (only for http parsers)

       --reuse-port
              enable REUSE_PORT flag on socket (BSD only)

       --tcp-fast-open
              enable TCP_FASTOPEN flag on TCP sockets with the specified qlen value

       --tcp-fastopen
              enable TCP_FASTOPEN flag on TCP sockets with the specified qlen value

       --tcp-fast-open-client
              use sendto(..., MSG_FASTOPEN, ...) instead of connect() if supported

       --tcp-fastopen-client
              use sendto(..., MSG_FASTOPEN, ...) instead of connect() if supported

       --zerg attach to a zerg server

       --zerg-fallback
              fallback to normal sockets if the zerg server is not available

       --zerg-server
              enable the zerg server on the specified UNIX socket

       --cron add a cron task

       --cron2
              add a cron task (key=val syntax)

       --unique-cron
              add a unique cron task

       --cron-harakiri
              set the maximum time (in seconds) we wait for cron command to complete

       --legion-cron
              add a cron task runnable only when the instance is a lord of the specified legion

       --cron-legion
              add a cron task runnable only when the instance is a lord of the specified legion

       --unique-legion-cron
              add a unique cron task runnable only when the instance is a lord of the specified legion

       --unique-cron-legion
              add a unique cron task runnable only when the instance is a lord of the specified legion

       --loop select the uWSGI loop engine

       --loop-list
              list enabled loop engines

       --loops-list
              list enabled loop engines

       --worker-exec
              run the specified command as worker

       --worker-exec2
              run the specified command as worker (after post_fork hook)

       --attach-daemon
              attach a command/daemon to the master process (the command has to not go in background)

       --attach-control-daemon
              attach a command/daemon to the master process (the command has to not go in  background),
              when the daemon dies, the master dies too

       --smart-attach-daemon
              attach  a  command/daemon  to the master process managed by a pidfile (the command has to
              daemonize)

       --smart-attach-daemon2
              attach a command/daemon to the master process managed by a pidfile (the  command  has  to
              NOT daemonize)

       --legion-attach-daemon
              same as --attach-daemon but daemon runs only on legion lord node

       --legion-smart-attach-daemon
              same as --smart-attach-daemon but daemon runs only on legion lord node

       --legion-smart-attach-daemon2
              same as --smart-attach-daemon2 but daemon runs only on legion lord node

       --daemons-honour-stdin
              do not change the stdin of external daemons to /dev/null

       --attach-daemon2
              attach-daemon keyval variant (supports smart modes too)

       --plugins
              load uWSGI plugins

       --plugin
              load uWSGI plugins

       --need-plugins
              load uWSGI plugins (exit on error)

       --need-plugin
              load uWSGI plugins (exit on error)

       --plugins-dir
              add a directory to uWSGI plugin search path

       --plugin-dir
              add a directory to uWSGI plugin search path

       --plugins-list
              list enabled plugins

       --plugin-list
              list enabled plugins

       --autoload
              try to automatically load plugins when unknown options are found

       --dlopen
              blindly load a shared library

       --allowed-modifiers
              comma separated list of allowed modifiers

       --remap-modifier
              remap request modifier from one id to another

       --dump-options
              dump the full list of available options
              装在所有可用的选项

       --show-config
              show the current config reformatted as ini
              显示当前重新初始化时的设置

       --binary-append-data
              return  the  content of a resource to stdout for appending to a uwsgi binary (for data://usage)

       --print
              simple print
              简易输出

       --iprint
              simple print (immediate version)
              建议输出（当前生效）

       --exit force exit() of the instance
              强制退出当前运行实例

       --cflags
              report uWSGI CFLAGS (useful for building external plugins)
              创建拓展插件是报告uwsgi编译器选项

       --dot-h
              dump the uwsgi.h used for building the core  (useful for building external plugins)
              创建时使用uwsgi.h

       --config-py
              dump the uwsgiconfig.py used for building the core  (useful for building  external  plugins)
              创建时使用uwsgiconfig.py

       --build-plugin
              build a uWSGI plugin for the current binary
              为当前的执行文件中创建一个uwsgi的插件，即加载插件到uwsgi服务器上

       --version
              print uWSGI version
              查看当前uwsgi版本

```