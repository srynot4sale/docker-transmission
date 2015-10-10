docker-transmission
===================

Transmission Daemon Docker Container (based off the fantastic docker by elventear)

Application container, don't forget to specify a local directory for the downloads:

```
docker run -d --name transmission \
-p 12345:12345 -p 12345:12345/udp -p 127.0.0.1:9091:9091 \
-v /archive/torrents/downloads:/var/lib/transmission-daemon/downloads \
-v /archive/torrents/incomplete:/var/lib/transmission-daemon/incomplete \
-v /archive/torrents/info:/etc/transmission-daemon \
aaronb-transmission
```

Included is a systemd unit file, which will destroy the docker on host shutdown and restart (and resume torrents) on startup.

To access visit http://127.0.0.1:9091/web in your browser.
