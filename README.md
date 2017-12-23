# xymon_freebsd-pkg

#### Dependencies 

* zsh
* sudo

#### Configuration

* add this to : /usr/local/www/xymon/client/etc/clientlaunch.cfg

~~~
[pkg]
        ENVFILE $XYMONCLIENTHOME/etc/xymonclient.cfg
        CMD /usr/local/www/xymon/client/ext/pkg
        LOGFILE /usr/local/www/xymon/client/logs/pkg.log
        INTERVAL 25m
~~~

* add this to : /usr/local/etc/sudoers

~~~
xymon ALL=NOPASSWD:/usr/sbin/pkg audit -F
xymon ALL=NOPASSWD:/usr/sbin/pkg upgrade --dry-run
xymon ALL=NOPASSWD:/usr/sbin/pkg -vv
xymon ALL=NOPASSWD:/usr/sbin/pkg -v
~~~
