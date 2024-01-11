# PAWICAN (Preservation Actions for Wildlife: Integrated Conservation Application Network)
### Developed by: E-Core

HTTP POST is widely used in web applications for tasks like submitting forms, uploading files, and interacting with APIs. It allows for the transfer of complex data and is essential for various web-based services and applications.

## API DESCRIPTION

This API will contain endpoints that will insert, update, delete and extract data from the database. This API will be the foundation of API development.This API features  
-Create: This operation involves sending a POST request to add new data or resources to a server. It is commonly used for creating new records in a database, such as adding a new user or item.     
-View: "View" or "Read" operations are more commonly associated with HTTP GET requests, you can also use HTTP POST for retrieving data. In this case, you would send a POST request to a server, specifying what data you want to retrieve. This can include actions like fetching a user's profile, retrieving a list of products, or displaying specific records from a database.

## API Endpoints
1. /postNestingData
2. /printNestingData
3. /updateNestingData
4. /deleteNestingData
5. /postStrandingReport
6. /printStrandingReport
7. /updateStrandingReport
8. /deleteStrandingReport
9. /searchStranding

## DESCRIPTION of API Endpoints 
1. /postNestingData: 
    This endpoint facilitates users in submitting crucial nesting data, including intricate details such as the location where the nesting was found, the location where the eggs were transferred, the specific number of eggs, and timestamps indicating dates and times of the activities. Upon successful submission through this endpoint, users receive a confirmation status, signifying that the data has been securely uploaded to the database.
    
2. /printNestingData
    This endpoint is for retrieving previously captured nesting data entries. Without requiring any specific payload, this endpoint presents a detailed list of recorded nesting data, encompassing information about locations, egg counts, date-time stamps, and collector credentials.

3. /updateNestingData
    This endpoint allows users to specify the unique Entry ID along with the modified details, such as revised locations, egg counts, or collector information. Upon successful execution, the system conveys a confirmation status, assuring stakeholders that the respective data has been appropriately updated.

4. /deleteNestingData
    This endpoint empowers users to remove specific nesting data entries by providing the associated Entry ID. This functionality ensures data integrity and relevance, allowing conservationists to maintain an accurate database free from redundant or outdated information.
    
5. /postStrandingReport
    The API also incorporates functionalities dedicated to stranding reports through the /postStrandingReport endpoint. This feature enables users to document stranding incidents by capturing essential data elements like observer details, species involved, exact stranding location, condition assessments, disposition outcomes, and associated tag numbers. Upon successful submission, users are notified of the recorded stranding report, furthering efforts to understand and mitigate stranding events.  

6. /printStrandingReport
    This endpoint serves as a tool for accessing previously logged stranding reports, offering a comprehensive list replete with observer credentials, species details, location specifics, condition evaluations, and disposition outcomes.

7. /updateStrandingReport
    For scenarios necessitating modifications to recorded stranding reports, this endpoint provides a structured mechanism. By specifying the unique Report ID and incorporating updated information like observer details, species, location, condition assessments, disposition outcomes, and associated tag numbers, users can ensure data accuracy and relevance. Successful execution of this endpoint elicits a confirmation status, affirming stakeholders of the applied modifications.

8. /deleteStrandingReport
    This endpoint serves as a critical tool within the API system, offering users the capability to remove specific stranding reports with precision. By providing the unique Report ID associated with the record in question, stakeholders can ensure the elimination of outdated, redundant, or erroneous data entries. This targeted deletion mechanism enhances data integrity and relevance, enabling conservationists and researchers to maintain a streamlined and accurate database. 

9. /searchStranding
    This endpoint enhances the system's search capabilities, allowing users to retrieve specific stranding reports based on the provided Report ID. This targeted search functionality facilitates efficient data retrieval, providing stakeholders with detailed insights into individual stranding incidents. By supplying the unique identifier, users can access comprehensive information encompassing observer details, species involved, location specifics, condition evaluations, disposition outcomes, and associated tag numbers.

## Request Payload and Response
1. /postNestingData
    Payload:
        <pre>
        {
            "location_found": "Urbiztondo, San Juan, La Union",
            "transfer_location": "Project Norte, San Juan, La Union",
            "number_of_eggs": "101",
            "date_transplanted": "11:39:04",
            "date_emergence": "11:39:04",
            "time_emergence": "11:39:04",
            "no_emergence": "11:39:04",
            "collected_by": "Carlos Tamayo"
            "hatched_number": "90",
            "unhatched_number": "20",
        }
        </pre>
        The sample payload specify what will be the content of the diffeent columns on the database. Once you send, these data are going to be upload to the database.
    
    Result:
        <pre>
        {
            "status": "success",
            "data": null
        }
        </pre>
        
2. /printNestingData
    Payload:

    Result:
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
                }
            ]
        }
        </pre> 

