# JAVASCRIPT HTTP-Requests

Use the fetch() function and promises [.then()] to handle HTTTP requests <br>
 
|4 Common HTTP requests |
|:----------:|
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

The fetch() call takes 2 arguments: an endpoint and an object. <BR>
The object contains 2 properties: 
    1. method, with a value of 'POST', and 
    2. body, with a value of JSON.stringify({id: '200'});. 
This second argument determines that this request is a POST request and what information will be sent to the API.<BR>
A successful POST request will return a response body, which will vary depending on how the API is set up.<BR>
The rest of the request is identical to the GET request. <BR>
A .then() method is chained to the fetch() function to check and return the response as well as throw an exception when a network error is encountered. <BR>
A second .then() method is added on so that we can use the response however we may choose. <BR>
### 2 STEPS in a POST REQUEST:
1st SET UP THE POST REQUEST by providing the endpoint and an object with additional information about the POST.<br>

    - In the fetch() function add
        - fetch(endpoint argument, An object with POST info) 
        
2nd Handle the POST request

    - the request returns a Promise either resolved or rejected
      - Resolved - check response ok and then return response (a json ojbec)
      - Rejected - return error message
    - A .then method will handle the returned object if resolved
To Chain .then method syntax:

      fetch(url, {
        property: value, 
        property: value
      }).then(respose => {
       if(response.ok){
            return response.json();
        } throw new Error('Request failed!');
      }, networkError => {
          // Previous code
      ).then(
          (jsonResponse) => {
          rendersResponse(jsonResponse); //renderResponse is a helper function in a module  
          }                              // it will take the jsonResponse and do something with the information 
      ););
## Async GET Requests

![image](https://github.com/nafizjiwa/JAVASCRIPT-HTTP-Requests/assets/56348190/c4f343a9-bd81-4593-8b6a-dbd57b24a266)

## Async POST Requests
![image](https://github.com/nafizjiwa/JAVASCRIPT-HTTP-Requests/assets/56348190/0aeb4a5a-4a77-4660-acff-66f4b630b174)

Async arrow function syntax:

    const functionName = async () => {}






      
