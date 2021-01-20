# Requirements
We want to develop 4 APIs:

### Post new question: `http://localhost:5000/questions`
with body:
```json
{
  "author": "Daniel",
  "message": "Message text"
}
```
Response should be 201:
```json
{
  "id": 1,
  "author": "Daniel",
  "message": "Message text",
  "replies": 0
}
```

### Post a reply to a message: `http://localhost:5000/questions/{questionId}/reply`
with body:
```json
{
  "author": "Reply author",
  "message": "Message reply text"
}
```
Response should be 201:
```json
{
  "questionId": 1,
  "id": 5,
  "author": "Reply author",
  "message": "Message reply text"
}
```

### Get a thread: `http://localhost:5000/questions/{questionId}`,
the response should look like:
```json
{
  "id": 1,
  "author": "Daniel",
  "message": "Message text",
  "replies": [
    {
       "id": 5,
       "author": "Reply author",
       "message": "Message reply text"
    },
    ...
  ]
}
```

### Get a list of questions: `http://localhost:5000/questions`
The response should look like:
```json
[
    {
      "id": 1,
      "author": "Daniel",
      "message": "Message text",     
      "replies": 0
    },
    ...
]
```
