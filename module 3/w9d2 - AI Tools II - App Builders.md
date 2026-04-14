

# AI Tools II - App Builders



## Intro

- What we'll see in this session
    - AI App Builders (aka AI coding agents / AI prototyping tools)

- "Vibe Coding"




## AI App Builders

Design generators:
- Stitch (https://stitch.withgoogle.com)

Some popular AI-powered app builders / AI prototyping tools:
- bolt.new
- lovable.dev
- Replit Agent
- ...

Other related tools:
- UI generators: v0.dev (react, tailwind)
- Gemini canvas: https://www.linkedin.com/posts/addyosmani_programming-softwareengineering-ai-activity-7308542354821394432-AdnZ





## Demo I: Lovable

Pricing:
- https://lovable.dev/pricing#pricing-section
    - `On the free plan, you get 5 credits per day, with a total limit of 30 credits per month.`
    - For info on how each credit is calculated, see the FAQs "What is a credit?"

Code functionality:
- Chat (plan / build): create a new app from a prompt
- Chat: ask for changes
- Visual edits (allows you to select an element in the UI and change it)
- Code mode (allows you to see and modify the code)

Demo:
- initial request:
    <!-- 
    @LT: 
        - it may be good to start with the mode "Plan"... but it may burn all credits
        - do all testing for this session on a separate account 😉
    -->
    - option1: `Create the homepage for a coding school`
    - option2: `Create the homepage for a Fitness & Workouts app`
- note: may need to enable "Cloud mode", so that it allows Databases 
- add contact form
    - `Add a contact form that saves inquiries to the database and sends email notifications.`
- add user authentication


- See code
    - Probably using React + RadixUI


- Publish / Deploy


Some examples (generated with Lovable):
- Example 1 (Workouts homepage): 
    - https://demo-workouts-app.lovable.app/
    - Includes a form (when a form is submitted, it will send a confirmation email to the user and add an entry in the DB)
- Example 2 (Fitness homepage): 
    - https://demo-fitness-homepage.lovable.app/
    - It's just the homepage (used the "plan" mode with a few changes, and it burned most of the credits in the free tier).


Other features:
- generate the code from a screenshot or design (eg. Figma)
- database (uses Supabase)
- integration with AI models
- e-commerce
- analytics
- security scan
- speed analysis
- deployment + domains



## Demo II: Bolt.new

Pricing:
- https://bolt.new/pricing

Goal:
- Create an app for teachers to generate random pairs and keep track of previous pairs.


Example A - Fitness Homepage:
    - note: can do "meta-prompting" (ie. use an LLM to create a detailed prompt)
    - example: `I want to create a prompt to generate a Fitness Homepage with bolt.new. The goal is to maximize conversion (increase free trial registrations). Help me craft a good quality prompt. If needed more information, ask me before generating the final prompt.`.

Example B - Iteration 1 - Initial prompt:
<!--
    note: 
    - as of apr. 2026 the free tier is more limited, and this prompt will likely burn all the tokens in the free tier
    - do "Example A" instead
-->
- Create a responsive web app for teachers to manage student pairing in class activities.
- Core features
    - Teacher authentication (email/password).
    - Ability to create and manage multiple groups/classes.
    - Add, edit, and remove students within each group.
    - Generate random student pairs for a selected group.
    - When a pair is generated, store it in a “pair history” with timestamp.
    - Prevent or warn about recently used pairs (configurable, e.g. last N sessions).
    - View pair history per group and per student.
    - Button to regenerate pairs.

Example B - Iteration 2 - Pairing History Grid:
- Implement functionality so that the user can see the history of pairs of a group as a grid.
- Functionality:
    - Display a matrix/grid similar to a spreadsheet.
    - The first row lists all students in the group (names).
    - The first column lists the same students, in the same order.
    - Each cell at the intersection (Student A × Student B) shows the number of times those two students have been paired together.
    - The diagonal cells (same student) should be disabled or shown as “—”.
    - The grid updates automatically when new pairs are generated.
    - Data is computed from the stored pair history (do not store counts redundantly).


- See code
    - Probably using React + RadixUI

- Publish / Deploy


Possible final result:
- generated with bolt.new: https://teacher-student-pair-pf01.bolt.host
- generated with Lovable: https://teacher-student-pair.lovable.app/
    - note: students need to be added first in the page "Students", before they can be added to a group



Other features in bolt.new:
- import from Github
- import from Figma
- database (uses its own DB but can also be connected to Supabase)
- authentication



## Some other examples

Examples:
- create an Instant Resume Analyzer

- For an app that will allow users to practice their language skills by having a realtime voice conversations with an AI, create the private area for logged in users (users need to be able to start a new conversation, see how many minutes they have remaining, see some stats, logout, etc).

- create the homepage for a furniture company that offers beautiful pieces of furniture and shipping everywhere in Germany

- create a REST API with Express and PostgreSQL. API should implement auth functionality with jwt, CRUD on projects and CR on tasks.

- Create a react app to generate random pairs with students. The app will let you create a cohort & add a list of students for that cohort (by entering all the names in comma separated format). Once you have created a cohort, you can generate random pairs (if there's an odd number of students, it will generate a group of 3). If you like the pairs generated, you can click a button to confirm. One you confirm, those pairs will be added to a "pairs history". The user can visit the pairs history to see a table with all the students that have already been matched together. Also, when you create new random pairs, the app will avoid pairing students that have already worked together.



## Use cases

- Vibe Coding

- MVP Development
    - Building a functional "Minimum Viable Product"
    - Especially for relatively simple apps / internal tools

- Prototyping 
    - Instead of showing investors static Figma slides, founders create live, clickable apps with real data to demonstrate their vision.

- Brainstorming (if you don't have clear specs, it may be great to give you some interesting ideas)



## Warnings and limitations ⚠️

- Requires some basic knowledge
    - You don't need to code, but you do need to understand concepts like "database tables," "API keys," and "deployment" to get past the 80% mark.

- Complex apps
    - With current state-of-the-art tooling, AI app builders work well for MVPs and simple products, but often struggle with complex applications (e.g. apps that require deep domain logic, long-term maintainability, or nuanced architectural decisions).

- The "Vibe Coding" Ceiling
    - There is a limit to what "just talking" can achieve.
    - If your app requires highly specific business rules, the AI may start "hallucinating" solutions that look correct but fail in edge cases.

    - (meme) When I try out vibe coding with AI:
        - https://thecodinglove.com/when-i-try-out-vibe-coding-with-ai

- Performance, Security & Compliance Gaps
    - Not for "Big Tech" scale: Great for thousands of users; risky for millions without a human dev team.

- Using AI to find quick solutions vs. learning
    - This tools may be great to find a quick solution but, if your goal is to learn the fundamentals, they may actually work against you by obscuring core concepts.



## Recommendations

- For learning → keep practicing
- For quick apps and prototypes → AI App Builders (e.g. Lovable, Bolt.new)
- For complex projects → AI Coding Assistants (e.g. Github Copilot, Claude Code)

Remember that, as of today, core coding skills are required for most dev jobs.



## Practice: App Builders & Vibe Coding

<!--
alternative:

Ask Lovebale and bolt.new to generate a page for the type of project you're building for project-3
(it can be the homepage or any other internal page)

It may be useful to get some ideas & even specific components.
-->

Use Lovable or bolt.new to generate a simple app that helps users split expenses.

You can see a demo of a similar app here: https://spliit.app/

For example, users will need to be able to create a group of friends and add expenses (e.g. how much it was paid and who paid). 
The app should also tell you the balance for each person (e.g. who needs to pay and who needs to get money back)


