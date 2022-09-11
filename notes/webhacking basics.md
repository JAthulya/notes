**XSS**
reflected XSS 
stored xss
DOM XSS

recognise xss vulnerabilities
- figure out where the data goes
- figure out any special handling
- figure out how special characters are handled

<script>alert(1);</script>
<a href="http://"onmouseover="alert(1);"> -> when victim hovers over that link, u have javascripting executing.
_xss cheat sheet_
- "><h1>test</h1>
- '+alert(1)+'
- "onmouseover="alert(1)
- http://"onmouseover="alert(1)

**Javascript**
chrome devtools
`XMLHttpRequest` (XHR) objects are used to interact with servers. You can retrieve data from a URL without having to do a full page refresh. This enables a Web page to update just part of a page without disrupting what the user is doing.


