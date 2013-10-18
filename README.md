openshift-quota-monitor-cartridge
=================================

This cartridge monitors your OpenShift gear quota and notify you via mail if you exceed it.

Installation
============

First, add the cron cartridge to your app (in this example myapp).

```
rhc cartridge add cron -a myapp
```

After you're done, add the quota monitor cartridge. You also need to set your notification mail address.

```
rhc cartridge-add http://bit.ly/quotamonitor -e OPENSHIFT_QUOTAMONITOR_MAIL=admin@example.com -a myapp
```


Configuration
=============

You can set a different notification mail address in post configuration.

```
rhc set-env OPENSHIFT_QUOTAMONITOR_MAIL=operations@cloud.example.com -a myapp
``` 

You can also set the frequency in seconds at which the notification mail is send. Minimal value is 60.

```
rhc set-env OPENSHIFT_QUOTAMONITOR_PERIOD=300 -a myapp
```

License
=======

Licensed under ASL V2, http://www.apache.org/licenses/LICENSE-2.0
