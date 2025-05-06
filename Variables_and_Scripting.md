# Variables in Postman
* Previously in the "Request Parameters" section of this course, we saw how using a variable saved us time and helped reduce redundant copy-paste of the request URL using the double curly brace syntax like this: {{variableName}}.
* Use of variables
    * Reuse values to keep your work DRY (Don’t Repeat Yourself)
    * Hide sensitive values like API keys from being shared publicly
## Variable Scopes
![var-scope-v10](https://github.com/user-attachments/assets/20d0a9f6-067b-4670-aee6-cd5bfca2d8d8)

* From broadest to narrowest, these scopes are global, collection, environment, data, and local.
* **If a variable with the same name is declared in two different scopes, the value stored in the variable with narrowest scope will be used. For example, if there is a global variable named username and a local variable named username, the local value will be used when the request runs.**

## Setting Variables Programitically
* Postman allows you to add **automation and dynamic** behaviors to your collections with scripting.
* Postman will automatically execute any provided scripts during two events in the request flow:
    * Immediately before a request is sent: **pre-request script** (Pre-request Script of Scripts tab).
    * mmediately after a response comes back: **post-response script** (Post-response of Scripts tab).

# The **pm** Object
* Postman has a helper object named pm that gives you access to data about your Postman environment, requests, responses, variables and testing utilities.
* https://learning.postman.com/docs/tests-and-scripts/write-scripts/postman-sandbox-api-reference/#the-pm-object
* The Postman **JavaScript API** functionality enables you to programmatically access and alter request and response data and variables using the **pm object.**
* You can access and manipulate variables at each scope in Postman using the pm API.
* Postman supports a variety of variable scopes. The pm object provides methods for accessing global, collection, and environment variables specifically, and pm.variables methods for accessing variables at different scopes and setting local variables.

```js
// collection var 'score' = 1
// environment var 'score' = 2

// first request run
console.log(pm.variables.get('score')); // outputs 2
console.log(pm.collectionVariables.get('score')); // outputs 1
console.log(pm.environment.get('score')); // outputs 2

// second request run
pm.variables.set('score', 3);// local var
console.log(pm.variables.get('score')); // outputs 3

// third request run
console.log(pm.variables.get('score')); // outputs 2

```

* You can also access variables defined in the individual scopes with pm.environment, pm.collectionVariables, and pm.globals. You can access vault secrets in your Postman Vault with pm.vault.
* Postman doesn't support using pm.variables to access and manipulate vault secrets.
* You can use variables in your scripts to:
    * Check if there is a Postman variable in the current scope:
        * pm.variables.has(variableName:String):function // Boolean
    * Get the value of the Postman variable with the specified name:
        * pm.variables.get(variableName:String):function
    * Append a string to the value of the Postman variable using the + operator:
        * String + pm.variables.get(variableName:String):function
    * Set a local variable with the specified name and value:
        * pm.variables.set(variableName:String, variableValue:*):function
    * Return the resolved value of a dynamic variable inside a script using the syntax {{$variableName}}
        * pm.variables.replaceIn(variableName:String):function:
        * ```js
          const stringWithVars = pm.variables.replaceIn("Hi, my name is {{$randomFirstName}}");
          console.log(stringWithVars);
          ```
    * Return an object containing all variables with their values in the current scope. Based on the order of precedence, this will contain variables from multiple scopes.
        * pm.variables.toObject():function // Object


and there are a lot more in https://learning.postman.com/docs/tests-and-scripts/write-scripts/postman-sandbox-api-reference/#the-pm-object



* Postman has a helper object named pm that gives you access to data about your Postman environment, requests, responses, variables and testing utilities.
* For example, you can access the JSON response body from an API with:
    * pm.response.json()
* You can also programmatically get collection variables like the value of baseUrl with:
    * pm.collectionVariables.get(“baseUrl”)
* In addition to getting variables, you can also set them
    * pm.collectionVariables.set("variableName", "variableValue")
    *  pm.collectionVariables.set(“myVar”, “foo”)


# TASK : First script

## Logging Data
```js
console.log("Hello world!")
```
## comments
```js
//HI
/*H
e
l
l
o */
```

## so we are writing POST-response Script
* So post-response script is nothing but the group of instructions that needs to be executed right after the response of  arequest.
* Soo Let's take the add a book request
* Go to Scripts tab and select post response tab
* Now Lets try to print the response in json format in the console after the completion of response
```js
console.log(pm.response.json())
```
* Now save and send the request
* After that, Go to console abd you will see the json() data being there
* so post-res script can be anything not just printing

# TASK - Grab the new book id
* automatically set a value for a variable via scripting.
* Saving a value as a variable allows you to use it in other requests.
* Using a Post-response script, let's grab the id of a newly added book and save it so we can use it in future requests.

# Setting and Getting Collection variables
* The pm object allows you to set and get collection variables.
* To set a collection variable, use the .set() method with two parameters: the variable name and the variable value
      * pm.collectionVariables.set("variableName", value)
* To get a collection variable use the .get() method and specify the name of the variable you want to retrieve:
      * pm.collectionVariables.get("variableName")
## Local variables
* We can also store local variables inside our scripts using JavaScript.
* There are two ways to define a variable in JavaScript: using the const or let keywords.
      * **const** is for variables that won't change value,
      * **let** allows you to reassign the value later.

* For now, We need to grab the new id of the book we added
## process
* Go to the add a book request
* Go to scripts and then select post response tab
* there write the code
```js
const new_book_id = pm.response.json().id 
pm.collectionVariables.set("new_book_id", new_book_id)
```
* then save and send
* Now check the collection's variables tab and you'll see the **new_book_id** there
* From Now on, You can use {{new_book_id}} in place of it.



