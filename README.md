# Deloitte Customer API

## Preface:

The Deloitte Customer API is a REST based service built in Mulesoft that will cater the needs of an organization for a customer portal.
It can be accessed as a mobile application with a provision to fetch customer details and update them. This enables the customer representatives quick and easy access to customer data on their hand-held devices.

## Resource/Methods:

The Deloitte Customer API can be accessed through a base path /api/* followed by a resource 'customers'. It supports the following operations.
 -GET (Fetch customer data)
 -POST (Create Customer data)
 -PUT (Update Customer data)
 -DELETE (Delete Customer data)
 
## Parameters List:

The ID of a customer is used as a key attribute that uniquely identifies a customer. This parameter is used with some of the operations.
 
GET: Fetch all the customers data available in the HR system. There are just 2 customers setup now for this exercise.
 
GET: customers/{ID} - Fetch the details of a specific customer that matches the ID passed as a uri param. Returns an error for an unmatched ID.

POST: Add a new customer to the HR system. The HR system in the backend is for Australian employees only. So the API has a validation on the country field passed as one of the input fields in the JSON request. It returns an error when the country is anything but Australia. The API can be extended to route requests through to different HR systems for different countries in the future.

PUT: customers/{ID} - Updates the details of a specific customer that matches the ID passed as a uri param. Does not include any country or ID check validation now for this exercise.

DELETE: customers/{ID} - Deletes the details of a specific customer that matches the ID passed as a uri param. Does not include any country or ID check validation now for this exercise.

## Sample Request:

GET url: http://localhost:8081/api/customers

GET url with ID: http://localhost:8081/api/customers/2

POST url: http://localhost:8081/api/customers

PUT url: http://localhost:8081/api/customers/2

DELETE url: http://localhost:8081/api/customers/2


## Customer data used for the exercise:

 {
    "ID": 1,
    "firstName": "Sam",
    "lastName": "Billings",
    "address": {
      "unitNo": 8,
      "streetName": "The Boulevarde",
      "suburb": "Strathfield",
      "postcode": 2135,
      "state": "NSW",
      "country": "Australia"
    }
  },
  {
    "ID": 2,
    "firstName": "Dave",
    "lastName": "Warner",
    "address": {
      "unitNo": 10,
      "streetName": "Warrimoo Street",
      "suburb": "Bracken Ridge",
      "postcode": 4017,
      "state": "QLD",
      "country": "Australia"
    }
  }


## Sample POST request:

{
    "ID": 2,
    "firstName": "Dave",
    "lastName": "Warner",
    "address": {
      "unitNo": 10,
      "streetName": "Warrimoo Street",
      "suburb": "Bracken Ridge",
      "postcode": 4017,
      "state": "QLD",
      "country": "Australia"
    }
  }
  
## Sample POST request for a Non-Australian Customer:

{
    "ID": 3,
    "firstName": "Joe",
    "lastName": "Root",
    "address": {
      "unitNo": 15,
      "streetName": "George Street",
      "suburb": "Clayfield",
      "postcode": 3000,
      "state": "Wales",
      "country": "England"
    }
  }


## Sample  PUT request:

{
    "ID": 2,
    "firstName": "Dave",
    "lastName": "Warner",
    "address": {
      "unitNo": 10,
      "streetName": "Warrimoo Street",
      "suburb": "Bracken Ridge",
      "postcode": 4017,
      "state": "QLD",
      "country": "Australia"
    }
  }


