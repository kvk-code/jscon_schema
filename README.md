# json_schema

## A Sample JSON Schema and Object Confirming to the Schema

```bash

| JSON Schema                                                                      | Student Object                          |
|----------------------------------------------------------------------------------|-----------------------------------------|
| `{                                                                               | `{                                      |
|   "$schema": "http://json-schema.org/draft-07/schema#",                          |   "id": 12345,                          |
|   "title": "Student",                                                            |   "name": "Alex Johnson",               |
|   "type": "object",                                                              |   "email": "alex.johnson@example.edu",  |
|   "properties": {                                                                |   "age": 21,                            |
|     "id": {                                                                      |   "isEnrolled": true,                   |
|       "type": "integer",                                                         |   "courses": ["Biology 101",            |
|       "description": "The unique identifier for a student"                       |                "Mathematics 202",       |
|     },                                                                           |                "Literature 303"],       |
|     "name": {                                                                    |   "address": {                          |
|       "type": "string",                                                          |     "street": "456 University Blvd",     |
|       "description": "Name of the student"                                       |     "city": "College Town",             |
|     },                                                                           |     "postalCode": "78901"               |
|     "email": {                                                                   |   }                                     |
|       "type": "string",                                                          | }                                       |
|       "format": "email",                                                         |                                         |
|       "description": "The student's email address"                               |                                         |
|     },                                                                           |                                         |
|     "age": {                                                                     |                                         |
|       "type": "integer",                                                         |                                         |
|       "minimum": 0,                                                              |                                         |
|       "description": "Age of the student"                                        |                                         |
|     },                                                                           |                                         |
|     "isEnrolled": {                                                              |                                         |
|       "type": "boolean",                                                         |                                         |
|       "description": "True if the student is currently enrolled"                 |                                         |
|     },                                                                           |                                         |
|     "courses": {                                                                 |                                         |
|       "type": "array",                                                           |                                         |
|       "items": { "type": "string" },                                             |                                         |
|       "description": "List of courses the student is enrolled in"                |                                         |
|     },                                                                           |                                         |
|     "address": {                                                                 |                                         |
|       "type": "object",                                                          |                                         |
|       "properties": {                                                            |                                         |
|         "street": { "type": "string" },                                          |                                         |
|         "city": { "type": "string" },                                            |                                         |
|         "postalCode": { "type": "string" }                                       |                                         |
|       },                                                                         |                                         |
|       "required": ["street", "city", "postalCode"],                              |                                         |
|       "description": "The student's address"                                     |                                         |
|     }                                                                            |                                         |
|   },                                                                             |                                         |
|   "required": ["id", "name", "email", "age", "isEnrolled"]                       |                                         |
| }`                                                                               |                                         |

```
* The `"type": "object"` indicates that the JSON data should be an object. 

* The `"properties"` field is an object that defines the properties allowed in the data. Each property (like `id`, `name`, `email`, etc.) is defined with its own type and optional description.

* The `"type"` inside each property definition specifies the data type of that property (`"integer"`, `"string"`, `"boolean"`, `"array"`, `"object"`).  

* `"required"` is an array of strings where each string is the name of a property. This means that these properties must be present in the JSON data.
   
* Additional validation keywords like `"minimum"` for numbers and `"format": "email"` for strings are used to add further constraints.

* Nested objects and arrays can also be defined, as shown in the `address` and `courses` properties.

## JSON Schema Minimal Requirements

1. `$schema`: This is a URI (Uniform Resource Identifier) that indicates which version of the JSON Schema specification the schema is written in. It's like declaring the 'syntax rules' your schema follows. For example, `"$schema": "http://json-schema.org/draft-07/schema#"` indicates that the schema is using Draft 7 of the JSON Schema Specification.  

2. `type`: This keyword defines the data type for the JSON data. The basic types in JSON Schema are:

    * `string`
    * `number`
    * `integer`
    * `boolean` 
    * `array`
    * `object`
    * `null`

3. `properties` (for objects): This is used to define the properties or fields of an object, what type each property is, and other details about each property. For example, if you're defining a schema for an object that represents a person, you might have properties like `name`, `age`, and `email`.

4. `items` (for arrays): When you have an array type, `items` is used to specify the schema for the elements within the array.  

5. `required`: This is an array of strings where each string is the name of a property in an object. It defines which properties must be present in the JSON data for it to be valid against the schema.




