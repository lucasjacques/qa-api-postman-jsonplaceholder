# Documentation
For the requests I used [JSONPlaceholder](https://jsonplaceholder.typicode.com/)

## GETs
### GET - Retrieve Post by ID - Success
#### Description
This request validates the JSONPlaceholder endpoint responsible for returning Post information based on its ID. A GET request is made using a valid ID (100), with the goal of ensuring that the API is available, correctly processes the input, and returns the expected data. The focus of this test is to validate the basic functioning of the service in a success scenario.

#### Response Validations Performed
The response validation is done at three levels. First, the status code is checked to ensure the request was processed successfully (expected 200 OK). Next, the headers are validated, ensuring that the response Content-Type indicates JSON format. Finally, the response body is validated in two aspects: the presence of required fields (id, userId, title, and body) and data consistency, confirming that the returned ID matches exactly the ID sent in the request.

### GET - Retrieve Post by ID - Failed
#### Description
This request validates the JSONPlaceholder endpoint responsible for returning Post information based on its ID. A GET request is made using an invalid ID (101), with the goal of ensuring that the API is available, correctly processes the input, and returns the expected error. The focus of this test is to validate the basic functioning of the service in a failure scenario.

#### Response Validations Performed
The response validation is done at three levels. First, the status code is checked to ensure the request was processed correctly (expected 404 Not Found). Next, the headers are validated, ensuring that the response Content-Type indicates JSON format. Finally, the response body is validated to verify that it is empty.

## POSTs (via JSONPlaceholder)
### POST - Create a Post - Success
#### Description
This request validates the post creation endpoint of JSONPlaceholder through a POST call to /posts. In the test, a payload containing title, body, and userId is sent, simulating the creation of a new post. The goal is to verify whether the API correctly accepts the submitted data and returns a response consistent with the creation operation.

#### Response Validations Performed
The response validation is performed at three levels. The status code is checked to ensure the creation was successful (expected 201 Created). In the headers, the presence of the Location field is validated, ensuring that the response indicates the created resource (even considering that the API used is a mock and does not fully follow the REST standard). Finally, the response body is validated ensuring that the returned data matches what was sent in the request, confirming the integrity and consistency of the operation.

### POST - Create a Post with Minimal Params - Success
#### Description
This request validates the post creation endpoint of JSONPlaceholder through a POST call to /posts. In the test, a payload containing no parameters is sent, simulating the creation of a new post with the minimum required information. The goal is to verify whether the API correctly supports receiving no parameters and returns a response consistent with the creation operation.

#### Response Validations Performed
The response validation is performed at three levels. The status code is checked to ensure the creation was successful (expected 201 Created). In the headers, the presence of the Location field is validated, ensuring that the response indicates the created resource (even considering that the API used is a mock and does not fully follow the REST standard). Finally, the response body is validated ensuring that the returned data matches what was sent in the request, confirming the integrity and consistency of the operation.

## PUTs (via JSONPlaceholder)
### PUT - Update a Post - Success
#### Description
This request validates the resource update endpoint of JSONPlaceholder through a PUT call to /posts/{{postId}}, using a valid ID (observed by sampling that it works with values from 1 to 100). The goal is to simulate the update of an existing post, sending a payload with the field to be modified (in this case, "title"), ensuring that the API correctly processes the change of a previously existing resource.

#### Response Validations Performed
The response validation is performed at three levels. The status code is checked to ensure the update was successful (expected 200 OK). In the headers, the response Content-Type is validated to be in JSON format. Finally, the response body is validated ensuring that the returned data correctly reflects the values sent in the request, in this example only the id is returned, guaranteeing consistency and integrity of the operation.

### PUT - Update a Post with Invalid Id - Failed
#### Description
This request validates the API behavior when attempting to update a resource with an invalid ID (e.g., 101), which does not exist in the JSONPlaceholder database. The goal is to simulate a negative scenario, checking how the system behaves when faced with an attempt to update a non-existent resource, highlighting limitations of the mock API used.

#### Response Validations Performed
The response validation is also done at three levels. The status code is checked to ensure the API returns an error (expected 500 Internal Server Error). In the headers, the response Content-Type is validated to indicate HTML, reflecting an internal server error. Finally, the response body is validated in a generic way, ensuring it is not empty and contains signs of an error, without coupling to specific messages, keeping the test more robust and less dependent on internal implementation details.
