# EX01 Developing a Simple Webserver
## Date:26-09-24

## AIM:
To develop a simple webserver to display the configuration details of my laptop.

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
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
        <h1>
            <center>
                <b>MY LAPTOP CONFIGURATION</b>
            </center>

        </h1>
        <table align="center" border="2" cellspacing="5" cellpadding="5">
            
            <tr>
                <th>MODEL</th>
                <th>SPECIFICATION</th>
            </tr>
            <tr>
                <td>brand</td>
                <td> samsung galaxy</td>
            </tr>
            <tr>
                <td>price</td>
                <td>20000</td>
            </tr>
            <tr>
                <td>display</td>
                <td>6.6-inch full HD+screen</td>
            </tr>
            <tr>
                <td>camera</td>
                <td>50MP main</td>
            </tr>
            <tr>
                <td>performance</td>
                <td>4gb RAM</td>
            </tr>
            <tr>
                <td>
                    battery
                </td>
                <td>
                    5000 mAh
                </td>
                
            </tr>
            <tr>
                <td>storage</td>
                <td>64gb</td>
            </tr>
            <tr>
                <td>connectivity</td>
                <td>4g support, dual SIM, headphone jack</td>
            </tr>
        </table>

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
![Screenshot (83)](https://github.com/user-attachments/assets/f7101819-8698-4084-8ec6-95148ce6c883)


## RESULT:
The program for implementing simple webserver is executed successfully.
