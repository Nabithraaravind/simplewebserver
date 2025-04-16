# EX01 Developing a Simple Webserver
## Date:31.03.2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.


## DESIGN STEPS:
### Step 1:
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

## Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
    <title>TCP/IP</title>
</head>
<body bgcolor="skyblue">
    <center>
        <H1>TCP/IP PROTOCOLS</H><br>
    </center>
 <h3>
    1. Application layer protocols - HTTP, FTP, SSH, DNS & TELNET<br>
    2. Transport layer protocols - TCP, UDP<br>
    3. Internet layer protocols - IPv4v6<br>
    4. Physical layer protocols - ETHERNET
    <br>
    <br>
    <br>
    <br>
    Name : A.Nabithra <br>
    Register no : 212224230172
</body>
</html>
'''
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```

## OUTPUT:
![alt text](<Screenshot 2025-04-16 183142.png>)
![alt text](<Screenshot 2025-04-16 183320.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
