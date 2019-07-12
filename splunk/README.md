# v7.2.1
This is a Dockerfile setup for splunk - http://www.splunk.com


By default, the 60-day enterprise free trial is installed, but this can be changed to the free 500MB/day version at any time.

## Usage

```
docker run -d -p 8000:8000 -p 8089:8089 -p 9997:9997 -p 514:514 -v /mnt/user/appdata/splunk:/opt/splunk/var -v /mnt/user/appdata/splunk:/opt/splunk/etc --name splunk zyphermonkey/splunk
```

Once the container is running, browse to: `http://<host>:8000` to complete the setup.

## Volumes

* `/opt/splunk/var` For the splunk app data and configuration.
* `/data` For monitoring the local host. Can be mapped to /var/log for instance.
* `/license` For loading an enterprise license in the app.

All three volumes are optional, but to have a persistent install, you should map /opt/splunk/var.