3. /updateNestingData
    Payload:
        <pre> 
        {
            "id": "1",
            "location_found": "Ili Norte, San Juan, La Union",
            "transfer_location": "Project Norte, San Juan, La Union",
            "number_of_eggs": "101",
            "date_transplanted": "2023/11/13",
            "date_emergence": "2023/12/30",
            "time_emergence": "11:39:04",
            "hatched_number": "90",
            "unhatched_number": "20",
            "collected_by": "Carlos Tamayo"
        }
        </pre>

    Result:
        <pre>
        {
            "status": "success",
            "data": null
        }
        </pre>

4. /deleteNestingData
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
     
5. /postStrandingReport
    Payload:
        <pre>
        { 
            "observer_name": "Dennis Loren Tacubanza", 
            "stranding_datetime": "2023-11-19 15:30:00", 
            "species": "Green Sea Turtle", 
            "sex": "Female", 
            "turtle_location": "Ili Sur, San Juan, La Union", 
            "turtle_condition": "Alive", 
            "disposition": "Alive, released", 
            "disposition_location": "Ili Norte, San Juan, La Union", 
            "tag_numbers": "101", 
            "other_information": "Nothing follows" 
        } 
        </pre>

    Result:
        <pre>
        {
            "status": "success",
            "data": null
        }
        </pre>

6. /printStrandingReport
    Payload:

    Result:
        <pre>
        {
            "status": "success",
            "data": [
                {
                    "id": 1,
                    "observer_name": "Carlos L. Tamayo",
                    "stranding_datetime": "2023-11-19 15:30:00",
                    "species": "Green Sea Turtle",
                    "sex": "Female",
                    "turtle_location": "",
                    "turtle_condition": "Alive",
                    "disposition": "Alive, released",
                    "disposition_location": "Ili Norte, San Juan, La Union",
                    "tag_numbers": 101,
                    "other_information": "Nothing follows"
                },
                {
                    "id": 2,
                    "observer_name": "Carlos Tamayo",
                    "stranding_datetime": "2023-11-19 15:30:00",
                    "species": "Green Sea Turtle",
                    "sex": "Female",
                    "turtle_location": "Ili Sur, San Juan, La Union",
                    "turtle_condition": "Alive",
                    "disposition": "Alive, released",
                    "disposition_location": "Ili Norte, San Juan, La Union",
                    "tag_numbers": 101,
                    "other_information": "Nothing follows"
                },
                {
                    "id": 3,
                    "observer_name": "Carlos L. Tamayo",
                    "stranding_datetime": "2023-11-19 15:30:00",
                    "species": "Green Sea Turtle",
                    "sex": "Female",
                    "turtle_location": "Ili Sur, San Juan, La Union",
                    "turtle_condition": "Alive",
                    "disposition": "Alive, released",
                    "disposition_location": "Ili Norte, San Juan, La Union",
                    "tag_numbers": 101,
                    "other_information": "Nothing follows"
                }
            ]
        }
        </pre>

7. /updateStrandingReport
    Payload:
        <pre>
        { 
            "id": "3",
            "observer_name": "Erin Cruz", 
            "stranding_datetime": "2023-11-19 15:30:00", 
            "species": "Green Sea Turtle", 
            "sex": "Female", 
            "turtle_location": "Ili Sur, San Juan, La Union", 
            "turtle_condition": "Alive", 
            "disposition": "Alive, released", 
            "disposition_location": "Ili Norte, San Juan, La Union", 
            "tag_numbers": "101", 
            "other_information": "Nothing follows" 
        } 
        </pre>

    Result:
        <pre>
        {
            "status": "success",
            "data": null
        }
        </pre>

8. /deleteStrandingReport
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

9. /searchStranding
    Payload:
        <pre>
            {
            "id":3
            }
        </pre>

    Result:
        <pre>
        {
            "status": "success",
            "data": [
                {
                    "id": 3,
                    "observer_name": "Erin Cruz",
                    "stranding_datetime": "2023-11-19 15:30:00",
                    "species": "Green Sea Turtle",
                    "sex": "Female",
                    "turtle_location": "Ili Sur, San Juan, La Union",
                    "turtle_condition": "Alive",
                    "disposition": "Alive, released",
                    "disposition_location": "Ili Norte, San Juan, La Union",
                    "tag_numbers": 101,
                    "other_information": "Nothing follows"
                }
            ]
        }
        </pre>


## ADDITIONAL ENDPOINTS
## ADDITIONAL ENDPOINTS
## ADDITIONAL ENDPOINTS
/postHatcheryData
/printHatcheryData
/searchHatchery
### Endpoints:

1. `/postHatcheryData`
2. `/printHatcheryData`
3. `/searchHatchery`

---

<PRE>
#### 1. `/postHatcheryData`

**Payload:**
{
    "location_hatchery": "Location A",
    "month": "January",
    "year": 2024,
    "date_transplanted": "2024-01-10",
    "nest_code": "N001",
    "no_eggs": 100,
    "date_emergence": "2024-02-01",
    "emerged_hatchlings": 90,
    "hatchlings_released": 85,
    "remarks": "Some remarks here"
}

