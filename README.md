# **Project Summary**

This project aims to demonstrate the use of Postman to perform automated tests on the [The Dog API](https://thedogapi.com/). Below are the steps taken, configurations implemented, and tests created to validate different aspects of the API.

---

## **Configurations Made**

### **1. Environment Variables**

- We set up environment variables to dynamically manage values.
  
- These variables allow the reuse of values without needing to configure them manually in each request.

### **2. Pre-request Scripts**

- We implemented pre-request scripts to generate dynamic data and configure authentication headers using the API key.

### **3. Test Scripts**

- We added validation scripts to verify the API responses:
  
    - Status code validation.
    
    - Property verification in the JSON responses.
    
    - Storing dynamic values for use in subsequent requests.

---

## **Implemented Tests**

### **1. Basic Requests**

- **GET /v1/breeds**: We retrieved a list of breeds and validated:
  
    - Status code (200).
    
    - Each breed contains an `id` and a `name`.
    
    - We stored the `breed_id` of the first breed for future tests.
  
- **POST /v1/votes**: We created a dynamic vote using previously generated values and validated:
  
    - Status code (201).
    
    - The response contains a `vote_id` of the created vote.
  
- **DELETE /v1/votes/{vote_id}**: We deleted a previously created vote and verified:
  
    - Status code (200).
    
    - Confirmation of successful deletion.

### **2. Tests with Dynamic Data**

- We used scripts to extract dynamic values from the responses (e.g., `breed_id`) and set them as environment variables for subsequent requests.

### **3. Data-Driven Testing**

- We integrated a JSON file with test data (`data.json`) to perform multiple `POST /v1/votes` requests with different input values.
  
- This allowed us to validate the API functionality with different scenarios.

### **4. Performance Validations**

- We added global tests to measure the response time of each request, ensuring that the times are below a defined threshold (1000 ms).

---

## **Advanced Extensions**

### **1. Organization**

- We grouped the requests into logical folders to maintain a clear and easy-to-navigate structure.

---

