## Week 14 Homework Submission

*Created by: Adam Borel*

---

### HTTP Requests and Responses

##### 1. What type of architecture does the HTTP request and response process occur in?

*HTTP requests occur in the client/server based architecture.*

##### 2. What are the different parts of an HTTP request?

*Request line, header, and body.*

##### 3. Which part of an HTTP request is optional?

*The body is optional.*

##### 4. What are the three parts of an HTTP response?

*Status line, header, and body.*

##### 5. Which number class of status codes represents errors?

*The 4th class.*

##### 6. What are the two most common request methods that a security professional will encounter?

*GET and POST.*

##### 7. Which type of HTTP request method is used for sending data?

*POST*

##### 8. Which part of an HTTP request contains the data being sent to the server?

*The request body is the part of an HTTP request that contains the data being sent to the server.*

##### 9. In which part of an HTTP response does the browser receive the web code to generate and style a web page?

*The User-Agent response header receives the web code to generate and style a web page.*

---

### Using Curl

##### 10. What are the advantages of using `curl` over the browser?

*The advantages of using curl over the browser is that curl is simple and flexible, but still able to complete complex tasks that the browser may not support.*

##### 11. Which `curl` option is used to change the request method?

*`-X` or `--request`*

##### 12. Which `curl` option is used to set request headers?

*`-H`*

##### 13. Which `curl` option is used to view the response header?

*`-I`*

##### 14. Which request method might an attacker use to figure out which HTTP requests an HTTP server will accept?

*OPTIONS request*

---

### Sessions and Cookies

##### 15. Which response header sends a cookie to the client?

~~HTTP/1.1 200 OK~~
~~Content-type: text/html~~
Set-Cookie: cart=Bob

*`Set-Cookie: cart=Bob`*

##### 16. Which request header will continue the client's session?

~~GET /cart HTTP/1.1~~
~~Host: www.example.org~~
Cookie: cart=Bob

*`Cookie: cart=Bob`*

### Example HTTP Requests and Responses

##### HTTP Request

```
POST /login.php HTTP/1.1
Host: example.com
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 34
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.132 Mobile Safari/537.36

username=Barbara&password=password
```

##### 17. What is the request method?

*`POST`*

##### 18. Which header expresses the client's preference for an encrypted response?

`Upgrade-Insecure-Requests: 1`

##### 19. Does the request have a user session associated with it?

>*Yes*, `User-Agent: Mozilla/5.0 >?(Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36`

#### 20. What kind of data is being sent from this request body?


###### *The user is filling out a form for `username` and `password`*

#### HTTP Response

```
HTTP/1.1 200 OK
Date: Mon, 16 Mar 2020 17:05:43 GMT
Last-Modified: Sat, 01 Feb 2020 00:00:00 GMT
Content-Encoding: gzip
Expires: Fri, 01 May 2020 00:00:00 GMT
Server: Apache
Set-Cookie: SessionID=5
Content-Type: text/html; charset=UTF-8
Strict-Transport-Security: max-age=31536000; includeSubDomains
X-Content-Type: NoSniff
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block

[page content]
```

#### 21. What is the response status code?

###### *`200`*

##### 22. What web server is handling this HTTP response?

*`Apache`*

##### 23. Does this response have a user session associated to it?

*Yes `Set-Cookie: SessionID=5`*

##### 24. What kind of content is likely to be in the [page content] response body?

*Some sort of Bank account?*

##### 25. If your class covered security headers, what security request headers have been included?

*`Strict-Trasnport-Security`*

---

### Monoliths and Microservices

##### 26. What are the individual components of microservices called?

*Front End Servers, Back End Severs, and Databases?*

##### 27. What is a service that writes to a database and communicates to other services?

*The Back-end Server?*

##### 28. What type of underlying technology allows for microservices to become scalable and have redundancy?

*Containers?*

---

### Deploying and Testing a Container Set

##### 29. What tool can be used to deploy multiple containers at once?

*Docker?*

##### 30. What kind of file format is required for us to deploy a container set?

*An Ansible Playbook?*

---

### Databases

##### 31. Which type of SQL query would we use to see all of the information within a table called `customers`?

*Read?*

##### 32. Which type of SQL query would we use to enter new data into a table? (You don't need a full query, just the first part of the statement.)

*Create?*

##### 33. Why would we never run `DELETE FROM <table-name>;` by itself?

*Because we will delete the entire database vs deleting an individual piece of data within the table?*

### Bonus
