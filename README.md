# Task 4 - Animal Adoption Platform API Documentation

## Project Structure

src/
    routes/
        pets.route.js
        clinics.route.js
        articles.route.js
    controllers/
        pets.controller.js
        clinics.controller.js
        articles.controller.js
    middlewares/
        handleId.js
    models/
        pet.model.js
        clinic.model.js
        article.model.js
    app.js
    server.js
.gitignore
.env

## Libraries
- express
- dotenv
- morgan
- mongoose (if you want to use mongodb)
- nodemon

## APIs Documentation

### Pets Endpoints

#### 1. Get All Pets (Filtered)
- Method: GET  
- Endpoint: `/api/pets`  
- Query Params:  
  - `location` (optional): Filter by city  
  - `type` (optional): Filter by pet type (cat/dog)  
- Response:  
```json
  {  
    "message": "Pets retrieved successfully",
    "data": [
      {
        "id": 1,
        "name": "Max",
        "type": "dog",
        "age": 3,
        "isFree": true,
        "location": "Roma"
      }
    ]
  }
```
- Errors: 
    - 404: No data fits your filter

#### 2. Add new Pets
- Method: POST  
- Endpoint: `/api/pets`  
- Request Body:  
  - `name` 
  - `type`
  - `age`
  - `location`
  - 'isFree'
- Response:  
```json
  {
    "message": "Add new Pet successfully",
    "data": {
        "id": 1,
        "name": "Max",
        "type": "dog",
        "age": 3,
        "isFree": false,
        "location": "Roma"
      }
  }
```
- Errors: 
    - 400: Wrong data

#### 3. Update a Pet
- Method: PUT  
- Endpoint: `/api/pets/:id`  
- Request Body:  
  - `name` 
  - `type`
  - `age`
  - `location`
  - `isFree`
- Request Params: id
- Response:  
```json
  {
    "message": "Updated Pet successfully",
    "data": {
        "id": 1,
        "name": "Max",
        "type": "dog",
        "age": 3,
        "isFree": false,
        "location": "Roma"
      }
  }
```
- Errors: 
    - 400: Wrong data
    - 404: Pet not found

#### 4. Delete a Pet
- Method: DELETE
- Endpoint: `/api/pets/:id`  
- Request Params: id
- Response:  
```json
  {
    "message": "Deleted Pet successfully",
  }
```
- Errors: 
    - 404: Pet not found

#### 5. Get single Pet
- Method: GET
- Endpoint: `/api/pets/:id`  
- Request Params: id
- Response:  
```json
  {
    "message": "Get Pet successfully",
    "data": {
        "id": 1,
        "name": "Max",
        "type": "dog",
        "age": 3,
        "isFree": false,
        "location": "Roma"
      }
  }
```
- Errors: 
    - 404: Pet not found

### Clinics Endpoints

#### 1. Get All Clinics (Filtered)
- Method: GET  
- Endpoint: `/api/clinics`  
- Query Params:  
    - location (optional): Filter by city
    - emergency (optional): true/false
    - openNow (optional): true/false 
- Response:  
```json
  {
    "message": "Clinics retrieved successfully",
    "data": [
      {
        "id": 1,
        "name": "Emergency Vet Roma",
        "location": "Roma",
        "emergency": true,
        "openNow": true
      }
    ]
  }
```
- Errors: 
    - 404: No data fits your filter

#### 2. Add new clinic
- Method: POST  
- Endpoint: `/api/clinics`  
- Request Body:  
  - `name` 
  - `location`
  - `emergency`
  - `openNow`
- Response:  
```json
  {
    "message": "Add new clinic successfully",
    "data": {
        "id": 1,
        "name": "Emergency Vet Roma",
        "location": "Roma",
        "emergency": true,
        "openNow": true
      }
  }
```
- Errors: 
    - 400: Wrong data

#### 3. Update a clinic
- Method: PUT  
- Endpoint: `/api/clinics/:id`  
- Request Body:  
  - `name` 
  - `location`
  - `emergency`
  - `openNow`
- Request Params: id
- Response:  
```json
  {
    "message": "Updated clinic successfully",
    "data": {
        "id": 1,
        "name": "Emergency Vet Roma",
        "location": "Roma",
        "emergency": true,
        "openNow": true
      }
  }
```
- Errors: 
    - 400: Wrong data
    - 404: Clinic not found

#### 4. Delete a Clinic
- Method: DELETE
- Endpoint: `/api/clinics/:id`  
- Request Params: id
- Response:  
```json
  {
    "message": "Deleted Clinic successfully",
  }
```
- Errors: 
    - 404: Clinic not found

#### 5. Get single Clinic
- Method: GET
- Endpoint: `/api/clinics/:id`  
- Request Params: id
- Response:  
```json
  {
    "message": "Get Clinic successfully",
    "data": {
        "id": 1,
        "name": "Emergency Vet Roma",
        "location": "Roma",
        "emergency": true,
        "openNow": true
      }
  }
```
- Errors: 
    - 404: Clinic not found


### Articls Endpoints

#### 1. Get All Articls (Filtered)
- Method: GET  
- Endpoint: `/api/articls`  
- Query Params:  
    - type (optional): Filter by type of animal
- Response:  
```json
  {
    "message": "Articls retrieved successfully",
    "data": [
      {
        "id": 1,
        "title": "How can you play with your cat",
        "type": "cat",
        "body": "You can make ......",
      }
    ]
  }
```
- Errors: 
    - 404: No data fits your filter

#### 2. Add new article
- Method: POST  
- Endpoint: `/api/articls`  
- Request Body:  
  - `title` 
  - `body`
  - `type`
- Response:  
```json
  {
    "message": "Add new article successfully",
    "data": {
        "id": 1,
        "title": "How can you play with your cat",
        "type": "cat",
        "body": "You can make ......",
      }
  }
```
- Errors: 
    - 400: Wrong data

#### 3. Update an article
- Method: PUT  
- Endpoint: `/api/articls/:id`  
- Request Body:  
  - `title` 
  - `body`
  - `type`
- Request Params: id
- Response:  
```json
  {
    "message": "Updated article successfully",
    "data": {
        "id": 1,
        "title": "How can you play with your cat",
        "type": "cat",
        "body": "You can make ......",
      }
  }
```
- Errors: 
    - 400: Wrong data
    - 404: Article not found

#### 4. Delete an Article
- Method: DELETE
- Endpoint: `/api/articls/:id`  
- Request Params: id
- Response:  
```json
  {
    "message": "Deleted Article successfully",
  }
```
- Errors: 
    - 404: Article not found

#### 5. Get single Article
- Method: GET
- Endpoint: `/api/articls/:id`  
- Request Params: id
- Response:  
```json
  {
    "message": "Get Article successfully",
    "data":  {
        "id": 1,
        "title": "How can you play with your cat",
        "type": "cat",
        "body": "You can make ......",
      }
  }
```
- Errors: 
    - 404: Article not found

- Generic server error: 500 => Server Error
