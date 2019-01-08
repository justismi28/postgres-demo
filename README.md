## postgres-demo
SpringBoot RESTful endpoint with PostgreSQL backend to store Questions and Answers

# Sample Question POST
Using Postman you can post a body with the JSON keys ```title``` and ```description``` 
```
{
	"title":"How to use PostgreSQL with Spring Boot and JPA",
	"description":"I want to use PostgreSQL with Spring Boot and JPA and develop RESTful APIs. Please help!"
}
```

A successful posting should return a 200 OK response with a body similar to the following 
```
{
    "id": 1000,
    "title": "How to use PostgreSQL with Spring Boot and JPA",
    "description": "I want to use PostgreSQL with Spring Boot and JPA and develop RESTful APIs. Please help!"
}
```
