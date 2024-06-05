# JAVASCRIPT HTTP-Requests

Use the fetch() function and promises [.then()] to handle requests <br>

|4 Common HTTP requests |
| ----------|
  |GET|
 | POST|
 | PUT|
  |DELETE|

The fetch() function:<br>

Creates a request object that contains relevant information that an API needs.<br>
Sends that request object to the API endpoint provided.<br>
Returns a promise that ultimately resolves to a response object, which contains the status of the promise with information the API sent back.<br>
## GET REQUEST
![image](https://github.com/nafizjiwa/JAVASCRIPT-Fetch-Requests/assets/56348190/a3881c0d-9916-4106-ad0e-91d7b29d53ad)

1st call the fetch() function and pass it a URL as a string for the first argument, determining the endpoint of the request.<br>
The.then() method is chained at the end of the fetch() function<br>
1st, the response of the GET request is passed to the callback arrow function. <br>
Inside the callback function, the ok property of the response object returns a Boolean value. If there are no errors, response.ok will be true and the code will return response.json().

If response.ok is a falsy value, our code will throw an error.<br>
A second argument passed to .then() will be another arrow function that will be triggered when the promise is rejected. It takes a single parameter, networkError. <br>
This object logs the networkError if we could not reach the endpoint at all (e.g., the server is down).<br>

A second .then() method will run after the previous .then() method has finished running without error. <br>
It takes jsonResponse, which contains the returned response.json() object from the previous .then() method, as its parameter and can now be handled, however we may choose.<br>

## POST REQUEST

![image](https://github.com/nafizjiwa/JAVASCRIPT-Fetch-Requests/assets/56348190/efd42bc3-1032-4662-8c02-d253cee435d0)

Notice that the fetch() call takes two arguments: an endpoint and an object that contains information needed for the POST request. <BR>
The object passed to the fetch() function as its second argument contains two properties: method, with a value of 'POST', and body, with a value of JSON.stringify({id: '200'});. <BR>
This second argument determines that this request is a POST request and what information will be sent to the API.<BR>
A successful POST request will return a response body, which will vary depending on how the API is set up.<BR>
The rest of the request is identical to the GET request. <BR>
A .then() method is chained to the fetch() function to check and return the response as well as throw an exception when a network error is encountered. <BR>
A second .then() method is added on so that we can use the response however we may choose. <BR>
