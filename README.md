# PAWICAN (Preservation Actions for Wildlife: Integrated Conservation Application Network)
### Developed by: E-Core

HTTP POST is widely used in web applications for tasks like submitting forms, uploading files, and interacting with APIs. It allows for the transfer of complex data and is essential for various web-based services and applications.

## API DESCRIPTION

This API will contain endpoints that will insert, update, delete and extract data from the database. This API will be the foundation of API development.This API features  
-Create: This operation involves sending a POST request to add new data or resources to a server. It is commonly used for creating new records in a database, such as adding a new user or item.     
-View: "View" or "Read" operations are more commonly associated with HTTP GET requests, you can also use HTTP POST for retrieving data. In this case, you would send a POST request to a server, specifying what data you want to retrieve. This can include actions like fetching a user's profile, retrieving a list of products, or displaying specific records from a database.

## API Endpoints
1. /postTurtleData endpoint: is a component of an API or web service created to handle HTTP POST requests for adding or creating names. It normally anticipates the request body to contain data, which may be in the form of XML, JSON, or form data. This API is frequently used to add names to user profiles, databases, and other systems that need to store and manage names. When a POST request is made to this endpoint, the server processes the information and stores the supplied name as requested, making it available for further retrieval or use by the application.  
UPDATE: /postTurtleData endpoint is updated to "/postNestingData"

2. "/printTurtleData" endpoint: when accessed via a POST request in Postman, is used for custom data retrieval with the option to specify filtering criteria. This approach allows more complex data retrieval based on the data provided in the request body.    

## UPDATE on API Endpoints 
1. /postTurtleData endpoint is updated to "/postNestingData"
2. /printTurtleData endpoint is updated to "/printNestingData"
3. /updateTurtleData and /deleteTurtleData endpoint is added in the index.php

## Request Payload
### postNestingData Payload  

<pre>
{
    "location_found": "Ili Norte, San Juan, La Union",
    "transfer_location": "Project Norte, San Juan, La Union",
    "number_of_eggs": "101",
    "data_transplanted": "2023/11/13",
    "data_emergence": "",
    "time_emergence": "",
    "no_emergence": "",
    "collected_by": "",
    "hatched_number": "",
    "unhatched_number": "Carlos Tamayo"
}
</pre>

The sample payload specify what will be the content of the diffeent columns on the database. Once you send, these data are going to be upload to the database.

### printNestingData Payload
just enter the /printName endpoint and click send

## Response
### postNestingData Response Payload
If there are no errors on the code and payload, the response you can see from postman is (although there still errors needed to be addressed):  

<pre>
{  
         "status":"success","data":null  
}  
</pre>
You can double check by going to your database or by sending a request on printName if the data was uploaded.


### UPDATE ON RESULT: postNestingData Response Payload Result
<pre>
{
  "status": "success",
  "data": null,
  "warnings": [
    {
      "message": "Undefined property: stdClass::$date_transplanted",
      "file": "C:\\xampp\\htdocs\\pawican\\public\\index.php",
      "line": 18
    },
    {
      "message": "Undefined property: stdClass::$date_emergence",
      "file": "C:\\xampp\\htdocs\\pawican\\public\\index.php",
      "line": 19
    }
  ]
}
</pre>

### printNestingData Response Payload
If there are no errors on the code, the response you can see from postman is:  

<pre>{
    "status": "success",
    "data": [
        {
            "location_found": "Ili Norte, San Juan, La Union",
            "transfer_location": "Project Norte, San Juan, La Union",
            "number_of_eggs": "101",
            "date_transplanted": "0000-00-00",
            "date_emergence": "0000-00-00",
            "time_emergence": "00:00:00",
            "no_emergence": "0",
            "collected_by": "",
            "hatched_number": "0",
            "unhatched_number": "0"
        },
        {
            "location_found": "Urbiztondo, San Juan, La Union",
            "transfer_location": "Project Norte, San Juan, La Union",
            "number_of_eggs": "101",
            "date_transplanted": "0000-00-00",
            "date_emergence": "0000-00-00",
            "time_emergence": "00:00:00",
            "no_emergence": "0",
            "collected_by": "Carlos Tamayo",
            "hatched_number": "0",
            "unhatched_number": "0"
        },
        {
            "location_found": "Urbiztondo, San Juan, La Union",
            "transfer_location": "Project Curma, Ili Norte, San Juan, La Union",
            "number_of_eggs": "101",
            "date_transplanted": "0000-00-00",
            "date_emergence": "0000-00-00",
            "time_emergence": "00:00:00",
            "no_emergence": "0",
            "collected_by": "",
            "hatched_number": "0",
            "unhatched_number": "0"
        },
        {
            "location_found": "Ili Norte, San Juan, La Union",
            "transfer_location": "Project Norte, San Juan, La Union",
            "number_of_eggs": "101",
            "date_transplanted": "0000-00-00",
            "date_emergence": "0000-00-00",
            "time_emergence": "00:00:00",
            "no_emergence": "0",
            "collected_by": "",
            "hatched_number": "0",
            "unhatched_number": "0"
        },
        {
            "location_found": "Ili Norte, San Juan, La Union",
            "transfer_location": "Project Norte, San Juan, La Union",
            "number_of_eggs": "101",
            "date_transplanted": "0000-00-00",
            "date_emergence": "0000-00-00",
            "time_emergence": "00:00:00",
            "no_emergence": "0",
            "collected_by": "",
            "hatched_number": "0",
            "unhatched_number": "0"
        }
    ]
}
</pre>

