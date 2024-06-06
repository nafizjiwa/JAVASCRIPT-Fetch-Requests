# JAVASCRIPT HTTP-Requests

|Objective | How | What is the result of this request | What do we do with the info |
|:----------:|:----------:|:----------|:----------|
|Make HTTP GET request | Use a fetch() function | the request returns a promise (JS objects with data) | Handle the info/request with .then( ) method |

##### *****-----------------PROMISE.then( ) same as FETCH.then( )-------------------------*****

; same as  <br>

HTTP REQUESTS CAN ALSO BE MADE WITH async...await and fetch() function <br>
async...await will contain a try catch statement so .then are not needed ot handle the response object <br>

   The async keyword used as a promise creates an asynchronous function to return a promise
   The await keyword before fetch() suspends the code until the promise is resolved.

 
|4 Common HTTP requests |
|:----------:|
  |GET|
 | POST|
 | PUT|
  |DELETE|
  
    HTTP GET requests - retrieve information or data from a source (server)
                      - have no body
                      - information required by the source is included in the URL path or query string.
    
Javascript fetch() function makes requests with Promises:<br>
   FETCH API<br>

     fetch('url', { options: method/body/headers})             //Accepts a 1st Param URL & 2nd Param Options object 
      .then(                                                                              //(allows to customize the request)
           response  => {                       // then returns a promise (response callback handles success)
              console.log(response);               //that resolves to a response object 
        },                                                    (rejection callback handles failure)
           rejection => {                              //or rejects with an error message 
             console.error(rejection.message);            if a network error occurs
     );

Options object allows for customization of the request
     
#### Here the FETCH API parses the response stream as a JSON object.

     fetch('url-that-returns-JSON')
     .then(
             response => response.json();
      ).then(jsonResponse => {
             console.log(jsonResponse);
      });
- Creates a request object needed by the endpoint.<br>
- Request object sent to endpoint.<br>
<br>
## GET REQUEST

![image](https://github.com/nafizjiwa/JAVASCRIPT-Fetch-Requests/assets/56348190/a3881c0d-9916-4106-ad0e-91d7b29d53ad)

1st call the fetch() function and pass it a string URL as first argument, determining the endpoint of the request.<br>
The.then() method is chained at the end of the fetch() function<br>
1st, the response of the GET request is passed to the callback arrow function. <br>
Inside the callback function, the ok property of the response object returns a Boolean value. If there are no errors, response.ok will be true and the code will return response.json().

If response.ok is a falsy value, our code will throw an error.<br>
A second argument passed to .then() will be another arrow function that will be triggered when the promise is rejected. It takes a single parameter, networkError. <br>
This object logs the networkError if we could not reach the endpoint at all (e.g., the server is down).<br>

A second .then() method will run after the previous .then() method has finished running without error. <br>
It takes jsonResponse, which contains the returned response.json() object from the previous .then() method, as its parameter and can now be handled, however we may choose.<br>

## POST REQUEST
HTTP POST requests send new information to the source (server).

![image](https://github.com/nafizjiwa/JAVASCRIPT-Fetch-Requests/assets/56348190/efd42bc3-1032-4662-8c02-d253cee435d0)

The fetch() call takes 2 arguments: an endpoint and an object. <BR>

    The object contains 2 properties: 
        1. method: 'POST' ----> says this request is a POST
        2. body: JSON.stringify({id: '200'});  -----> submit data or info to the API

A successful POST request will return a response body, which will vary depending on how the API is set up.<BR>
The rest of the request is identical to the GET request. <BR>
A .then() method is chained to the fetch() function to check and return the response as well as throw an exception when a network error is encountered. <BR>
A second .then() method is added on so that we can use the response however we may choose. <BR>

### 2 STEPS in a POST REQUEST:
1st SET UP THE POST REQUEST using the fetch function and providing the endpoint and an a request object (contains information about the POST).<br>

        constant responsePromise = fetch(endpoint argument, request object with POST info) 
        
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


## Async…await syntax can be used with the Fetch API to handle promises.
### Async GET Requests

![image](https://github.com/nafizjiwa/JAVASCRIPT-HTTP-Requests/assets/56348190/c4f343a9-bd81-4593-8b6a-dbd57b24a266)

### Async POST Requests
The fetch() method is inside the 
   try{
   
    }catch statement{
   
   }
![image](https://github.com/nafizjiwa/JAVASCRIPT-HTTP-Requests/assets/56348190/0aeb4a5a-4a77-4660-acff-66f4b630b174)

Async arrow function syntax:

    const functionName = async () => {}






      
