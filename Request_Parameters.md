# Request Parameters
* Postman allows you to save values as variables to reuse them and easily hide sensitive information like API Keys
* We will use a variable to replace our base URL so that we don't have to type that repeatedly. Once a variable is defined, you can access its value using double curly brace syntax like this: **{{variableName}}**

### Let's set a variable
* Let's make a variable for the host that we used in the previous request.
* select the url and right click, you'll see "Set as a variable"
* CLick that and give it a name
* **Variable Names are cAsE Sensitive**
* And then Define it's scope like Global, Collection, Vault..
* And DONE
* From then it'll be represented as {{name_of_variable}}

## Where to see the Variables???
* Click on your collection name and you can get to see the variable tab
* Seems like you can even modify the variable as there are two columns called "Initial Value" and "Current Value".

![instructor_26fp2261340y1ukokimvca8su_public_1649630820_baseUrl+1 1649630820044](https://github.com/user-attachments/assets/d2abce83-e22a-4e1e-8676-4c07421d0f39)


## Query Parameters
* Minimum things required to make an API call
    * Request Type (GET, POST, PUT, PATCH, DELETE...)
    * URL
* Sometimes api calls ALLOW some parameters that Key, Value pairs
* Key-Value pairs are represented within the URL.. They start with '?' and seperated with '='
* "URL?<key>=<value>
* There might be a case where there are more than one key-value pair
* And they are seperated by '&'
* URL?<key1>=<value1>&<key2>=<value2>
### Example
* If we search "Hello" in google it goes like
* https://google.com/search?q=Hello..........
* Here '/search' is the **PATH**
* Where <q, Hello> --> Key -value pairs where q stands for query

## When to use parameters?
* Based on the documentation of API


# TASK - Search books by genre
* In the previous API request, We wrote the call to retrieve ALL books
* Now, Let us try to filter by genre
* The API allows us to add query parameters to a GET /books request to filter the results, as shown under "Params." Check out the Postman Library API v2 documentation for detailed documentation.
* So acc to Postman library API , There are some params listed like, genre, checkout, Search
* SO we can filter out by genre
* And the URL goes like
      * https://library-api.postmanlabs.com/books?genre=fiction
      * https://library-api.postmanlabs.com/books?genre=fiction&checkedOut=true etc
* These will give the books that falls under those conditions



