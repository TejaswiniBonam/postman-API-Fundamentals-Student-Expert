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



