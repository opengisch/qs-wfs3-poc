# QGIS Server poc WFS3

QGIS Server as fastcgi app on port 9993. Traffic is running through a front nginx. Projects are derived from
URL path.

```shell
docker-compose up
```

[Collections of test project](http://test.localhost:8080/wfs3/collections)

## Known issues:
- Starting with QGIS 3.30 the WFS3 seems to have issues with `.` chars in layer names. Until 3.28 it was working
correctly.
- including FCGI params from file is not working as expected. They need to be defined directly in the nginx conf probably because there are other ones included first (its handled as an array so first match serves!) => would need further investigation.

