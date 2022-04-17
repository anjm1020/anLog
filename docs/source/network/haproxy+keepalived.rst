========================================
Haproxy,Keepalived를 이용한 VRRP 구현
========================================

**1. 개발 환경**

.. code-block ::
 
 VM : UTM
 OS : Ubuntu 20.04 server(amd)
 apt : 2.0.6
 nginx : 1.18.0
 haproxy : 2.0.13
 keepalived : 2.0.19

**2. nginx 설치**

.. code-block :: bash

  $ apt-get install nginx
  
**3. nginx 테스트**

.. code-block :: bash
  
  $ service nginx start
  $ service nginx status
  
  ● nginx.service - A high performance web server and a reverse proxy server
    Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
    Active: active (running) since Fri 2022-04-15 22:05:02 UTC; 8h left
      Docs: man:nginx(8)
   Process: 720 ExecStartPre=/usr/sbin/nginx -t -q -g daemon on; master_process on; (c>
   Process: 748 ExecStart=/usr/sbin/nginx -g daemon on; master_process on; (code=exite>
  Main PID: 766 (nginx)
     Tasks: 2 (limit: 1062)
    Memory: 3.0M
    CGroup: /system.slice/nginx.service
             ├─766 nginx: master process /usr/sbin/nginx -g daemon on; master_process o>
             └─776 nginx: worker process

  
**4. nginx 테스트 및 루트폴더 확인**
  
.. code-block :: bash

  $ nginx -V
  > nginx version: nginx/1.18.0 (Ubuntu)
  > built with OpenSSL 1.1.1f  31 Mar 2020
  > TLS SNI support enabled
  > configure arguments : ...... --prefix=<root file>
  
