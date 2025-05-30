# Postman API Fundamentals Student Expert certification

## API Application Programming Interfaces
* An API (Application Programming Interface) is a set of rules, protocols, and tools that allow different software applications to communicate with each other.
* an API acts as a bridge between two applications
* they allow for sharing of resources and services across applications, organizations, and devices.
* Example : Twilio API, It helps us send messages through whatsapp.

### Why use API?
* APIs simplify complex processes. Instead of building everything from scratch, developers can use existing APIs to add functionality to their applications.
  * ex: using a Weather API instead of launching your weather balloons
* APIs allow different software systems to work together.
  * For example, a weather app can use an API to get weather data from a weather service.
* By using APIs, developers can save time and resources, focusing on building their application rather than reinventing the wheel.
* Reusing functionalities.
* APIs can be products themselves
  * ex: Software as a Service (SaaS) products like Stripe's payment APIs or Twilio's text messaging and email APIs

### Who works with APIs?
*APIs are not just for developers. According to Postman's latest State of the API Report, almost half of the survey respondents identified as holding non-developer roles, such as management, solutions architects, business and data analysts, educators and researchers. All these roles benefit from the standardized data access provided by APIs*.

![4DoRYQk7xxkmEe](https://github.com/user-attachments/assets/e6c08bbc-73da-4303-acf7-beb0f079d480)

  
![3UsVrbnGRCyNZY](https://github.com/user-attachments/assets/1259c3d1-761a-48af-bb74-2a1184ef6824)

### APIs - A Digital Restaurant

* You can think of APIs as being like a waiter at a restaurant, serving as a go-between for the customer and the kitchen. 

<img width="557" alt="ALZWDyawVmyZ8W" src="https://github.com/user-attachments/assets/d103d84e-ebfe-4103-a794-f6bd1987be9d" />

* A customer who wants soup **doesn't go** into the kitchen to cook. They don't even have to know **how to make soup!** They only have to know how to ask the waiter for soup, expecting the ***waiter*** to bring back soup.
* APIs work the same way, but there are different names for the players involved. Instead of soup, the *requester* might ask for data or execution of a service.

| Networking Term | Description | Restaurant Analogy |
|----------------------|---------------------------------------------------------|-------------------------|
| Client | The requester. Ex: browser, web app, mobile app | Customer | 
| API | Simplified interface for interacting with the backend | Waiter | 
| Server | The backend where the processing happens | Kitchen |

### Types of APIs
------------------------------------------------------------------------------------------
### Hardware APIs 
*Hardware APIs allow software applications to communicate with hardware components like cameras, microphones, sensors, or GPUs without the developer having to deal with the internal complexity of the hardware.*
* **How They Work** : When a developer writes code to access hardware features, they don't write code that directly controls the hardware.
 * Instead, they use APIs provided by the operating system.
 * The operating system acts as a middle layer between the software and hardware.
* **Example 📱** : Imagine you're building a mobile app that needs to take pictures.
 * If the code includes the below code, the **Camera** is the API, your code calls this API.
 * OS receives that request and communicates with the Camera Hardware driver.
 * And the same Camera API gives you the captured image as a response
```python
#code calls Camera API open() method
#OS receives request and communicate with the real Camera H/W and opens the camera as response
Camera.open();

#code calls API captureimage()
#OS talks with real cam
#captures image
Camera.captureImage();
```
**Examples**

| Hardware	API | Example |	Platform |
| --------------- | ------------------------ | -------------------------------- |
| Camera |	CameraX |	Android |
| Microphone |	MediaRecorder |	Android |
| GPS |	LocationManager |	Android |
| Bluetooth |	CoreBluetooth |	iOS |
| Graphics Card (GPU)	| DirectX	| Windows |

------------------------------------------------------------------------------------------------------------------

### Software Library APIs 
*A Software Library API allows developers to reuse code written by someone else without writing it from scratch.It is simply a set of functions, methods, or classes that perform specific tasks like file handling, encryption, or data manipulation.*
* **How They Work** : Developers import the library into their project.
 * They call the library's functions through its API.
 * The library performs the task and returns the result.
* **Example 📱** : Imagine you want to hash passwords in your Node.js application.
 * Without a library:
```javascript
   function hashPassword(password) {
  // Complex hashing logic
}
```
 * with library bcrypt:
```javascript
const bcrypt = require('bcrypt');
bcrypt.hash(password, 10);
```

**Examples**

| Library |	Purpose |	Language |
|------------------------|-----------------------|---------------------|
| NumPy |	Data | Manipulation |	Python |
| Lodash	Utility | Functions	| JavaScript |
| TensorFlow |	Machine | Learning |	Python |
| Axios |	HTTP | Requests |	JavaScript |
| Hibernate |	Database | ORM |	Java |

-------------------------------------------------------------------------------------------
### Web APIs 🌐💻
*Web APIs allow different applications to communicate over the internet or network.
These APIs are hosted on a web server and provide services to other applications via HTTP or HTTPS requests.*
* **How They Work** : Your app sends a request to the API URL.
 * The API processes the request.
 * It fetches the required data from the server.
 * It sends back the response in JSON or XML format.
* **Example 📱** : Imagine you want to hash passwords in your Node.js application.
 * Fetching weather data from an API: Request:
```javascript
   fetch('https://api.openweathermap.org/data/2.5/weather?q=Delhi&appid=API_KEY')
  .then(response => response.json())
  .then(data => console.log(data));

```
 * Response:
```json
{
  "city": "Delhi",
  "temperature": 28,
  "description": "clear sky"
}

```
----------------------------------------------------------------------------------------------------------------
* Multiple API types may be used to achieve a task. For example, uploading a photo to Instagram makes use of various APIs:
  * Hardware API for the app to talk to your camera
  * Software library API for the image to be processed with filters
  * Web API for sending your image to Instagram's servers so your friends can like it!
* There is more than one way to build and consume APIs. Some architecture types you may come across are:
  * REST (Representational State Transfer)
  * GraphQL
  * WebSockets
  * webhooks
  * SOAP (Simple Object Access Protocol)
  * gRPC (Google Remote Procedure Call)
  * MQTT (MQ Telemetry Transport)
### REST APIs
Some traits of REST APIs include not storing session state between requests, the ability to cache, and the ability to send and receive various data types.

## ACCESS
### Public API (aka Open API)
* Consumed by anyone who discovers the API
### Private API
* Consumed only within an organization and not made public.
### Partner APIs
* Consumed between one or more organizations that have an established relationship

