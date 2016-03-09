## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.
\\\ 

1. The protocol, which determines how the server and the browser communicate

\\\ 

2. The domain, which identifies the server

\\\ 

3. The path, which points to the leads to the files to actually load

\\\

 4. The port, which usually remains unspecified

\\\

 5. Query strings, a way of passing data entered on the web page to the server

\\\

 6. Sometimes anchor tags which lead to a certain spot on the page 

 \\\

* Name the pieces of the following urls:
	* `https://www.google.com/`

  \\\

  protocol: https domain: google.com

	* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`

  \\\

  protocol: https domain: workbook.galvanize.com path: /cohorts/41/learning_experience/367

  \\\

	* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`

  \\\

  protocol: http domain: localhost port: 5000 path: /puppies query string: ?onlycute=1&size=medium anchor tag: #firstpuppy

  \\\

	* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`

  \\\

  protocol: https domain: wikipedia.org path: /wiki/List_of_HTTP_status_codes anchor: #4xx_Client_Error

  \\\

* Can a server use more than 1 port?

\\\

A server can connect clients to different ports and can itself connect to clients with different ports

\\\

* Why is https different than http?

\\\

The s stands for secure. HTTTPS encrypts communication between the server and the client whereas http does not.

\\\

* How does a server interpret the following url's query paramter.  What data structure does it create on the server?

```
http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie
```

\\\

This creates an array. puppies = [fido, moxie]

\\\

__HTTP Request/Response__

* Name at least 4 http verbs

\\\

GET, POST, DELETE, PUT

* What is each verb useful for in your own words

\\\

GET is used to request resources from the server such as html, javascript or css files.

\\\

POST is used to send (a limited amount of) data to the server

\\\

DELETE is used to remove existing information

\\\

PUT is used to update existing information

\\\

* What does idempotent mean?

\\\

Operations are idempotent if they can be performed multiple times and produce the same result, i.e. without damaging any resources.

\\\

* Name the 5 http status code ranges.  What are they used for in general?

\\\ 

100 -in progress, continue 200- successful, 300- redirect 400- client-side error 500- server-side error

\\\

* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

\\\

Redirect to https://www.google.com/

\\\

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept

  \\\

  Used for requests

  \\\

	* Content-type

  \\\

  Used for both

  \\\

	* User-agent

  \\\

   Used for requests

  \\\

	* Set-cookies

  \\\

  Used for responses

  \\\

	* Cache-control

  \\\

  Used for both

  \\\

	* Cookie

  \\\

  Used for requests

  \\\

* Is the following a http request or response?  How do you know for each?

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>
```

\\\

A response, since it starts with a status code not a verb

\\\

```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```
\\\

A request, since it starts with a verb

\\\

__JSON__

* Describe what JSON is.  What is it used for.

\\\

JSON is a way of transfering data asynchronously between servers and clients in key value pairs similar to javascript objects, whcih makes it easy to convert to javascript.

\\\

* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}
```
\\\

var obj = JSON.parse('{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}');
console.log(obj.age);

\\\

* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}
```

\\\

var obj = JSON.parse('{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"}, { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"}, { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"}, { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}]}');
obj.Companies.forEach(function(el) {
  console.log(el.company);
});

\\\

* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};

\\\

var str = "company: " + myObj.company + ", age: " + myObj.age + ", categories: " + myObj.Education;
console.log(str);

\\\

```
__MISC__

* Describe what DNS is.

\\\

DNS, or Domain Name System, is a set of servers that allow people to type in a regular web address and have the domain replaced by an IPA

\\\

* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

\\\

-v for verbose, returns more detailed information about the results of an operation
-X followed by an http request will cause curl to execute it instead of the default, GET

\\\

* What is TCP/IP?  How does it interact with HTTP?

\\\
 
TCP/IP is a protocol for transfering information that works beneath http. IP transfers data in packets and TCP ensures that all packets are transfered at a certain pace and puts them back in the right order. HTTP works at a higher level above this process, requesting and interpreting the requested resources.

\\\

* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?

\\\

No. IP

\\\