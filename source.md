name: inverse
class: center, middle, inverse
layout: true

---

name:  normal
class:
layout: true

---

class: center, middle

centralized application logging
<img src='images/graylog.png'>

![WDCM](images/wdcm.png)

13.01.2014


---
template: inverse

# Zentralisiert loggen

<img src='http://www.stefanwienert.de/images/headers/captainslog.jpg'/>

---

# Warum will man das?

.left-column[
Zentralisiert loggen
]

.right-column[

* Festplattenaktivität reduzieren / Cloud-Server

* Einheitliches Interface

* Filter + Aggregation + Visualisierung + Alerts

* <abbr title='Service oriented architecture'>SOA</abbr>: Nutzeraktivitäten über eine Vielzahl von Services hinweg nachverfolgen

]

---

template: inverse

# Graylog
---

template: normal

# Was ist Graylog2

.left-column[
  O-Ton
]
.right-column[

Centralize all your log messages

*    Collect terabytes of log messages

*    Process in real-time

*    Search and analyze in seconds
]

---

# Wer ist Graylog2

* Deutsches Startup (Hamburg)
<br>
<small>
2013 - Seed finanziert <small> e.ventures, HTGF, Hasso Plattner und Atlantic Capital</small></small>

* OpenSource (GPL) + Kommerzieller Support

* Java

* Aktuell: Version 0.92 (1.0.0 beta)
  <br> 3200 Commits
  <br> 1100 Stars auf Github
  <br> seit ca. 2010

---

.left-column[ Komponenten ]
.right-column[
* Graylog2-Server
* Graylog2-Web
* Inputs
* ElasticSearch + MongoDB

]
<div class='clear'></div>

<img class='img-responsive' src='https://www.graylog2.org/assets/images/how_it_works.png'/>


---

# Integrationen

https://www.graylog2.org/supported-sources

.column-list[
*    .NET/log4net (gelf4net)
*    .NET/NLog (Gelf4NLog)
*    .NET/NLog (NLog.GelfLayout)
*    Apache AccessLog
*    APC MGE
*    Audit Daemon
*    AWS CloudTrail   beta
*    Bind9 Query Log
*    C++ (gelf4cplus)
*    Cisco Catalyst
*    Clavister Firewalls
*    Cocoa/mObjective-C (MCGraylog)
*    Dropwizard (dropwizard-gelf)
*    Erlang/lager (erl_graylog_sender)
*    Erlang/lager (lager_graylog_backend)
*    Go (go-gelf)
*    Go (gomaplog)
*    Go (graylog-golang)
*    HAProxy
*    HAProxy HTTP Logs
*    HAProxy HTTP logs
*    Heroku
*    hubot (hubot-graylog-transcript)
*    Java (gelfclient)
*    Java/Log4j (gelf4j)
*    Java/Log4j (gelfj)
*    Java/Log4j 2 (log4j2-gelf)
*    Java/Logback (logback-gelf)
*    Java/tinylog (tinylog-gelf)
*    Juniper ScreenOS
*    MAC Address
*    MongoDB
*    NetApp
*    nginx
*    node.js (gelf-node)
*    node.js (graygelf)
*    node.js (log4js-node)
*    node.js (node-gelf-pro)
*    node.js (node-graylog)
*    node.js/Bunyan (gelf-stream)
*    node.js/Bunyan (messina)
*    Oracle Database 11.2g
*    Palo Alto Firewalls
*    Pam and Crond
*    Perl/Log4perl (log4perl_gelf)
*    Perl/Log4perl (Net-Graylog-Client)
*    pfSense
*    PHP (gelf-php)
*    PHP/log4php (log4php-graylog2)
*    PHP/Monolog (Monolog GelfHandler)
*    Postfix
*    Puppet
*    Python (gelfHandler)
*    Python (graypi)
*    Python (pygelf)
*    Python (python-gelfclient)
*    RabbitMQ
*    Redis
*    Resque (graylog2-resque)
*    Ruby (gelf-rb)
*    Ruby/Rack (graylog2_exceptions)
*    Ruby/Yell (yell-adapters-gelf)
*    Sidekiq (sidekiq-gelf)
*    Snort
*    Squid
*    SSH daemon
*    Sudo Command
*    systemd (journal2gelf)
*    systemd (SystemdJournal2Gelf)
*    Ubuntu Linux UFW firewall log values

*    syslog-ng
*    rsyslog
*    GELF over HTTP

]


---

template: inverse

# Live-Demo

???

http://ec2-54-93-59-43.eu-central-1.compute.amazonaws.com/

```
logger --priority local0.info "Hello World"
```

```
curl -XPOST localhost:12201/gelf -p0 -d '{"short_message":"Hello there", "host":"example.org", "facility":"test", "_foo":"bar"}' -v
```


---

template: normal

# Installation

.left-column[

Manuell

<small></small>

]
.right-column[
* <a href='https://www.graylog2.org/resources/documentation/general/packages'>Package repository</a> (Debian, Ubuntu, CentOS)
* Custom (Source)
]

<div class='clear'></div>

.left-column[

Automatisch

<small><abbr title='Configuration Management'>CM</abbr>-Pakete direkt angeboten</small>
]
.right-column[
* <a href='https://github.com/Graylog2/graylog2-ansible-role'>Ansible</a>
* Puppet
* Chef
]

---
# Alternativen

.left-column[
Zentralisiert loggen
]

.right-column[

* OpenSource
  * ELK (ElasticSearch, Logstash, Kibana)
  * Splunk
  * Fluentd
* Hosted
  * Papertrail
  * NewRelic
* <a href='http://jasonwilder.com/blog/2012/01/03/centralized-logging/'>Mehr</a>, <a href='http://blog.takipi.com/the-7-log-management-tools-you-need-to-know/'>Noch mehr</a>

]

---

template: inverse

# Fin.

**Stefan Wienert**

pludoni GmbH

<a href='https://twitter.com/stefanwienert'>@stefanwienert</a> / github.com/zealot128

[Ansible Playbook Demo-Server]( https://github.com/zealot128/wdcm-graylog-exampleserver)
