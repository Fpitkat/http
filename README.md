## Part One: Solidify Terminology

### What is HTTP?
According to MDN HTTP is a protocol for fetching resources such as HTML documents. It is the foundation of any data exchange on the Web and it is a client-server protocol, which means requests are initiated by the recipient, usually the Web browser. A complete document is reconstructed from the different sub-documents fetched, for instance, text, layout description, images, videos, scripts, and more.
### What is a URL?
According to MDN URL stands for Uniform Resource Locator. A URL is nothing more than the address of a given unique resource on the Web.
### What is DNS?
According to MDN DNS (Domain Name System) is a hierarchical and decentralized naming system for Internet connected resources. DNS maintains a list of domain names along with the resources, such as IP addresses, that are associated with them.
### What is a query string?
According to Wikipedia a query string is: A query string is a part of a uniform resource locator (URL) that assigns values to specified parameters. A query string commonly includes fields added to a base URL by a Web browser or other client application, for example as part of an HTML document, choosing the appearance of a page, or jumping to positions in multimedia content
### What are two HTTP verbs and how are they different?
GET - A GET request is a request to the server to retrieve information.\
POST - A POST request is a request to the server to add new infomation. \
### What is an HTTP request?
According to MDN a HTTP request is: According to MDN a HTTP request is: HTTP defines a set of request methods to indicate the desired action to be performed for a given resource. Although they can also be nouns, these request methods are sometimes referred to as HTTP verbs. Each of them implements a different semantic, but some common features are shared by a group of them: e.g. a request method can be safe, idempotent, or cacheable.
### What is an HTTP response?
According to MDN a HTTP response status codes indicate whether a specific HTTP request has been successfully completed. Responses are grouped in five classes:

1. Informational responses (100 – 199)
2. Successful responses (200 – 299)
3. Redirection messages (300 – 399)
4. Client error responses (400 – 499)
5. Server error responses (500 – 599)


### What is an HTTP header? Give a couple examples of request and response headers you have seen.
According to MDNAn HTTP header is a field of an HTTP request or response that passes additional context and metadata about the request or response. For example, a request message can use headers to indicate it's preferred media formats, while a response can use header to indicate the media format of the returned body. Headers are case-insensitive, begin at the start of a line and are immediately followed by a ':' and a header-dependent value. The value finishes at the next CRLF or at the end of the message.
### What are the processes that happen when you type “http://somesite.com/some/page.html” into a browser?
1. Your browser “resolves” the name into an IP address using DNS
2. Your browser makes a request to that IP address, including headers (info about browser, any previous cookies, and other things)
3. The server sends a response (typically, HTML, with a status code (200 if it was sucessful)
4. The browser makes a DOM from that HTML, and finds any other resources needed (images, CSS, JavaScript, etc)
5. The browser makes separate HTTP requests for those resources and receives response from the server for each

## Part Two: Practice Tools

1. Using curl, make a GET request to the icanhazdadjoke.com API to find all jokes involving the word “pirate”
- https://icanhazdadjoke.com/search?term=pirate
3. Use dig to find what the IP address is for icanhazdadjoke.com
* icanhazdadjoke.com.	300	IN	A	104.21.66.15
* icanhazdadjoke.com.	300	IN	A	172.67.198.173
4. Make a simple web page and serve it using python3 -m http.server. Visit the page in a browser.
- python3 -m http.server 

## Part Three: Explore Dev Tools

1. Build a very simple HTML form that uses the GET method (it can use the same page URL for the action) when the form is submitted.

```
<form action="/about.html" method="get">
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname"><br><br>
  <label for="lname">Last name:</label>
  <input type="text" id="lname" name="lname"><br><br>
  <input type="submit" value="Submit">
</form>
```

2. Add a field or two to the form and, after submitting it, explore in Chrome Developer tools how you can view the request and response headers.
DONE
3. Edit the page to change the form type to POST, refresh in the browser and re-submit. Do you still see the field in the query string? Explore in Chrome how you can view the request and response headers, as well as the form data.
```
<form action="/about.html" method="post">
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname"><br><br>
  <label for="lname">Last name:</label>
  <input type="text" id="lname" name="lname"><br><br>
  <input type="submit" value="Submit">
</form>
```


