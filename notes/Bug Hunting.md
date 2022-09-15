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