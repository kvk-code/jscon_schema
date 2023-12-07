# json_schema

## A Samle JSON Object

<code> {

"id": 12345,

"name": "Alex Johnson", 

"email": "alex.johnson@example.edu",

"age": 21,

"isEnrolled": true,

"courses": ["Biology 101", "Mathematics 202", "Literature 303"],

"address": {

"street": "456 University Blvd",

"city": "College Town",

"postalCode": "78901"

}

\} </code>

## Corresponding Schema

<code>{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "Student",
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "description": "The unique identifier for a student"
    },
    "name": {
      "type": "string",
      "description": "Name of the student"
    },
    "email": {
      "type": "string",
      "format": "email",
      "description": "The student's email address"
    },
    "age": {
      "type": "integer",
      "minimum": 0,
      "description": "Age of the student"
    },
    "isEnrolled": {
      "type": "boolean",
      "description": "True if the student is currently enrolled"
    },
    "courses": {
      "type": "array",
      "items": {
        "type": "string"
      },
      "description": "List of courses the student is enrolled in"
    },
    "address": {
      "type": "object",
      "properties": {
        "street": { "type": "string" },
        "city": { "type": "string" },
        "postalCode": { "type": "string" }
      },
      "required": ["street", "city", "postalCode"],
      "description": "The student's address"
    }
  },
  "required": ["id", "name", "email", "age", "isEnrolled"]
}</code>



