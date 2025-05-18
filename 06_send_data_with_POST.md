# Sending Data with POST
* A new bestseller book arrived! As a librarian, you wish to add that book to the library.
*  we will learn how to add a book via POST request with a JSON Body to submit book data to our Postman Library API database.
*  Acc to the postman API documentation
*  https://documenter.getpostman.com/view/15567703/UVyxRtng#e0dbc14c-371d-4813-97c3-281de36fad0c

## What is BODY?
* You will need to send body data with requests whenever you need to add or update structured data.
* For example, if you're sending a request to add a new customer to a database, you might include the customer details in JSON data format.
* Typically, you will use body data with PUT, POST, and PATCH requests.
* The Body tab in Postman enables you to specify the data you need to send with a request. You can send different types of body data to suit your API.
* You can use raw body data to send anything you can enter as text. Use the raw tab, and the type dropdown list to indicate the format of your data (Text, JavaScript, JSON, HTML, or XML), and Postman will enable syntax-highlighting and appending the relevant headers to your request.

## Les send a POST request
* CReate a new request
* Set the request to POST
* Keep the usrl : {{baseuRL}}/books
* Now we set them, to add a new book, we need to send the data of book details as well
* Acc to postman API, it accepts the data in JSON format as we already saw
* So go to body tab and selct raw and select JSON in the drop down
* Now past the JSON format of book details in the text box

![BdRh1xGJbRu2ut](https://github.com/user-attachments/assets/3c073665-0496-4e99-ada4-0bf3808e22bf)




```json
{
  "title": "BRL BOOK",
  "author": BRL",
  "genre": "Delulu",
  "yearPublished": 2004
}
```
* Now save and send the request

# BUT IT FAILS with a 401 ERROR
* remember? 4xx errors are client error?
* 401 goes for Unauthorized error
* Since we are updating some data into postman database, we need to authenticated before doing thattt


![BdRh1xGJbRu2ut](https://github.com/user-attachments/assets/0af2a83f-6833-4302-a130-d28c31c552c4)

# Add an AUthorization Header
* Some APIs require Authorization (aka Auth) for certain endpoints in order to permit a request.

## Authorization
* Think about why you might not want an API to have completely open endpoints that anyone can access publicly. It would allow unauthorized people to access data they shouldn't see, or allow bots to flood an API with thousands of calls per second and shut it down.
* There are multiple methods for authorizing a request. Some examples are
    * Basic Auth (username and password),
    * OAuth (delegated authorization), 
    * API Keys (secret strings registered to a developer from an API portal). 
## Getting an API Key
* APIs that use API Key auth usually allow developers to sign up in a developer portal, where they will receive a random API Key that can be used to authorize their requests to the API. The API Key allows the API to track who is making calls and how often.
* The Postman Library API v2 uses very light protection and does not require you to register for an API Key. You simply have to know it:
    * Header name: api-key
    * Header value: postmanrulz
* As the documentation shows, the Postman Library API v2 requires adding this header to any requests for **adding, updating and deleting books**, since these operations change data in the database instead of simply reading them.

# Headers

* Headers are how we can add metadata about our requests, such as authorization information or specify the data type we want to receive in a response.
* This is different than the actual payload data we send in the body of a request, such as our new book information.
* You can think of headers like the outside of an envelope when you send a letter.
* The envelope has information about delivering the letter, like proof that you've paid for postage. The actual data "payload" is the letter inside the envelope.

## process
* Now, in the add a book request, Go to Headers Tab
* Fill the key value values as api-key, postmanrulz
* Now save and send the request
* IT SHOW 201 Created status which means, We are SUCCEEDED
```json
{
    "id": "b28adc4a-7dbb-4b9d-9870-db91d4b8db82",
    "title": "BRL Book",
    "author": "BRL",
    "genre": "delulu",
    "yearPublished": 2004,
    "checkedOut": false,
    "isPermanentCollection": false,
    "createdAt": "2025-05-06T05:29:27.721Z"
}
```

# NOW YOU can test if book is added or Not..
* {{baseURL}}/books?genre=delulu
* {{baseURL}}/books?search=BRL
```json
[
    {
        "id": "b28adc4a-7dbb-4b9d-9870-db91d4b8db82",
        "title": "BRL Book",
        "author": "BRL",
        "genre": "delulu",
        "yearPublished": 2004,
        "checkedOut": false,
        "isPermanentCollection": false,
        "createdAt": "2025-05-06T05:29:27.721Z"
    }
]
```

# ANother Way for Auth
# Use postman AUTH!
* Postman has an Auth helper that makes authorizing requests even easier!
* https://learning.postman.com/docs/sending-requests/authorization/authorization/
* Delete the api-key HEader you created Earlier
* Hover over the api-key header in the Headers tab and click the "x" icon at the right to delete the header. Save your request.

## Add AUth to collection
* The Postman Auth helper can help you add authorization at the request, folder or collection level. Let's add the api-key to our entire collection so that all requests will send the key.
* Instead of adding auth details to every request, we are adding it to entire collection
    * click on collection namr
    * Click authorization
    * Set authorization type to API Key
    * Enter api key and value <api-key, postmanrulz>
    * And put the type to HEADER
    * and SAVE
* Now Go back to the POST request and send it now (We deleted the header)
* AND it goes without ERROR






