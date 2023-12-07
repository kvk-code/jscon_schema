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

## Adavantages and Use cases of JSON Schema

1. **Consistency and Validation**: JSON Schema ensures consistency in data representation. If different people are inputting student data, JSON Schema can enforce that all entries have the same fields, with the same field names and data types. This prevents errors and inconsistencies that could arise from different naming conventions or data formats.  

2. **Data Validation**: JSON Schema is not just about structure, but also about validating the data itself. For instance, it can ensure that an email field contains a valid email address, or that an age field contains a number within a specified range. This automatic validation saves time and reduces errors compared to manual data checks.

3. **Documentation**: A JSON Schema serves as a clear documentation of the data format. This is especially useful in API development where developers need to know the structure of the data being sent and received.  

4. **Automated Testing and Mock Data Generation**: With a defined schema, it's easier to write automated tests for your applications. Also, you can generate mock data that adheres to the schema for testing purposes.  

5. **Error Reporting**: When data validation fails, JSON Schema can provide detailed and specific error reports. This makes it easier to pinpoint exactly where and how the data is incorrect.  

6. **Data Modelling and Design**: When designing a new data format, JSON Schema can be used as a tool to model and refine the structure of the data.

7. **Compatibility and Integration**: If you're integrating with external systems, a JSON Schema ensures that the data exchanged between the systems adheres to a known and agreed-upon format.   

8. **Code Generation**: Some tools can generate data models or API client code directly from a JSON Schema, speeding up development.


Let's consider an example with a 'Student' object:

Without JSON Schema:  

* Person A creates a student record with `{ "firstName": "John", "lastName": "Doe", "age": 20, "email": "john.doe@example.com" }`

* Person B creates another record with `{ "name": "Jane Smith", "email_address": "jane.smith@example.org", "age": "twenty-one" }`  

Inconsistencies here include different field names for similar information (e.g., `firstName` vs `name`) and data types (age as a number vs a string).  

With JSON Schema:

* You define a schema that specifies that each student object must have `firstName`, `lastName`, `email`, and `age` fields, with `age` as an integer and `email` as a valid email string.

* Both Person A and B now have to conform to this schema, leading to consistent and valid data representation.


