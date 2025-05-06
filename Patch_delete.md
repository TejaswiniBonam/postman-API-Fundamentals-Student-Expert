# PATCH method
A PATCH request in HTTP is used to partially update an existing resource on a server. Unlike PUT requests, which replace the entire resource with a new version, PATCH only modifies specific properties or attributes of the resource, leaving the rest unchanged. 
# TASK checkout ur book
* The API documentation shows we can update a book by id by making a request (authorized with the API Key) with the updated information to:
* PATCH https://library-api.postmanlabs.com/books/:id
* And in the path variables, update id to {{new_book_id}}
* now in the body, keep the raw json text
```json
{ 
  "checkedOut": true 
}
```
* save and send
* Now ur book is updated as CHeckedOut

# TASK Delete ur book
* delete the book
* DELETE https://library-api.postmanlabs.com/books/:id
* update id to {{new_book_id}} in the path variables
* save and send
* It should show 204 no content status
* To check it it is really deleted or Not, Try sending the request again
* IT WILL SAY 404 NOT FOUND
