# json_schema

## A Sample JSON Schema and Object Confirming to the Schema

```bash
| JSON Schema                           | Student Object                          |
|---------------------------------------|-----------------------------------------|
| `{                                    | `{                                      |
|   "$schema": "http://json-schema.org/ |   "id": 12345,                          |
|   draft-07/schema#",                  |   "name": "Alex Johnson",               |
|   "title": "Student",                 |   "email": "alex.johnson@example.edu",  |
|   "type": "object",                   |   "age": 21,                            |
|   "properties": {                     |   "isEnrolled": true,                   |
|     "id": {                           |   "courses": ["Biology 101",            |
|       "type": "integer",              |                "Mathematics 202",       |
|       "description": "The unique      |                "Literature 303"],       |
|       identifier for a student"       |   "address": {                          |
|     },                                |     "street": "456 University Blvd",     |
|     "name": {                         |     "city": "College Town",             |
|       "type": "string",               |     "postalCode": "78901"               |
|       "description": "Name of the     |   }                                     |
|       student"                        | }                                       |
|     },                                |                                         |
|     "email": {                        |                                         |
|       "type": "string",               |                                         |
|       "format": "email",              |                                         |
|       "description": "The student's   |                                         |
|       email address"                  |                                         |
|     },                                |                                         |
|     "age": {                          |                                         |
|       "type": "integer",              |                                         |
|       "minimum": 0,                   |                                         |
|       "description": "Age of the      |                                         |
|       student"                        |                                         |
|     },                                |                                         |
|     "isEnrolled": {                   |                                         |
|       "type": "boolean",              |                                         |
|       "description": "True if the     |                                         |
|       student is currently enrolled"  |                                         |
|     },                                |                                         |
|     "courses": {                      |                                         |
|       "type": "array",                |                                         |
|       "items": {                      |                                         |
|         "type": "string"              |                                         |
|       },                              |                                         |
|       "description": "List of courses |                                         |
|       the student is enrolled in"     |                                         |
|     },                                |                                         |
|     "address": {                      |                                         |
|       "type": "object",               |                                         |
|       "properties": {                 |                                         |
|         "street": { "type": "string" },|                                         |
|         "city": { "type": "string" },  |                                         |
|         "postalCode": { "type":       |                                         |
|         "string" }                    |                                         |
|       },                              |                                         |
|       "required": ["street", "city",  |                                         |
|       "postalCode"],                  |                                         |
|       "description": "The student's   |                                         |
|       address"                        |                                         |
|     }                                 |                                         |
|   },                                  |                                         |
|   "required": ["id", "name", "email", |                                         |
|   "age", "isEnrolled"]                |                                         |
| }`                                    |                                         |




```






