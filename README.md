# Reloader JS

A small script to schedule page reload in a given number of milliseconds
truncated to the top of the nearest minutes, then delayed by so many milliseconds.
Maybe some examples are in order:

Reload every minute at the top of the minute
```
<script src = "reloader.js"></script>
<script>scheduleReload(60000, 0);</script> 
```

Reload every 2 minutes, 15 seconds after the minute: 6:00:15, 6:01:15, 6:02:15, etc.
```
<script>scheduleReload(120000, 15000);</script> 
```
