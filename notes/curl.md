This was used to debug the example application.

```shell
$ curl -v -c cookies.txt -b cookies.txt http://$IP_ADDRESS:8081
$ ls
cookies.txt
$ cat cookies.txt
# Netscape HTTP Cookie File
# https://curl.haxx.se/docs/http-cookies.html
# This file was generated by libcurl! Edit at your own risk.

#HttpOnly_192.168.1.107 FALSE   /       FALSE   0       session eyJjc3JmX3Rva2VuIjp7IiBiIjoiTkdRMVlXTXdaREF5WlRVNU9

$ # Token taken from the csrf_token input html tag from the response from the first request
$ curl -v -c cookies.txt -b cookies.txt -d "login=admin&password=admin&target=''&csrf_token=1489077789##47a42db39383c6d615267f3e93a9341b2a1b49b5" http://$IP_ADDRESS:8081/login

$
```
