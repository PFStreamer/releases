## Introduction
Perfect Streamer® is software for delivering digital streams of television channels via public Internet network anywhere in the world in Point-to-Point mode.

It uses proprietary protocol Perfect Stream that ensures reliable and stable video stream delivery without using expensive networks.

Also, standard transport protocols Pro-MPEG, SRT and RIST are supported. This allows to organize channels both via Perfect Streamer® and other software or hardware supporting the protocols.

Perfect Streamer® is a powerful software for delivering video streams over the public Internet using the transport protocols SRT, RIST, HLS, ProMpeg, PS1 and many others. 
The program has the functionality of stream reservation, EPG server, Multiplexor and Demultiplexor, EIT generator, professional analyzer, charts, AES encryption, mosaic, modification of metadata in MPEG-TS, works with DVB cards, etc. Unique functions of stream synchronization and jitter elimination, correction of PCR marks in the video stream. Integration with monitoring systems Zabbix, Grafana and others. There is a free Demo version for 10 streams and a fully functional paid version.

You can find our site [here](https://pstreamer.tv) or read [documentation](http://doc.pstreamer.tv/en/index.html).

## Demo version features
- Limited by 10 streams
- No limitations of functionality
- No time limitations

There is also 30-days trial-version without any limitations.

## Installation

### Install to Redhat family  (el7, el8)

Install pstreamer repo (el7):
```
$ sudo yum-config-manager --add-repo=http://repo.pstreamer.tv/pub/pstreamer/pstreamer.repo
```
or el8:
```
$ sudo yum config-manager --add-repo=http://repo.pstreamer.tv/pub/pstreamer/pstreamer.repo
```

Install pstreamer:
```
$ sudo yum -y install pstreamer
```

Complete remove:
```
$ sudo yum -y remove pstreamer aksusbd
```

### Install to Debian family (Ubuntu etc.)

```
$ sudo wget http://repo.psts.info/pub/deb/dists/pstreamer/pstreamer.list -O /etc/apt/sources.list.d/pstreamer.list     
$ sudo apt-get update
$ sudo apt-get install pstreamer
```
Complete remove:
```
$ sudo apt-get remove pstreamer aksusbd
```
### After the installation

Files:
```
/usr/local/bin/pss - pstreamer binary file
/opt/pss/config/pss.properties - global options
/opt/pss/config/pss_default.json - default configuration file
/usr/lib/systemd/system/pss.service - systemd service file
/var/log/pss - directory log files location
```
After install new package make trial activation:
```
$ /opt/pss/tools/activate.sh
```
After install new package use default web access:
* port: 8808
* login: admin
* password: admin

Service manipulations:
```
$ systemctl stop pss
$ systemctl start pss
$ systemctl restart pss
$ systemctl status pss
```

Hasp package: **aksusbd**

Hasp services: **hasplmd aksusbd**

If have start problem see log:
```
$ tail -n 20 /var/log/pss/main.log
$ journalctl -u pss -n 20
```
Check installed binary:
```
$ pss -h
```

