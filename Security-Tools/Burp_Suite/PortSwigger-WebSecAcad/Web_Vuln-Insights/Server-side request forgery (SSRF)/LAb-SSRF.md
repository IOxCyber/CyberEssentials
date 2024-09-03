# 1. Lab [i](https://portswigger.net/web-security/ssrf/lab-basic-ssrf-against-localhost)
- Directly go to `/admin`, it'll allow access if ![image](https://github.com/user-attachments/assets/a522f7c7-2799-4163-b318-ff66b35a9767)
- We need to find a request from the local host.
- Capture a Stock Check Request > Send it to "Repeater" > Change the StockAPI call to `Internal Page`.
- From `stockApi=http%3A%2F%2Fstock.....` to `stockApi=http://localhost/admin`
- ![image](https://github.com/user-attachments/assets/4057fa42-3da5-4004-9183-006c91770151)
- Try deleting carlos user > Observe the requested URL > Pass it to `stockApi=http://localhost/admin/delete?username=carlos` > User is deleted now.

# Lab 2: [SSRF attacks against other back-end systems](https://portswigger.net/web-security/ssrf/lab-basic-ssrf-against-backend-system)
- To Another backend system, i.e running on 192.168.0.X
- Use the Intruder module: `192.168.0.$X$:8080` > scan the ip from 1-256 > Update request with 200 code in `stockApi=http://192.168.0.154:8080/admin` > open URL in browser
- Try deleting carlos user > Observe the requested URL > Pass it to `stockApi=http://localhost/admin/delete?username=carlos` > User is deleted now.

# Lab 3: [SSRF with blacklist-based input filter](https://portswigger.net/academy/labs/launch/f97f7df5a96da8563edc18e5544b8ef962f8ee47abd9b9bb3d30706f15bff341?referrer=%2fweb-security%2fssrf%2flab-ssrf-with-blacklist-filter)
- 

# Lab 4: []()


# Lab 5: []()

