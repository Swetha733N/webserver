# Developing a Simple Webserver

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1><u>Top five web application development frameworks.</u><h1>
<ul>
<li>Django</li>
<li>Angular or Angular JS</li>
<li>Laravel.</li>
<li>Meteor. </li>
<li>ASP.NET. </li>
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

### Server output:
![web ex1 serever](https://user-images.githubusercontent.com/122199934/228425561-a1b3dc55-2d0c-42fd-87dd-06e1b6e299ab.png)

### Client output:
![client output](https://user-images.githubusercontent.com/122199934/228425311-5ff5a4a7-b76c-43d6-82be-dac31a7a7a2a.png)


## RESULT:
The program is executed succesfully
