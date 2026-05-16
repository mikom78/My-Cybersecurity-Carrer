1. **HTTP & HTTPS**
    -==**HTTP(Hyper Text Transfer Protocol)**==-> it's developed by **Tim Berners-Lee** and his team between **1989-1991**. is the **protocol or set of rules** that specifies how a web browser will communicate with a web server for the transmitting of webpage data, whether that is HTML, Images, Videos, etc.
    -==**HTPPS(Hyper Text Transfer Protocol Secure)**==-> is the **secure** version of **HTTP**. **HTTPS** data is **encrypted** so it stops people from seeing the data you are receiving and sending, also gives you assurances that you're talking to the correct web server and not something impersonating it.
2. **URL(Uniform Resource Locator)**
    -is the unique address used to access specific resources such as webpages, images, or documents on the internet. Often called a "web address".
   -e.g:-
      ![[URL_eg.png]]
    
	  - **==Scheme==:** This instructs on what protocol to use for accessing the resource such as HTTP, HTTPS, FTP (File Transfer Protocol).
	  - **==User==:** Some services require authentication to log in, you can put a username and password into the URL to log in.
	  - **==Host==:** The domain name or IP address of the server you wish to access.
	  - **==Port==:** The Port that you are going to connect to, usually 80 for HTTP and 443 for HTTPS, but this can be hosted on any port between 1 - 65535.
	  - **==Path==:** The file name or location of the resource you are trying to access.
	  - **==Query String==:** Extra bits of information that can be sent to the requested path. For  example, /blog?**id=1** would tell the blog path that you wish to receive the blog article with the id of 1.
	  - **==Fragment==:** This is a reference to a location on the actual page requested. This is commonly used for pages with long content and can have a certain part of the page directly linked to it, so it is viewable to the user as soon as they access the page.
   -**HTTP REQUEST**
        -It's possible to make a request to a web server with just one line **GET / HTTP/1.1** but for much richer experience, you will send other data. This other data is sent in what is called **headers**.
    -e.g:-
    ```http request
	GET / HTTP/1.1
	Host: tryhackme.com
	User-Agent: Mozilla/5.0 Firefox/87.0
    Referer: https://tryhackme.com/ 
      
    ```
    - **==Line 1==**: This request is sending the GET method, request the home page with / and telling the web server we are using **HTTP** protocol version 1.1.
    - **==Line 2==**: We tell the web server we want the website tryhackme.com.
    - **==Line 3==:** We tell the web server we are using the Firefox version 87 Browser.
    - **==Line 4==:** We are telling the web server that the web page that referred us to this one is https://tryhackme.com.
    - ==**Line 5==:** HTTP requests always end with a blank line to inform the web server that the request has finished.
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
    - **==Line 1==**: HTTP 1.1 is the version of the HTTP protocol the server is using and then followed by the HTTP Status Code in this case "200 OK" which tells us the request has completed successfully.
    - **==Line 2==**: This tells us the web server software and version number that sent the respond.
    - **==Line 3==**: The current date, time and time zone of the web server generated the message.
    - **==Line 4==**: The Content-Type header tells the client what sort of information is going to be sent, such as HTML, images, videos, pdf, XML.
    - **==Line 5==**: Content-Length tells the client how long the response is, this way we can confirm no data is missing.
    - **==Line 6==**: HTTP response contains a blank line to confirm the end of the HTTP response.
    - ==**Lines 7-14==**: The information that has been requested, in this instance the homepage.
3. **HTPP Request**
    -are a way for the client to show their intended action when making an **HTTP request**. there are alot of HTTP methods but mostly you will deal with GET & POST methods.
   -e.g:-most common **HTTP methods** ->
     - **==GET Request==**->This is used for getting information from a web server.
     - **==POST Request==**->This is used for submitting data to the web server and potentially creating new records.
     - **==PUT Request==**->This is used for submitting data to a web server to update information.
     - **==DELETE Request==**->This is used for deleting information/records from a web server.
4. **HTTP States Codes**
    -when **HTTP servers** respond, the first line always contains a **status code** the client of the the outcome of their request & potentially how to handle it. 
    -5 different ranges & common HTTP Status Codes [[HTTP Status Codes]].
5. 
