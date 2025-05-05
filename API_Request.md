# First API request
## A digital Librarian

* This REST API allows you to CRUD (Create, Read, Update, Delete) books in a public library database.
* You will use Postman to interact with this API and manage books.

### Open Postman for web
* Postman can be Used as a desktop app or web browser.
* For Now les go with browser
  * Navigate to https://www.postman.com/
  * Sign up / Sign in
## Create a workspace
* To start making Postman requests, you need to be inside a workspace
  * Workspaces dropdown > Create Workspace
  * <img width="482" alt="instructor_26fp2261340y1ukokimvca8su_public_1649272400_workspace-new 1649272400639" src="https://github.com/user-attachments/assets/7bab142e-a037-4611-a650-40bd94c4eb6c" />
  * Select Blank Workspace as Template and Name your workspace
  * <img width="1422" alt="8DfWSfTvWiejKX" src="https://github.com/user-attachments/assets/13998de1-37be-4a6b-bcd9-1ba20529f1f0" />
  * Set the visibility to as you want. Then click "Create Workspace."
  * <img width="1265" alt="instructor_7k52zal2mzkzozhgzyoosmk2v_public_1734085130_Screenshot+2024-12-13+at+3 48 08 PM 1734085130035" src="https://github.com/user-attachments/assets/9bc81f88-94cc-4851-8f3e-87ef6a12a590" />

  # Well well THATS HOW YOU CREATE A WORKSPACE

## Create a Collection
### wait- what is a collection??
* Collections are places to organize your API requests in Postman.
* They serve as executable documentation of API endpoints.
  * **WHAT IS AN API ENDPOINT?** - An API endpoint is a specific URL (Uniform Resource Locator) or URI (Uniform Resource Identifier) where an API (Application Programming Interface) can be accessed to perform a particular function or retrieve specific data.
* A Collection in Postman is a group of HTTP requests that can be organized, saved, and executed together.
* It helps developers group related API endpoints for better organization and testing.


### steps to create a collection
* In ur respective workspace, Click "NEW" or "+".
* Click Blank collection and Name it.. that's It.
* I named it "library api vw"
* Here I put the related apis.
 
## GET BOOKS from library API
### Ok!! Now we r gonna make our first request
**Task** = To fetch all books
* Click on Add a request
* You'll see types of requests on the left as a dropdown.. make sure to select **GET**
* And Paste the URL https://library-api.postmanlabs.com/books
* Save it and send it
* You will see the JSON( JavaScript Object Notation) format response below that has all books details
<img width="380" alt="instructor_26fp2261340y1ukokimvca8su_public_1649281938_add+request 1649281938816" src="https://github.com/user-attachments/assets/18990211-a46c-40c8-b874-0c6b2130e675" />

<img width="676" alt="instructor_26fp2261340y1ukokimvca8su_public_1649282885_get+books 1649282885313" src="https://github.com/user-attachments/assets/ad0f7283-ba3f-4c79-9b89-8def787fac9c" />

<img width="868" alt="instructor_26fp2261340y1ukokimvca8su_public_1649283511_get+books+response 1649283511929" src="https://github.com/user-attachments/assets/cf47afdd-7284-4400-a429-3f0feadc9aec" />

## Popular Request Methods
| **Method name**	| **Operation** |
|-----------------|------------------|
| GET	| Retrieve data (Read) |
| POST |	Send data (Create) |
| PUT/PATCH |	Update data (Update) |
|      |    * PUT usually replaces an entire resource, whereas PATCH usually is for partial updates |
| DELETE |	Delete data (Delete) |

