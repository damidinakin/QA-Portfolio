# POST Request Testing

## Endpoint

POST /users

## Objective

Verify that a new user can be created successfully.

## Test Case ID

API-002

## Preconditions

API endpoint is available.

## Request Body

```json
{
  "name": "Damilola",
  "username": "QAEngineer",
  "email": "damilola@test.com"
}
```

## Steps

1. Launch Postman.
2. Send a POST request to /users.
3. Enter the request body.
4. Click Send.
5. Observe the response.

## Expected Result

* Status Code = 201 Created
* New user ID is returned.
* Response contains submitted data.

## Actual Result

* Status Code = 201 Created
* ID 11 was returned.
* Response contained all submitted fields.

## Status

Pass

## Assertions

### Status Code Validation

```javascript
pm.test("Status code is 201", function () {
    pm.response.to.have.status(201);
});
```

### ID Validation

```javascript
pm.test("ID is returned", function () {
    let jsonData = pm.response.json();
    pm.expect(jsonData.id).to.exist;
});
```
