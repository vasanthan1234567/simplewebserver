# EX01 Developing a Simple Webserver
## Date: 25/03/2025
## Name: vasanthan.n
## AIM:
To develop a simple webserver to serve html pages and display the Simple HTML Text Page.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple HTML Page</title>
</head>
<body>
    <h1>Welcome to My Simple HTML Page</h1>
    <p>This is a basic HTML page with a heading and a paragraph.</p>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',80)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```


## OUTPUT:

![WhatsApp Image 2025-03-25 at 10 40 51_66f95421](https://github.com/user-attachments/assets/644f5415-aea0-4352-9429-1150486cf75c)

![WhatsApp Image 2025-03-25 at 10 40 57_51989575](https://github.com/user-attachments/assets/cec3a7c5-4ec8-4015-8441-6e352b32e3d7)


## RESULT:
The program for implementing simple webserver is executed successfully.