### UPDATE ON RESULT: postNestingDataa Response Payload Result
<pre>
{
    "status": "success",
    "data": [
        {
            "location_found": "Ili Norte, San Juan, La Union",
            "transfer_location": "Project Norte, San Juan, La Union",
            "number_of_eggs": "101",
            "date_transplanted": "0000-00-00",
            "date_emergence": "0000-00-00",
            "time_emergence": "00:00:00",
            "hatched_number": "0",
            "unhatched_number": "0",
            "collected_by": ""
        },
        {
            "location_found": "Urbiztondo, San Juan, La Union",
            "transfer_location": "Project Norte, San Juan, La Union",
            "number_of_eggs": "101",
            "date_transplanted": "0000-00-00",
            "date_emergence": "0000-00-00",
            "time_emergence": "00:00:00",
            "hatched_number": "0",
            "unhatched_number": "0",
            "collected_by": "Carlos Tamayo"
        },
        {
            "location_found": "Urbiztondo, San Juan, La Union",
            "transfer_location": "Project Curma, Ili Norte, San Juan, La Union",
            "number_of_eggs": "101",
            "date_transplanted": "0000-00-00",
            "date_emergence": "0000-00-00",
            "time_emergence": "00:00:00",
            "hatched_number": "0",
            "unhatched_number": "0",
            "collected_by": ""
        },
        {
            "location_found": "Ili Norte, San Juan, La Union",
            "transfer_location": "Project Norte, San Juan, La Union",
            "number_of_eggs": "101",
            "date_transplanted": "0000-00-00",
            "date_emergence": "0000-00-00",
            "time_emergence": "00:00:00",
            "hatched_number": "0",
            "unhatched_number": "0",
            "collected_by": ""
        },
        {
            "location_found": "Ili Norte, San Juan, La Union",
            "transfer_location": "Project Norte, San Juan, La Union",
            "number_of_eggs": "101",
            "date_transplanted": "0000-00-00",
            "date_emergence": "0000-00-00",
            "time_emergence": "00:00:00",
            "hatched_number": "0",
            "unhatched_number": "0",
            "collected_by": ""
        },
        {
            "location_found": "Ili Norte, San Juan, La Union",
            "transfer_location": "Project Norte, San Juan, La Union",
            "number_of_eggs": "101",
            "date_transplanted": "0000-00-00",
            "date_emergence": "0000-00-00",
            "time_emergence": "00:00:00",
            "hatched_number": "0",
            "unhatched_number": "0",
            "collected_by": "Carlos Tamayo"
        }
    ]
}
</pre>

### UPDATE ON updateNestingData
1. updateNestingData cannot be tested properly, data to fetch is not matched with postNestingData and printNestingData

CHECK index.php
SEE COMPARISON:
postNestingData and printNestingData endpoints:
<pre>
    $location_found = $data->location_found;
    $transfer_location = $data->transfer_location;
    $number_of_eggs = $data->number_of_eggs;
    $date_transplanted = $data->date_transplanted;
    $date_emergence = $data->date_emergence;
    $time_emergence = $data->time_emergence;
    $hatched_number = $data->hatched_number;
    $unhatched_number = $data->unhatched_number;
    $collected_by = $data->collected_by;
</pre>

updateNestingData endpoint
<pre>
    $location_found = $data->location_found;
    $transfer_location = $data->transfer_location;
    $number_of_eggs = $data->number_of_eggs;
    $date_transplanted = $data->date_transplanted;
    $date_emergence = $data->date_emergence;
    $time_emergence = $data->time_emergence;
    $collected_by = $data->collected_by;
    $hatched_number = $data->hatched_number;
    $unhatched_number = $data->unhatched_number;
</pre>

### UPDATE ON deleteNestingData
Payload:
<pre>
{
    "id":1
}
</pre>
Result:
<pre>
{
    "status": "success",
    "data": null
}
</pre>

## Usage
(Note: You need to clone first the repository using this command in the CMD or terminal "git clone https://github.com/ragacutan/pawican.git" )  

Step 1: Create a New Request  
    Run SQLYOG and XAMPP, import demo.sql to your database.  
    Open Postman.  
    Click the "New" button.  
    Select "Request" to create a new request.  

Step 2: Set Request Type and URL  
    Choose the appropriate HTTP method for this API is (POST) based on the operation you want to perform.  
    Enter the API URL, including the specific endpoint you intend to access (e.g., http://localhost/pawican/public/postName).  

Step 3: Add Headers (if required)  
    If your API request requires specific headers, you can add them in this step.  

Step 4: Add Request Payload
    If you're using a POST or PUT request to add or update data, proceed to the "Body" tab.  
    Select "raw" as the data format, usually using JSON.  
    Enter the JSON payload in the request body.  

Step 5: Send the Request  
    Click the "Send" button to execute the API request.    

Step 6: View the Response  
    Postman will display the API's response in the lower part of the window.  
    You can review the HTTP status code, response headers, and the response body, which typically contains the data returned by the API.  

Step 7: Test Other Endpoints  
    You can repeat the above steps with different endpoints, such as printName, updateName, and deleteName, and customize the payloads as needed for testing various API functionalities.  

## Licences
No License. For Educational Purposes Only  

## Contributors
 

## Contact
For more information you can contact the following developers:

Name: Dennis Loren P. Tacubanza  
Email: dennisloren.tacubanza@student.dmmmsu.edu.ph  
Contact:   

Name: Ram Adrian N. Gacutan  
Email: ramadrian.gacutan@student.dmmmsu.edu.ph  
Contact: 09686769701

Name: Mc Jefferson Molina  
Email: mcjefferson.molina@student.dmmmsu.edu.ph  
Contact:

Quality Assurance:
Name: Rizalyn B. Florague  
Email: rizalyn.florague@student.dmmmsu.edu.ph  
Contact: 09155124048