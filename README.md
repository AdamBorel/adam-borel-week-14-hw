## Week 14 Homework Submission

*Created by: Adam Borel*

---

### HTTP Requests and Responses

---

##### 1. What type of architecture does the HTTP request and response process occur in?

###### *HTTP requests occur in the client/server based architecture.*

##### 2. What are the different parts of an HTTP request?

###### *Request line, header, and white space.*

##### 3. Which part of an HTTP request is optional?

###### *The request body is optional.*

##### 4. What are the three parts of an HTTP response?

###### *Status line, header, and response body.*

##### 5. Which number class of status codes represents errors?

###### *Class 4 for client and 5 for server errors.*

##### 6. What are the two most common request methods that a security professional will encounter?

###### *GET and POST requests.*

##### 7. Which type of HTTP request method is used for sending data?

###### *POST requests*

##### 8. Which part of an HTTP request contains the data being sent to the server?

###### *The request body is the part of an HTTP request that contains the data being sent to the server.*

##### 9. In which part of an HTTP response does the browser receive the web code to generate and style a web page?

###### *The User-Agent response body receives the web code to generate and style a web page.*

---

### Using Curl

---
##### 10. What are the advantages of using `curl` over the browser?

###### *The advantages of using curl over the browser is that curl is simple and flexible, but still able to complete complex tasks that the browser may not support.*

##### 11. Which `curl` option is used to change the request method?

###### *`-X` or `--request`*

##### 12. Which `curl` option is used to set request headers?

###### *`-H`*

##### 13. Which `curl` option is used to view the response header?

###### *`-I`*

##### 14. Which request method might an attacker use to figure out which HTTP requests an HTTP server will accept?

###### *OPTIONS request*

---

### Sessions and Cookies

---

##### 15. Which response header sends a cookie to the client?

```
XXXXXXXXXX HTTP/1.1 200 OK XXXXXXXXXX
XXXXXXXXXX Content-type: text/html---- XXXXXXXXXX
>>>>>>>>>>Set-Cookie: cart=Bob<<<<<<<<<<
```

###### *`Set-Cookie: cart=Bob`*

##### 16. Which request header will continue the client's session?

```
----GET /cart HTTP/1.1----
----Host: www.example.org----
>Cookie: cart=Bob<
```

###### *`Cookie: cart=Bob`*

---

#### Example HTTP Requests and Responses

---

#### HTTP Request

```POST /login.php HTTP/1.1
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

###### *`POST`*

##### 18. Which header expresses the client's preference for an encrypted response?

###### *`Upgrade-Insecure-Requests: 1`*

##### 19. Does the request have a user session associated with it?

###### *NO*

##### 20. What kind of data is being sent from this request body?

###### *The user is filling out a form for `username` and `password`*

#### HTTP Response

```HTTP/1.1 200 OK
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

##### 21. What is the response status code?

###### *`200`*

##### 22. What web server is handling this HTTP response?

###### *`Apache`*

##### 23. Does this response have a user session associated to it?

###### *Yes `Set-Cookie: SessionID=5`*

##### 24. What kind of content is likely to be in the [page content] response body?

###### *Code of the website itself.*

##### 25. If your class covered security headers, what security request headers have been included?

###### *`Strict-Trasnport-Security`*

---

#### Monoliths and Microservices

---

##### 26. What are the individual components of microservices called?

###### *Services*

##### 27. What is a service that writes to a database and communicates to other services?

###### *API*

##### 28. What type of underlying technology allows for microservices to become scalable and have redundancy?

###### *Containers*

---

#### Deploying and Testing a Container Set

---

##### 29. What tool can be used to deploy multiple containers at once?

###### *Docker*

##### 30. What kind of file format is required for us to deploy a container set?

###### *Docker YAML File*

---

#### Databases

---

##### 31. Which type of SQL query would we use to see all of the information within a table called `customers`?

###### *`SELECT*FROM customers;`*

##### 32. Which type of SQL query would we use to enter new data into a table? (You don't need a full query, just the first part of the statement.)

###### *`INSERT INTO`*

##### 33. Why would we never run `DELETE FROM <table-name>;` by itself?

###### *Because it will delete the whole table unless we use a `WHERE` clause!*

---

#### Bonus

---

##### 1. Did you see any obvious confirmation of a login?

###### *NO*

##### 2. How many items exist in this file?

###### *4*

##### 3. Is it obvious that we can access the Dashboard? (Y/N)

###### *No it isn't obvious.*

##### 4. Look through the output where Dashboard is highlighted. Does any of the wording on this page seem familiar? (Y/N) If so, you should be successfully logged in to your Editor's dashboard.

###### *Yes, it looks like the dashboard to me!*

##### 5. Finally, write a `curl` command using the same `--cookie ryancookies.txt` option, but attempt to access `http://localhost:8080/wp-admin/users.php.`. What happens this time?

###### *`<div class="wp-die-message"><h1>You need a higher level of permission.<h/1><p>Sorry, you are not allowed to list users.</p></div></body>`*
###### *Still unable to view the `userlist` because of permission issues.*