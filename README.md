# JAVASCRIPT HTTP-Requests

|Objective | How | What is the result of this request | What do we do with the info |
|:----------:|:----------:|:----------|:----------|
|Make HTTP GET request | Use a fetch() function | the request returns a promise (JS objects with data) | Handle the info/request with .then( ) method |

##### *****-----------------PROMISE.then( ) same as FETCH.then( )-------------------------*****

#### HTTP REQUESTS CAN ALSO BE MADE WITH
###### async...await and fetch() function <br>
async...await will contain a try catch statement so `.then ` is not needed to handle the response object <br>

|KEYWORD | WHERE IS KEYWORD USED | WHAT IS ITS ACTION |
|:----------:|:----------:|:----------|
|async | in front of function to create an asynchronous fnc | so it can return a promise |
|await | in an async funciton place before fetch( ) | Suspends code until fetch promise is resolved |
<br>
<br>
 
|4 Common HTTP requests |
|:----------:|
  |GET|
 | POST|
 | PUT|
  |DELETE|
  
    HTTP GET requests - retrieve information or data from a source (server)
                      - have no body
                      - information required by the source is included in the URL path or query string.
    
#### FETCH API 

     fetch('url-that-returns-JSON')    ---> fetch creates a request object (promise) of info
     .then(                                                ---> needed by endpoint
             response => response.json();   ---> fetch parses the response as a JSON object
      ).then(jsonResponse => {
             console.log(jsonResponse);
      });
      
<br>

###### FETCH API can have a 2nd argrument. <br>

     fetch('url', { options: method/body/headers})             //Accepts a 1st Param URL & 2nd Param Options object 
      .then(                                                              //Optons object (allows to customize the request)
           response  => {                       // then returns a promise (response callback handles success)
              console.log(response);               //that resolves to a response object 
        },                                                    (rejection callback handles failure)
           rejection => {                              //or rejects with an error message 
             console.error(rejection.message);            if a network error occurs
     );


## GET REQUEST

![image](https://github.com/nafizjiwa/JAVASCRIPT-Fetch-Requests/assets/56348190/a3881c0d-9916-4106-ad0e-91d7b29d53ad)


| Input | Events in Diagram  | Action |
|:----------:|:----------:|:----------:|
|1st | call fetch() with URL argument | GET promise returned|
|GET response| passed to a .then() method | response passed to a callback fnc|
|callback function | checks the ok property of the response object |
| If response.ok = true | object returned successfully | return is a response.json() |
| If response.ok = falsy | call fetch() with URL argument | code will throw an error|
| Second .then() argument func triggers | if Promise rejected ||
| argument 'networkError' | if endpoint not reached/server down | object logs networkError|


1st .then() runs no errror trigger 2nd .then(). <br>
2nd .then takes returned jsonResponse (a response.json() object) as a parameter to handled how it wants.<br>

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






      
