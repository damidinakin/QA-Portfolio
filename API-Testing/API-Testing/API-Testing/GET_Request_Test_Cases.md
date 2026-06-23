# GET Request Testing

## Endpoint

GET /users

## Objective

Verify that the API successfully retrieves all users.

## Test Case ID

API-001

## Preconditions

API endpoint is available.

## Steps

1. Launch Postman.
2. Send a GET request to /users.
3. Observe the response.

## Expected Result

* Status Code = 200 OK
* Response contains user records.
* Response body is returned in JSON format.

## Actual Result

* Status Code = 200 OK
* Response contained 10 user objects.
* Response returned in JSON format.

## Status

Pass

---

## Assertions Used

### Status Code Validation

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

### User Count Validation

```javascript
pm.test("Response contains users", function () {
    let jsonData = pm.response.json();
    pm.expect(jsonData.length).to.be.above(0);
});
```

### Response Time Validation

```javascript
pm.test("Response time is less than 1000ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(1000);
});
```

### Content-Type Validation

```javascript
pm.test("Content-Type is application/json", function () {
    pm.expect(pm.response.headers.get("Content-Type"))
      .to.include("application/json");
});
```
