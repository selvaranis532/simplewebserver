# EX01 Developing a Simple Webserver
## Date:8/10/24

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<body><pre>
<h1>Laptop configuration(24901160)</h1>
<ul>
<li>Device name       selvarani</li>
<li>Processor         AMD A8-6410 APU with AMD Radeon R5 Grapics</li>
<li>Installed ram     8.00GB (6.95GB usable)</li>
<li>Device id         4FC9B20B-F792-4299-B203-297ADE2E7E3C</li>
<li>Product id        00327-30000-00000-AAOEM</li>
<li>System type       64-bit operating system,x64-based processor</li>
<li>Pen and touch     no pen or touch input is available for this display</li>
</ul>
</pre></body>
</html>
"""

class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:
![alt text](<Screenshot (3).png>)
![alt text](<Screenshot (4).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
