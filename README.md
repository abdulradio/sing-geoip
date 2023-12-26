# GeoIP RU

geoip contains databases of IP addresses of Russia and Belarus(MaxMind), cloudflare, cloudfront, facebook, fastly, google, netflix, telegram, twitter.

## Example Sing-box rules geoip.db

```json
"route": {
    "geoip": {
        "path": "/tmp/geoip.db",
        "download_url": "https://github.com/abdulradio/sing-geoip/releases/latest/download/geoip.db",
        "download_detour": "proxy"
    },
    "rules": [
       {   
         "geoip": "telegram",
         "outbound": "proxy"
       },  
       {
         "geoip": [
           "private",
           "ru",
           "by",
           "google"
         ],
         "outbound": "direct"
       }
    ],
    "final": "proxy",
    "auto_detect_interface": true
}
