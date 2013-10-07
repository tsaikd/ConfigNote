Tomcat 7
========

[提升tomcat服务器性能的七条经验]: http://passover.blog.51cto.com/2431658/732629

* /etc/tomcat7/conf/server.xml
```
	<Connector port="8080" protocol="HTTP/1.1"
		connectionTimeout="20000"
		URIEncoding="UTF-8"
		compression="on"
		compressableMimeType="text/html,text/css,text/plain,text/xml,text/javascript,application/javascript,application/json"
		redirectPort="8443"
		maxThreads="10000"
		minSpareThreads="20"
		acceptCount="100"
		disableUploadTimeout="true"
		enableLookups="false"
		/>
```

* /etc/sysctl.cnf
```
net.core.netdev_max_backlog = 32768
net.core.somaxconn = 32768
net.core.wmem_default = 8388608
net.core.rmem_default = 8388608
net.core.rmem_max = 16777216
net.core.wmem_max = 16777216
net.ipv4.ip_local_port_range = 1024 65000
net.ipv4.route.gc_timeout = 100
net.ipv4.tcp_fin_timeout = 30
net.ipv4.tcp_keepalive_time = 1200
net.ipv4.tcp_timestamps = 0
net.ipv4.tcp_synack_retries = 2
net.ipv4.tcp_syn_retries = 2
net.ipv4.tcp_tw_recycle = 1
net.ipv4.tcp_tw_reuse = 1
net.ipv4.tcp_mem = 94500000 915000000 927000000
net.ipv4.tcp_max_orphans = 3276800
net.ipv4.tcp_max_syn_backlog = 65536
```

* 參考:
  * [提升tomcat服务器性能的七条经验][]

