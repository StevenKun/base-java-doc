```


wget -N --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh && chmod +x bbr.sh && bash bbr.sh
```

bbr一键脚本

```
yum -y install ntp
ntpdate pool.ntp.org
systemctl start ntpd
```

时钟矫正，则可能出现I/O错误等问题