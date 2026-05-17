1. **HTTP & HTTPS**
    -<mark>**HTTP(Hyper Text Transfer Protocol)**</mark>-> it's developed by **Tim Berners-Lee** and his team between **1989-1991**. is the **protocol or set of rules** that specifies how a web browser will communicate with a web server for the transmitting of webpage data, whether that is HTML, Images, Videos, etc.
    -<mark>**HTPPS(Hyper Text Transfer Protocol Secure)**</mark>-> is the **secure** version of **HTTP**. **HTTPS** data is **encrypted** so it stops people from seeing the data you are receiving and sending, also gives you assurances that you're talking to the correct web server and not something impersonating it.
2. **URL(Uniform Resource Locator)**
    -is the unique address used to access specific resources such as webpages, images, or documents on the internet. Often called a "web address".
   -e.g:-
      ![](/images/URL_eg.png)
    
	  - **<mark>Scheme</mark>:** This instructs on what protocol to use for accessing the resource such as HTTP, HTTPS, FTP (File Transfer Protocol).
	  - **<mark>User</mark>:** Some services require authentication to log in, you can put a username and password into the URL to log in.
	  - **<mark>Host</mark>:** The domain name or IP address of the server you wish to access.
	  - **<mark>Port</mark>:** The Port that you are going to connect to, usually 80 for HTTP and 443 for HTTPS, but this can be hosted on any port between 1 - 65535.
	  - **<mark>Path</mark>:** The file name or location of the resource you are trying to access.
	  - **<mark>Query String</mark>:** Extra bits of information that can be sent to the requested path. For  example, /blog?**id=1** would tell the blog path that you wish to receive the blog article with the id of 1.
	  - **<mark>Fragment</mark>:** This is a reference to a location on the actual page requested. This is commonly used for pages with long content and can have a certain part of the page directly linked to it, so it is viewable to the user as soon as they access the page.
   -**HTTP REQUEST**
        -It's possible to make a request to a web server with just one line **GET / HTTP/1.1** but for much richer experience, you will send other data. This other data is sent in what is called **headers**.
    -e.g:-
    ```http request
	GET / HTTP/1.1
	Host: tryhackme.com
	User-Agent: Mozilla/5.0 Firefox/87.0
    Referer: https://tryhackme.com/ 
      
    ```
    - **<mark>Line 1</mark>**: This request is sending the GET method, request the home page with / and telling the web server we are using **HTTP** protocol version 1.1.
    - **<mark>Line 2</mark>**: We tell the web server we want the website tryhackme.com.
    - **<mark>Line 3</mark>:** We tell the web server we are using the Firefox version 87 Browser.
    - **<mark>Line 4</mark>:** We are telling the web server that the web page that referred us to this one is https://tryhackme.com.
    - <mark>**Line 5</mark>:** HTTP requests always end with a blank line to inform the web server that the request has finished.
   -**HTPP Respond**
        -is the message sent by a web server to a client (like your browser) in reply to an **HTTP request**. It tells the client whether the request was successful & often includes the requested data, such as a webpage or image.
    -e.g:-
    ```HTML
    HTTP/1.1 200 OK
    Server: nginx/1.15.8
    Date:Fri, 09 Apr 2021 13:34:03 GMT
    Content-Type: text/html
    Content-Length: 98
    
    <html>
    <head>
       <title>TryHackMe</title>
    </head>
    <body>
       Welcome To TryHackMe.com
    </body>
    </html>
    ```
    - **<mark>Line 1</mark>**: HTTP 1.1 is the version of the HTTP protocol the server is using and then followed by the HTTP Status Code in this case "200 OK" which tells us the request has completed successfully.
    - **<mark>Line 2</mark>**: This tells us the web server software and version number that sent the respond.
    - **<mark>Line 3</mark>**: The current date, time and time zone of the web server generated the message.
    - **<mark>Line 4</mark>**: The Content-Type header tells the client what sort of information is going to be sent, such as HTML, images, videos, pdf, XML.
    - **<mark>Line 5</mark>**: Content-Length tells the client how long the response is, this way we can confirm no data is missing.
    - **<mark>Line 6</mark>**: HTTP response contains a blank line to confirm the end of the HTTP response.
    - <mark>**Lines 7-14</mark>**: The information that has been requested, in this instance the homepage.
3. **HTPP Request**
    -are a way for the client to show their intended action when making an **HTTP request**. there are alot of HTTP methods but mostly you will deal with GET & POST methods.
   -e.g:-most common **HTTP methods** ->
     - **<mark>GET Request</mark>**->This is used for getting information from a web server.
     - **<mark>POST Request</mark>**->This is used for submitting data to the web server and potentially creating new records.
     - **<mark>PUT Request</mark>**->This is used for submitting data to a web server to update information.
     - **<mark>DELETE Request</mark>**->This is used for deleting information/records from a web server.
4. **HTTP States Codes**
    -when **HTTP servers** respond, the first line always contains a **status code** the client of the the outcome of their request & potentially how to handle it. 
    -5 different ranges & common HTTP Status Codes [[HTTP Status Codes]].
5. **Headers**
    -are additional bits of data you can send to the web server when making requests. Although no headers are strictly required when making a HTTP request, you’ll find it difficult to view a website properly.
   -**Common Request Headers**->These headers are sent from the client (usually your browser) to the server.
     - **<mark>Host</mark>**->Some web servers host multiple websites so it Specifies the domain name and port number of the server being targeted.
     - **<mark>User-Agent</mark>**->This is your browser software and version number, telling the web server your browser software helps it format the website properly for your browser & also some elements of HTML, JavaScript and CSS are only available in certain browsers.
     - **<mark>Referrer</mark>**->Includes the URL of the previous web page that linked to the current resource.
     - **<mark>Content-Length</mark>**->tells the web server how much data to expect in the web request. This way the server can ensure it isn't missing any data.
     - **<mark>Accept-Language</mark>**->Specifies the client's preferred human language. e.g:- `en-US`, `fr`.
     - **<mark>Accept-Encoding</mark>**->tells the web server what types of compression methods the browser supports so the data can be made smaller for transmitting over the internet.
     - **<mark>Accept</mark>**: Informs the server which media types (e.g., `application/json`, `text/html`) the client is able to process.
     - **<mark>Authorization</mark>**: Carries authentication credentials (e.g., API keys, Bearer tokens) to verify identity.
     - **<mark>Cookie</mark>**->Sends stored HTTP cookies back to the server to maintain state/sessions.
   -**Common Response Headers**->These headers are returned to the client from the server after a request.
     - **<mark>Set-Cookies</mark>**->:information to Used by the server to send cookies to the client's browser