# Check for SCAN requests on the wireless network

After reading [this article](https://www.benkuhn.net/wireless/) on wireless performance I started looking through the logs on my macbook pro. And while I didn't find any egregious I did notice that `locationd` is doing a scan about once every five minutes. I'm presuming they're using maps of SSID and GPS coordinates as one of their methods to determine the computers locations. 

1. Enable wifi logging by Option Click the wifi icon in the menu bar and then select Enable Wi-Fi Logging.
2. `tail -f /var/log/wifi* | grep 'SCAN request'`

``` shell
$ tail -f /var/log/wifi* | grep 'SCAN request'
Tue Jun 23 18:53:46.178 Info: <airportd[4568]> SCAN request received from pid 394 (WiFiAgent) with priority 2
Tue Jun 23 18:54:00.263 Info: <airportd[4568]> SCAN request received from pid 139 (locationd) with priority 2
Tue Jun 23 18:54:03.538 Info: <airportd[4568]> SCAN request received from pid 394 (WiFiAgent) with priority 2
Tue Jun 23 19:30:06.623 AutoJoin: <airportd[4568]> BEST CONNECTED SCAN request on interface en0 for network 'XXXXXXXX'
```

