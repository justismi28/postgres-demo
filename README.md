# postgres-demo
SpringBoot RESTful endpoint with PostgreSQL backend to store Questions and Answers

## Sample Question POST
Using rest tool of choice (postman, curl, etc...) you can post a body with the JSON keys `title` and `description` 
```
{
	"title":"How to use PostgreSQL with Spring Boot and JPA",
	"description":"I want to use PostgreSQL with Spring Boot and JPA and develop RESTful APIs. Please help!"
}
```
###### question cURL
```
curl -d '{"title":"How to use PostgreSQL with Spring Boot and JPA","description":"I want to use PostgreSQL with Spring Boot and JPA and develop RESTful APIs. Please help!" }' -H "Content-Type: application/json" -X POST http://localhost:8080/questions
```

A successful posting should return a 200 OK response with a body containing the Database ID, question(title), and description from original request. 
```
{
    "id": 1000,
    "title": "How to use PostgreSQL with Spring Boot and JPA",
    "description": "I want to use PostgreSQL with Spring Boot and JPA and develop RESTful APIs. Please help!"
}
```


## Answer POSTS 
To create a new answer to a previously asked question, you POST to `.../questions/${id}/answers` Where the id is the question db id.
Using rest tool of choice (postman, curl, etc...) you can post a body with the JSON keys `text` to create a new answer with the 

###### answer JSON sample body
```
{
	"text":"It's very easy to configure PostgreSQL in a spring boot app."
}
```
###### answer cURL
```
curl -d '{"text":"It's very easy to configure PostgreSQL in a spring boot app."}' -H "Content-Type: application/json" -X POST http://localhost:8080/questions/1000/answers
```

A successful posting should return a 200 OK response with a body containing the Database Id and posted text.
```
{
    "id": 1000,
    "text": "It's very easy to configure PostgreSQL in a spring boot app."
}
```