### Datadog API connect

<img src="apic.png">

### creating dashboard from api 

```
curl -X POST "https://api.datadoghq.com/api/v1/dashboard" \
-H "Content-Type: application/json" \
-H "DD-API-KEY: " \
-H "DD-APPLICATION-KEY: " \
-d '{
  "title": "Ashutoshh Trainer 3 Overall CPU Usage Dashboard",
  "description": "Dashboard showing CPU usage across all Datadog agent hosts",
  "widgets": [
    {
      "definition": {
        "type": "timeseries",
        "requests": [
          {
            "q": "avg:system.cpu.user{*}",
            "display_type": "line",
            "style": {
              "palette": "dog_classic",
              "line_type": "solid",
              "line_width": "normal"
            }
          }
        ],
        "title": "Average CPU Usage (User Time)"
      }
    }
  ],
  "layout_type": "ordered"
}'

```

### listing dashboard 

```
 curl -X GET "https://api.datadoghq.com/api/v1/dashboard" \ 
 -H "Content-Type: application/json" \
 -H "DD-API-KEY: " \
 -H "DD-APPLICATION-KEY: "
```

## Database Monitoring 

### installing Mariadb-server

```
yum install mariadb105-server -y

===> starting database service 
 
systemctl enable --now mariadb

===> setting admin password of DB 

mysql_secure_installation  

```