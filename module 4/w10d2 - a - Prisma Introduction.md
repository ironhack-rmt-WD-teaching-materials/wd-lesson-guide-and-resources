
# Prisma Introduction

<!-- 

status: just some notes

@LT: keep it brief (students are familiar with most of those patterns, since they already know Mongoose)

-->



## Intro to Prisma

- What is Prisma


- Main elements (show in Student Portal)
  - Prisma Schema
  - Prisma Client
  - Prisma Migrate
  - Prisma Studio


- Watch this video (1min. quick intro to Prisma Schema, Client, Migrate & Studio):
  https://www.youtube.com/watch?v=EEDGwLB55bI


- Advantages of using Prisma (show in Student Portal)
  - Type-safe database access
  - Database agnostic
  - Schema migrations
  - Community and ecosystem




## Demo

- Follow all the steps in the Student Portal

  <!-- 
  
  @LT: do the same demo (library app).
  
  so that we can get the code for schema, same changes for migrations etc.
  
  -->




**IMPORTANT:**
- As of 2024.12.03: installing the latest version of Prisma (6.0.1) seems to give an error trying to connect to the DB
- Quick fix while we investigate: `npm i prisma@5.10.2 --save-exact`

- Note: 
  - if we do "prisma": "5.10.2" (exact version), we'll also need to do "@prisma/client": "5.10.2" (exact version).
  - if we keep "@prisma/client": "^5.10.2", it seems to give an error when we deploy on Render.com (version for prisma client needs to be exactly the same)



---


Some small changes for the demo:

- Section `Creating our first model`
  - Step 1. Start by creating a model with just id + title + year
  - Step 2: Explain the syntax for models (see `Field Definitions Explained (types, modifiers, and attributes)`)
  - Step 3: Copy the whole model & read the code together
  - Step 4: Configure Prisma for VS Code (see `Prisma extension for VS Code`)



How to explain the syntax for relationships in Prisma:
- see: https://chatgpt.com/share/674eb8ec-b8b4-8003-97a0-663450f3b5f0
- notes: 
  - when adding a relationship in Prisma, we add 3 new entries in the schema.
  - from those 3, only one will be a column in our tables (in this example, only `authorId` will be a new column; the other entries are used by Prisma)