**Response (Success):**
{
    "status": "success",
    "message": "Data successfully saved"
}

**Response (Error):**
{
    "status": "error",
    "message": "Error message details"
}

#### 2. `/printHatcheryData`

**Payload:** *(This endpoint does not require a payload as it retrieves all hatchery data from the database.)*

**Response (Success with Data):**
{
    "status": "success",
    "data": [
        {
            "hatchery_id": 1,
            "hatchery_location": "Location A",
            "month": "January",
            "year": 2024,
            "date_transplanted": "2024-01-10",
            "nest_code": "N001",
            "eggs_transplanted": 100,
            "emergence_date": "2024-02-01",
            "hatchlings_emerged": 90,
            "hatchlings_released": 85,
            "remarks": "Some remarks here"
        },
        // ... other records
    ]
}

**Response (Success with No Data):**
{
    "status": "success",
    "data": null
}

**Response (Error):**
{
    "status": "error",
    "message": "Error message details"
}

#### 3. `/searchHatchery`

**Payload:**
{
    "hatchery_id": 1
}

**Response (Success with Data):**
{
    "status": "success",
    "data": [
        {
            "hatchery_id": 1,
            "hatchery_location": "Location A",
            "month": "January",
            "year": 2024,
            "date_transplanted": "2024-01-10",
            "nest_code": "N001",
            "eggs_transplanted": 100,
            "emergence_date": "2024-02-01",
            "hatchlings_emerged": 90,
            "hatchlings_released": 85,
            "remarks": "Some remarks here"
        }
    ]
}

**Response (Success with No Data):**
{
    "status": "success",
    "data": null
}

**Response (Error):**
{
    "status": "error",
    "message": "Error message details"
}
</PRE>

### aDDITIONAL Endpoints:

1. `/government/printAccount`
2. `/government/updateAccount`
3. `/government/updateProfile`

### 1. Endpoint: `/government/printAccount`

**Payload:**
None. This endpoint fetches data based on the session username.

**Response:**
<PRE>
{
    "status": "success",
    "data": [
        {
            "government_id": "123",
            "full_name": "John Doe",
            ...
            "password": "hashed_password"
        },
        ...
    ]
}
</PRE>

### 2. Endpoint: `/government/updateAccount`

**Payload:**
<PRE>
{
    "new_username": "newGovUsername",
    "new_password": "newGovPassword"
}
</PRE>

**Response:**
<PRE>
{
    "status": "success",
    "message": "Government credentials updated successfully"
}
</PRE>

or

<PRE>
{
    "status": "error",
    "message": "Government account not found"
}
</PRE>

### 3. Endpoint: `/government/updateProfile`

**Payload:**
<PRE>
{
    "full_name": "Updated Full Name",
    "sex": "Updated Sex",
    "birthdate": "Updated Birthdate",
    "civil_status": "Updated Civil Status",
    "language": "Updated Language",
    "present_address": "Updated Present Address",
    "permanent_address": "Updated Permanent Address",
    "phone_number": "Updated Phone Number",
    "email": "Updated Email",
    "agency": "Updated Agency",
    "position": "Updated Position",
    "work_address": "Updated Work Address"
}
</PRE>

**Response:**
<PRE>
{
    "status": "success",
    "message": "Government profile updated successfully"
}
</PRE>

or

<PRE>
{
    "status": "error",
    "message": "Government account not found"
}
</PRE>

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


## QA Section
## QA Section
## QA Section
## QA Section
### ENDPOINT TESTING RESULT: 
/postNestingData - NO ISSUES (improve readablity, align format to db)
/printNestingData - NO ISSUES 
/updateNestingData - NO ISSUES (improve readablity, align format to db)
/deleteNestingData - NO ISSUES

/postStrandingReport - NO ISSUES
/printStrandingReport - NO ISSUES
/updateStrandingReport - NO ISSUES
/deleteStrandingReport - NO ISSUES
/searchStrandingReport - NO ISSUES

## NEED TO UPDATE
## NEED TO UPDATE
## NEED TO UPDATE
## NEED TO UPDATE
NONE


## Licences
No License. For Educational Purposes Only  

## Contributors
QA Team Representative
Name: Rizalyn B. Florague  
Email: rizalyn.florague@student.dmmmsu.edu.ph  
Contact: 09155124048 

## Contact
For more information you can contact the following developers:

Name: Dennis Loren P. Tacubanza  
Email: dennisloren.tacubanza@student.dmmmsu.edu.ph  
Contact:   

Name: Ram Adrian N. Gacutan  
Email: ramadrian.gacutan@student.dmmmsu.edu.ph  
Contact: 09686769701

Name: Mc Jefferson Molina  
Email: mmolina18062@student.dmmmsu.edu.ph  
Contact: 09695797988