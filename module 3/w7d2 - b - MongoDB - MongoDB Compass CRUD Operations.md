
# MongoDB - MongoDB Compass CRUD Operations

<!-- 

- Methodology: for all the part of operators, rather than explaining one by one
  - explain only the basic concepts (e.g. projection)


- @todo:
  - create a cheatsheet with all the different operators & how to use it
  - ask students to do the lab (they'll need to research & apply) 


Note: 
- in the database (IMDB) that we use for this lecture, year is stored as a string. 
- when we make the query, compare with a string (e.g. `{year: "2010"}`)


-->

## Intro

- CRUD
  https://i.imgur.com/CRowB2i.png



## Import Data


- We're going to import a DB from IMDB

  1. Download .zip from here: https://s3-eu-west-1.amazonaws.com/ih-materials/learning-units/movies.json.zip
    
    <!--  
      Note: 
      - downloaded here: "/Desktop/temp/imdb_json"
      - option 1: send .JSON directly on ZOOM 
      - option 2: send on Slack (works just fine, but students may not see where it is downloaded)
    -->

  2. Import: 
  
    Option 1: use mongoDB compass
      - create db: `cohortname-imdb` + collection `movies`
      - Click on the collection movies + Add Data + Import file

      <!-- @LT: choose this option (import through Compass) -->

    Option 2: 
      
      ```
      mongoimport --db video --collection movies --file movies.json --jsonArray
      ```
    - Mention: MongoDB comes with a command line tool to import data (e.g. JSON, CSV format, etc)


  3. See collection & documents

  4. Navigate to "Schema" tab.
    <!-- LT: demo only (ask students not to do it)  -->
    - there we can find stats of the schema of our documents
    - LT: Update the type of one document (e.g. change year to string)
    - takeover: **documents of the same collection can have a different schemas**

    - meme: SQL vs. MongoDB
      - https://programmerhumor.io/wp-content/uploads/2021/07/programmerhumor-io-databases-memes-backend-memes-1798da956a4b96a-758x954.png



## Update Documents

- Show how we can do it on Compass:
  - add fields
  - update fields
  - delete fields



## Delete Documents

- Show how to do it on Compass




## Read Documents


- Query Bar & Filter - Basic Query

  {title: "The Godfather"}
  {director: "Quentin Tarantino"}
  {year: "1994"}



- (skip) ObjectId()

  {_id: ObjectId('639ae2570db723509c5148f7')}



- Query with Logical Operators: $and, $or, $ne, $nor


{ $or: [ {year: ""}, {year: ""} ] }
{ $or: [ {director: "Francis Ford Coppola"}, {director: "Quentin Tarantino"} ] }


{ $and: [ { year: "2000", rate: "8.5" } ] }

Note: MongoDB provides an implicit AND operation when specifying a comma separated list of expressions.

{ year: "2000", rate: "8.5" }




- Query Projections (specify which fields we want)

{title: 1, year: 1}
{duration: 0, genre: 0}

Advantage: performance (Using projections makes our database queries faster).




- Sort Query Documents

{rate: 1} (ascending)
{rate: -1} (descending)



- Query Documents - Skip & Limit





## Comparison Query Operators

- (skip) $eq - Equal
- (skip) $ne - Not Equal

- $gt - Greater Than

  {rate: {$gt: "8.5"}}

- $gte - Greater Than Equal

- $lt - Less Than
- $lte - Less Than Equal




## Array Query Operators

$in:
- selects the documents where the value of a filed equals ANY (Logical OR) value in the specified array.

{year: { $in: ["1990", "1991", "1992"] } }


$nin
- selects the documents where the field value is not in the specified array or the field does not exist.


$all
- documents where the value of a field is an array that contains all the specified elements




## (skip) Element Query Operators


$exists
- Matches documents that have the specified field.	
- { field: { $exists: <boolean> } }

$type: 
- Selects documents if a field is of the specified type.
- { field: { $type: <BSON type> } }




## Exercise:

Practice: MongoDB CRUD operations

- Instructions: https://gist.github.com/luisjunco/42d608e3f96d712bc136ffbc4b2627bf
- Solutions: https://gist.github.com/luisjunco/54aa7b16c76bc868e8c94787d536f07f

- Time: 20min.
- How: individual / in pairs

