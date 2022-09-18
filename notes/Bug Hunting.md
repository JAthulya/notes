establish own TCP connection
> nc {ip address} 80

**browser makes 'GET' request**
>GET / HTTP/1.1
>Host: www.google.com
>Connection: keep-alive
>Accept : application/html,  * / *
>User-Agent: ksjfsflkjlsfj


1- path
2- host header
3- connection header -> indicates the request to keep the connection with the server open to avoid the overhead of constantly opening and closing connection. 
4- expected response format at here -> expecting ' application/html ' but will accept any format as indicated by the wildcard(  * / * ) ex- application/html, application/json, application/octet-stream, text/plain. 
5- user agent- denotes the software resposible for sending the request. 

If connection is complete browser makes a GET request. 
FIrst page of a website is in root path ( / )
IP addresses can host multiple domains. 

**Server Response** 
>HTTP/ 1.1 200 OK
>Content-Type: text/html
><html><head><title>Google.com</title></head><body> 
<body>
--snip--
</body>
</html>

HTTP response was recieved. status code is 200 adhering to HTTP/1/1. 200 code typically indicate a request was successful. 
--snip-- -> content of the body
content-type header informs the browsers about the medai type of the body. but browsers dont always use the value returned from an application, instead browsers perform MIME sniffing. reading the first bit of the body contents to determine the media type for themselves. applications can disable this browser behavior by including the header *X-Content-Type-Options:nosniff*
response codes starting with 3 indicate a redirection, which instructs ur broser to make an additional request. ex- if google theoretically needed to permanently redirect u from one url to another, it could use 301 response. 302 is temporary redirect. when 3xx response is received, ur browser should make a new HTTP request to the URL defined in a Location header
-----------HTTP/1.1 301 Found
-----------Location: https://www.google.com/

responses start with 4 typically indicate a user error, 403 request doesn't include proper identification to authorize access to content despite providing valid HTTP request. responses start with 5 indicate some type of server error. 503 server is unavailable to handle the send request. 

**100-199 - Information Response**

These are sent to tell the client the first part of their request has been accepted and they should continue sending the rest of their request. These codes are no longer very common.

**200-299 - Success**

This range of status codes is used to tell the client their request was successful.

**300-399 - Redirection**

These are used to redirect the client's request to another resource. This can be either to a different webpage or a different website altogether.

**400-499 - Client Errors**

Used to inform the client that there was an error with their request.

**500-599 - Server Errors**

This is reserved for errors happening on the server-side and usually indicate quite a major problem with the server handling the request.




**200 - OK**

The request was completed successfully.

**201 - Created**

A resource has been created (for example a new user or new blog post).

**301 - Permanent Redirect**

This redirects the client's browser to a new webpage or tells search engines that the page has moved somewhere else and to look there instead.

**302 - Temporary Redirect**

Similar to the above permanent redirect, but as the name suggests, this is only a temporary change and it may change again in the near future.

**400 - Bad Request**

This tells the browser that something was either wrong or missing in their request. This could sometimes be used if the web server resource that is being requested expected a certain parameter that the client didn't send.

**401 - Not Authorised**

You are not currently allowed to view this resource until you have authorised with the web application, most commonly with a username and password.

**403 - Forbidden**

You do not have permission to view this resource whether you are logged in or not.

**405 - Method Not Allowed**

The resource does not allow this method request, for example, you send a GET request to the resource /create-account when it was expecting a POST request instead.

**404 - Page Not Found**

The page/resource you requested does not exist.

**500 - Internal Service Error**

The server has encountered some kind of error with your request that it doesn't know how to handle properly.

**503 - Service Unavailable**

This server cannot handle your request as it's either overloaded or down for maintenance.