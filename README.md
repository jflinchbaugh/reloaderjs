# Reloader JS

A small script to schedule page reload in a given number of milliseconds
truncated to the top of the nearest minutes, then delayed by so many milliseconds.
Maybe some examples are in order:

Reload every minute at the top of the minute: 6:00:00, 6:01:00, 6:02:00, etc.
```
<script src = "reloader.js"></script>
<script>scheduleReload(60000, 0);</script> 
```

Reload every 2 minutes, 15 seconds after the minute: 6:00:15, 6:02:15, 6:04:15, etc.
```
<script>scheduleReload(120000, 15000);</script> 
```

The server must also serve headers to instruct the browser to not use cached copies
for XHR or reload. These configs can be added to the `.htaccess` file in the root 
of your web app if your Apache server allows it:
```
Header set Access-Control-Allow-Origin "*"

<IfModule mod_expires.c>
  ExpiresActive On
  ExpiresDefault A0
</IfModule>
```
