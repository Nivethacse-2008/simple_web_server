# EX01 Developing a Simple Webserver

# Date:22.09.2025
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
# HTML content with colored laptop specifications
content = '''
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laptop Specifications</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f8ff; /* Light blue background */
            padding: 20px;
        }
        h1 {
            color: #2e8b57; /* Sea green title */
            text-align: center;
        }
        table {
            width: 60%;
            margin: auto;
            border-collapse: collapse;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        th, td {
            padding: 12px;
            text-align: left;
        }
        th {
            background-color: #4CAF50;
            color: white;
        }
        tr:nth-child(even) {
            background-color: #e6f2ff; /* Light blue row */
        }
        tr:nth-child(odd) {
            background-color: #ffffff; /* White row */
        }
    </style>
</head>
<body>
    <h1>Laptop Specifications</h1>
    <table>
        <tr>
            <th>Feature</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Brand</td>
            <td>Dell</td>
        </tr>
        <tr>
            <td>Model</td>
            <td>XPS 15</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>Intel Core i7-12700H</td>
        </tr>
        <tr>
            <td>RAM</td>
            <td>16 GB DDR5</td>
        </tr>
        <tr>
            <td>Storage</td>
            <td>512 GB SSD</td>
        </tr>
        <tr>
            <td>Graphics</td>
            <td>NVIDIA RTX 3050</td>
        </tr>
        <tr>
            <td>Display</td>
            <td>15.6" FHD+ (1920x1200)</td>
        </tr>
        <tr>
            <td>Battery</td>
            <td>86 WHr, 6-cell</td>
        </tr>
    </table>
</body>
</html>
```
```
class LaptopServer(BaseHTTPRequestHandler):
    def do_GET(self):
        self.send_response(200)
        self.send_header('Content-type', 'text/html')
        self.end_headers()
        self.wfile.write(content.encode('utf-8'))

# Server setup
host = 'localhost'
port = 8080
server = HTTPServer((host, port), LaptopServer)
print(f"Server running at http://{host}:{port}")
server.serve_forever()
```
# OUTPUT:
![alt text](<Screenshot 2025-09-21 112306.png>)
![alt text](<Screenshot 2025-09-21 112319.png>)


# RESULT:
The program for implementing simple webserver is executed successfully.
