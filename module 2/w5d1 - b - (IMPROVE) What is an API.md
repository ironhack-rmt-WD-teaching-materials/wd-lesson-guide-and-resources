

# What is an API?


<!--

Status: draft

@todo: create slides

-->


## Topics


- HTTP (refresh)


- (skip) HTTP headers
  > HTTP headers let the client and the server pass additional information with an HTTP request or response.

  - See MDN: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers

  - Examples:
    - Set-Cookie
    - User-Agent (Identify the user agent / browser)
    - Content-Type (Indicates the media type of the resource.)


- (skip) Content Types

  > "What if we wanted to request some data from a website across the internet and then do something programmatic with that data?"


- JSON

  <!-- @LT: 
  - can show movies.json from previous codealong
  - alternative: ask chatgpt to generate json with a list of recipes
  -->

  - JSON (JavaScript Object Notation) 
  - Format to transfer/exchange data (also used to store)
  - Very common (even in systems that don't use JavaScript)

  - Main differences between JSON and JS objects:
    - JSON: property names must be in quotes
    - JSON: double quotes (js objects can use single quotes)
    - JSON: cannot store the following data types: functions, date, undefined


  - JSON vs. JavaScript objects:
    - https://cope-ali.github.io/cope-ali261.github.io/img/JSONcomp.jpg



- APIs 
  - explain concept of API
    - "Application Programming Interface"
  - Diagram (with browsers, native apps): https://www.erp-information.com/wp-content/uploads/2021/01/Application-programming-interface-new.jpg
  - examples: 
    - twitter
    - spotify
    - Fake apis
      - Json Placeholder: http://jsonplaceholder.typicode.com/
    - Public APIs: 
      - https://github.com/public-apis/public-apis?tab=readme-ov-file
    - Example 1 (openbrewerydb):
      - https://www.openbrewerydb.org/
      - https://api.openbrewerydb.org/v1/breweries/
      - https://api.openbrewerydb.org/v1/breweries/5128df48-79fc-4f0f-8b52-d06be54d0cec
    - Example 2 (thesimpsonsapi):
      - https://thesimpsonsapi.com/
      - https://thesimpsonsapi.com/api/characters
      - https://thesimpsonsapi.com/api/locations
      

