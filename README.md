# Cybersecurity News API Testing

A practical API testing project built with Postman to test the News API and demonstrate core API testing concepts.

## Project Overview

This project focuses on testing the News API using Postman.

The project includes successful requests, pagination, authentication testing, query parameters, JSON response analysis, and negative test cases.

The goal is to demonstrate practical understanding of REST APIs and API testing using Postman.

## API Used

**News API**

Main endpoint:

`https://newsapi.org/v2/everything`

The API is used to search and retrieve news articles based on different query parameters.

## Authentication

The API requires an API Key for authentication.

The API Key is stored as a Postman Collection Variable:

`{{news_api_key}}`

The real API Key is not included in this repository for security reasons.

## Requests

### 01 - Search Cybersecurity

Searches for cybersecurity-related news.

Parameters:

- `q = cybersecurity`
- `language = en`
- `pageSize = 5`
- `sortBy = publishedAt`

Expected result: `200 OK`

### 02 - Search Ransomware

Searches for ransomware-related news.

Parameters:

- `q = ransomware`
- `language = en`
- `pageSize = 5`
- `sortBy = publishedAt`

Expected result: `200 OK`

### 03 - Ransomware - Page 2

Tests pagination by requesting the second page of ransomware results.

Additional parameter:

- `page = 2`

Expected result: `200 OK`

### 04 - Invalid API Key

Tests authentication failure by sending an invalid API Key.

Expected result:

`401 Unauthorized`

Example error:

```json
{
  "status": "error",
  "code": "apiKeyInvalid"
}
````

### 05 - Missing Search Query

Tests how the API handles a request when the required `q` parameter is missing.

Expected result:

`400 Bad Request`

## Concepts Demonstrated

* REST API fundamentals
* HTTP GET requests
* Query Parameters
* API Key Authentication
* Postman Variables
* Collections
* JSON Objects
* JSON Arrays
* Reading nested JSON data
* Pagination
* HTTP Status Codes
* Positive Testing
* Negative Testing
* Request / Response validation

## Status Codes Tested

| Status Code | Meaning      | Test Case               |
| ----------- | ------------ | ----------------------- |
| 200         | OK           | Successful API requests |
| 400         | Bad Request  | Missing required query  |
| 401         | Unauthorized | Invalid API Key         |

## JSON Response Analysis

The API returns news articles inside the `articles` array.

Examples:

```text
articles[0].title
articles[0].author
articles[0].publishedAt
articles[0].url
articles[0].source.name
```

This demonstrates how to access values from nested JSON objects and arrays.

## Postman Variables

The API Key is stored as a Collection Variable instead of being hard-coded into every request.

```text
{{news_api_key}}
```

This improves maintainability and prevents the real API Key from being exposed in the project files.

## How to Run

1. Import the Postman Collection into Postman.
2. Create a Collection Variable named `news_api_key`.
3. Add your own News API Key as the variable value.
4. Run the requests individually or as a Collection.
5. Check the returned Status Code and JSON Response.

## Project Structure

```text
cybersecurity-news-api-testing/
│
├── README.md
│
└── postman/
    └── cybersecurity-news-api-testing.postman_collection.json
```

## Testing Summary

The project demonstrates both successful and unsuccessful API interactions.

Successful requests were tested using different search queries and pagination parameters, while negative test cases were used to validate API behavior when authentication or required request parameters were invalid.

## Tools

* Postman
* News API
* REST API
* JSON
* GitHub

