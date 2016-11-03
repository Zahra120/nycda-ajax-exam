Instructions:

- Add your answers inline to the markdown file.
- Use your own words.
- Come up with an answer from memory. Write it down, even if the answer is "I don't know."
- Then, we will go over the answers in class. Write down your revised answer below your original answer.
- There are two intermissions. We will go over the answers to the previous parts during those times.
- Finally, submit all of your answers in a file to canvas. This is so Lloyd and I can get a sense of your understanding.

---
### Part 1: Servers - 20 minutes

1. What is a server? What does a server do?

  server is big computer that other computer as a client can send a request like
  http request and get a response, they can post something to server too.

2. What is Node.js?

	   It is serverside language for javaScript, which helps javaScript
	   runs better in serverside.
3. What is express?

	  It is a server framework that has some  function handlers to help us to run server in our applications.

4. What is a client? What does a client do?

	 client can be a browser , or application that communicate with server, like sending or receiving(with request and response object) data.

5. How do the server and the client communicate?
   	using some controlers like express.

6. Debugging:
- 6a. How do you view server logs? we see them in terminal using midelware morgan.
- 6b. How do you view client logs? in browser console.

---
### Part 2: HTTP Requests - 15 minutes

1. What is an HTTP Request?

	HTTP Request is a request that browser or client makes to server and has header and body.
	header is the meta information about request and body is  the content.

2. GET Requests
- 2a. What is a GET request?

	Get is function of express to get some data from server
- 2b. When do you use GET requests?
- 2c. How do you send data in a GET request?

	app.get('path', function(req, res){

		})

3. POST Requests
- 3a. What is a POST request?

	post is a function of express to post some data to server.
- 3b. When do you use POST requests?
- 3c. How do you send data in a POST request?
	app.post('path', function(req, res){


		});

---

### Intermission

---
### Part 3: Ajax - 15 minutes

1. Ajax
- 1a. What is Ajax?

	We use Ajax to get or post data to server in frontend( brwoser console ) through jquery, without need to reload the page or go the other page.

- 1b. When should you use Ajax?

2. Given the following code snippet:

```js
console.log("A");
$('#map').click(function(event) {
	console.log("B");
	var coordinates = convertMouseCoordinatesToGeoCoordinates(event);

	console.log("C");
	$.get('/map', { lat: coordinates.x, lon: coordinates.y }, function(response, status) {
		console.log("D");
		mapDisplay.update(response);
	});

	console.log("E");
});
console.log("F");
```

- 2a. Describe what seems to be happening.
	when we click on element with id="map",  prints,"B" and put the result of function convert in cordinates variable. print,"C" . we use Ajax that when we are in /map path or url , prints "D"
	and update the response.
- 2b. In what order is `A` through `F` printed?
	"A" +"F". then "B"+"c"+"E" if we are in /map path
	"D"
- 2c. Describe the events that happen between each letter. When does the server get hit?

---

### Intermission

---
### Part 4: Jade - 20 minutes

1. Jade
- 1a. What is Jade?
	It is a View part of our application.

- 1b. Why should we use Jade?
	It is easer to write, we can use reusable codes and components, and also it makes
	our application more dynamic.

2. Explain the difference between 'server side' JavaScript and 'client side' JavaScript.
	we deal with server side javaScript through node.js and with client side through jQuery and
	Ajax.

3. Given this example `index.jade` file:

```js
doctype html
html
	head
		script(src='boop.js')
		script.
			var x = 1;
	body
		- var y = 2;
		h2= z + y
```

- 3a. Is `x` executed server side or client side? Does the client ever see `x`? Sever side. no
- 3b. Is `y` executed server side or client side? Does the client ever see `y`? client side. yes
- 3c. Is `z` executed server side or client side? Does the client ever see `z`? client side. yes
- 3d. When is `boop.js` executed? Does the client ever see `boop.js`? It uploads before html uploading
fininsh. No Client doesn't see.

---
### Part 5: Request Lifecycle - 15 minutes

5. Given the following code snippet in an express application:

```js
app.get('/home', function (request, response) {
	response.render('index', { z: 3 } );
});
```

- 5a. List the complete order of events, starting from the browser making a `GET` request to `/home`. Assume that `index` refers to the Jade file in Part 4. Be sure to describe when each JavaScript statement (`x`, `y`, `z`, and `boop.js`) gets executed.
	 when we are /home path, the index.pug will be renderd and display 5. boop.js before of displaying 5 will load to page . first boop.js , second x, then y and z.


- 5b. What is displayed on the page?  5 .
- 5c. What is visible from 'view page source'?body part.
