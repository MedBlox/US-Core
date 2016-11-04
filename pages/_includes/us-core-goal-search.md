

-------------------------

**Clients**

-  A client has connected to a server and fetched all of a patient's goals using `GET [base]/Goal?patient=[id]`.
- A client has connected to a server and fetched all of a patient's goals over a specified time period using `GET [base]/Goal?patient=[id]&date=[date]{&date=[date]}.`


**Servers**

- A server is capable of returning all of a patient's goals using `GET [base]/Goal?patient=[id]`.
- A server is capable of returning all of all of a patient's goals over a specified time period using `GET [base]/Goal?patient=[id]&date=[date]{&date=[date]}`.


- A server has ensured that every API request includes a valid Authorization token, supplied via:Authorization: Bearer {server-specific-token-here}
- A server has rejected any unauthorized requests by returning an HTTP 401 Unauthorized response code.

-----------

`GET /Goal?patient=[id]`

*Support:* Mandatory to support search by patient.

*Implementation Notes:* Search for all goals for a patient. Fetches a bundle of all Goal resources for the specified patient. [(how to search by reference)].



*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

GET https://fhir-open-api-dstu2.smarthealthit.org/Goal?patient=1137192

-----------

`GET /Goal?patient=[id]&date=[date]{&date=[date]}[edit]`

*Support:* Mandatory to support search by date.

*Implementation Notes:* Search for all goals for a patient within a time period. Fetches a bundle of all Goal resources for the specified patient with a specified time period. [(how to search by reference)] and [(how to search by date)].



*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

GET https://fhir-open-api-dstu2.smarthealthit.org/Goal?patient=1137192&date=ge2015-01-14

GET https://fhir-open-api-dstu2.smarthealthit.org/Goal?patient=1137192&date=ge2015-01-14&date=le2016-01-14


  [(how to search by reference)]: http://hl7.org/fhir/DSTU2/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/DSTU2/search.html#token
  [Composite Search Parameters]: http://hl7-fhir.github.io/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/DSTU2/search.html#date