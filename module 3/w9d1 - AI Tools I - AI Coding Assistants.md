

# AI tools I - AI Coding Assistants



## Intro: Popular AI Coding Assistants

- GitHub Copilot
- Cursor
- Windsurf
- Google Antigravity
- Openai Codex
- Claude Code
<!-- - Open Code -->



## GitHub Copilot

<!-- 
@LT: 
- for this demo, open a repo with an Express API or, even better, a full-stack app.
- for example, can use this repo (includes backend + frontend):
    - https://github.com/ironhack-feb2026-undefinedSquad/w8d2-demo-ai-powered-apps
-->

- url: https://github.com/features/copilot/plans

- settings
    - eg: enable/disable
    - choosing model

- code completions:
    - `function findLongestStringInArray(){}`
    - `const words = []`

- code suggestions from comments
    - example 1:
        - `// function to find the average in an array of numbers`
    - example 2:
        - `// GET /api/recipes/random`
    - example 3:
        - create file middleware/isOwner.js 
        - `// middleware function to verify if the user is the owner of the resource`

- (skip) inline chat and speech-to-text
    - note: now it's available in the copilot menu (at the top)
    - example 1: create a function that takes two arrays and returns true if they have exactly the same values
    - example 2: make this function generic, so that it works with any nested levels (ie. arrays of any depth).

- chat in sidebar:
    - main options: ask, agent, plan
    - choosing model (included vs. premium)
    - passing/defining context
        - instructions file (see below)
    
    - demo: Ask
        - example 1: how do i uninstall an npm package ? / provide a list with all endpoints in this api.
        - example 2: When I try to create a new project with Postman, I'm getting this error message: `ValidatorError: `abc` is not a valid enum value for path `difficulty`.`
    - demo: Agent
        - example 0 (quick teaser, basic functionality): 
            - create an endpoint to get a random recipe (or the number of recipes)
        - explain briefly how agents work:
            - diagram (agent loop): https://code.visualstudio.com/assets/docs/copilot/concepts/agent-loop.png
            - more info: https://code.visualstudio.com/docs/copilot/concepts/agents
        - example 1: 
            - rename the field "Instructions" as "cooking instructions"
        - example 2: 
            - (attempt 1 - simple) implement functionality so that users can generate images with AI: when the user creates a new recipe, they can click a button "Generate Image with AI" to generate an image (if they click on that button, an image will be generated, and the user can see a preview before submitting). Follow the same pattern as the existing feature "Generate Instructions with AI".
            - (attempt 2 - more specific) Add an AI image generation feature following the existing "Generate Instructions with AI" pattern: create a POST /api/recipes/generate-image authenticated backend route that takes the recipe title, ingredients, and difficulty, calls an image generation API, and returns { imageUrl }. Add an optional image field to the Recipe model. On the frontend in AddRecipe.jsx, add a "Generate Image with AI" button that calls this endpoint, shows a loading state and image preview, and includes the image URL when submitting the form.

        - (skip) example 3: 
            - implement functionality for image upload with cloudinary. If you need anything from me, ask.
        - example 4 (even more complex):
            - implement functionality for ingredients (users should be able to create ingredients. When you create or edit a recipe, the user can choose from the list of available ingredients)
            <!-- 
            note: without good instructions, this may fail
            (consider providing much more detailed instructions and/or, using the "plan" mode)
            -->
        - example 5 (debugging): uninstall mongoose & paste the error "mongoose is not defined"
    - demo: Plan
        - use any of the examples above (e.g. functionality for "ingredients")

    - Full demo:
        - In the backend: implement functionality for Ingredients (e.g. C+R)
        - In the frontend: implement functionality for Ingredients (e.g. C+R)
        - Planning
            - example 1 (plan a full app): https://chatgpt.com/share/69d7596b-7c10-8326-9bdc-5c2010db826f
            - example 2 (plan a change which is complex and/or affects many different parts)


    - providing context
        - tip: if you need to add all files as context, use `#codebase`

- sparkles (e.g. commit message)




## Further examples and use cases

- Copilot can be really good at doing things with existing libraries and apis (especially if they're popular & not very recent)
    - e.g.: `// get most popular artists from spotify api`

- It can also be useful to generate unit tests
    - e.g. `unit tests for a function that will receive a string and verify if it's a valid email address`
    - e.g. `generate unit tests for all endpoints on the project model`

- And also to generate readme files (at least a first version).




## (skip) Custom instructions file

> Instruction files enable you to specify custom instructions in Markdown files. 
> You can use these files to define your coding practices, preferred technologies, and project requirements.


- (skip) Agent specific files
    - e.g. `.github/copilot-instructions.md`: a single instruction file that contains all the instructions for your workspace. These instructions are automatically included in every chat request.
    - e.g. `CLAUDE.md`: 

- `AGENTS.md`
    - increasingly adopted by some agent-style tools


- example: 

    ```md
    General Guidelines:
    - Use modern JavaScript/TypeScript (ES6+).
    - Follow project coding standards and existing patterns.
    - For React projects, prefer functional components and hooks.

    Tech stack & preferred Libraries:
    - React
    - Next.js
    - Tailwind CSS
    - Axios (for HTTP requests)

    File Structure:
    - Use `components/` for reusable UI components.
    - Use `pages/` for route-level components (Next.js).
    - Use `utils/` for utility functions and API logic.

    Other notes:
    - For promises, use async/await

    ```

- (skip) demo:
    ```
    Handling promises:
    - For existing functionality: keep it as it is (e.g. if it uses .then.catch, keep it as it is)
    - For any new functionality, handle promises with use async/await
    ```
    - implement an endpoint to get a random recipe

- more info: https://code.visualstudio.com/docs/copilot/copilot-customization



## Giving some Super-powers to your agent (MCPs + Agent Skills)

MCP vs. Skills:
- MCP = connections (allows the agent to connect to other tools)
- Skills = abilities (tells the agent how to perform a specific task)


MCP:
- > MCP (Model Context Protocol) is a standardized interface that lets AI coding assistants securely connect to external tools and data sources in a structured way.
- examples:
    - Managing GitHub repos (issues, PRs, commits) directly from the assistant
    - Deploying a web app to Vercel or similar hosting platforms
    - ...


Agent Skills
- > Agent skills are predefined capabilities that let an AI agent do more than just generate text. They define what the agent is able to do, such as using tools, running commands, accessing files or APIs, and completing specific tasks step by step.


Demo without skills:
- "make the react app look good"
- worth to mention: this is a terrible prompt ;)

Demo with skills:
- install this skill: https://skills.sh/anthropics/skills/frontend-design
- repeat the same prompt "make the react app look good"


Other interesting skills:
- component libraries (e.g. mantine)
- apis (e.g. mistral)
- https://skills.sh/vercel/ai/ai-sdk
- https://skills.sh/vercel-labs/agent-skills/deploy-to-vercel
- https://skills.sh/vercel-labs/skills/find-skills


WARNING:
- > Review skills before use; they run with full agent permissions ⚠️⚠️
- Review skills before use because they execute with full agent permissions and may access files, run commands, or call external services, potentially causing security or unintended side effects
- Advice: if you install skills from skills.sh, use skills from trusted vendors (alternative, review them - ideally manually, as they may contain prompt injection)



<!-- 
Agent mode + MCP Servers + Skills:
- VS Code: Agent Mode + MCP Servers + BYOK: https://www.youtube.com/watch?v=dutyOc_cAEU
- Demo: Firebase MCP on VS Code
 -->




## Trends (2026)

CLI Coding assistants
- e.g. Claude Code

Independent/Asychronous Agents and parallelized work:
- (skip) Example using Copilot directly on Github (Addy Osmani):
    - https://www.linkedin.com/posts/addyosmani_ai-programming-softwareengineering-activity-7389186792706506752-BWnR
- e.g. Visual Studio Code Agents app
    - https://code.visualstudio.com/updates/v1_115#_visual-studio-code-agents-preview
- e.g. Claude Code + Playwright 
- e.g. Ralph Wiggum technique: https://www.youtube.com/watch?v=_IK18goX4X8

Other trends:
- AI tooling getting more and more powerful (not just models, but also the tools around them).
- Increasing reliance + costs rising


A tip from Alberta Tech:
- > If you wanna be in the top 99% early adopters, you're gonna be using dozens of useless tools to find the ones that work
- > There's nothing wrong with being like a month behind on all these new AI coding tools 
- https://www.youtube.com/watch?app=desktop&v=zXsuj6GFQIo




## Recommendations

Here's a video with very useful tips from TheCodingSloth:
- https://www.youtube.com/watch?v=91B_v-wOaws
- Tips:
    - Learn how to program first
    - Be specific
    - Smaller tasks give better results → break down the problem in smaller tasks
    - Do not let AI do all the thinking for you
    - Tell AI what you "don't" want
    - Generate a file with instructions for your AI tool (generate an AGENTS.md file / similar files depending on the tool)
    - MCPs can be very useful
    - Give AI a way to verify its work (e.g. unit tests)
    - Final thought: AI amplifies developers with good habits
- NOTE: 
    - The video is full of sponsorship to a very specific tool (junie) but, despite that being very annoying, all the tips and recommendations are top quality.


Here's an interesting post from Addy Osmani:
- https://www.linkedin.com/posts/addyosmani_ai-programming-softwareengineering-activity-7420197342873735168-xmGX/
- Summary:
    - 1. Specs before code (define specs before you start coding)
    - 2. Context is king - without it, LLMs can make incorrect assumptions
    - 3. Manage task granularity - just like with traditional engineering, do work in well defined tasks or chunks, not all at once
    - 4. Review and test what's important - LLMs are often an "over-confident pair programmer" 
    - 5. Git is your save point - commit early and often. 
    - Rely on the tools you know well, but try to make some time regularly to try out what's new.
    - "AI tools are incredible force multipliers, but they don't replace the need for engineering fundamentals. In fact, they reward them. The human engineer remains the director of the show."



## Warnings & Limitations 

- As you can see, to be a prompt engineer, one "must" know how to code.

- AI tools for Greenfield projects vs. commercial large codebases:
    - https://www.linkedin.com/posts/gergelyorosz_something-i-hear-very-little-talk-about-activity-7333488796627349505-QZnw


- Using AI to find quick solutions vs. learning
    - If you're learning a new technology, focus on practicing & disable autocompletion
    - "You will not learn a language by using Google Translator"

- Will AI replace developers? How to use AI to help you land a job?
    - https://chatgpt.com/share/6824e153-86ec-8003-a44f-33c5d9197b60


- (meme) When I try out vibe coding with AI:
    - https://thecodinglove.com/when-i-try-out-vibe-coding-with-ai


<!--
- Is AI really making software engineers 10x more productive? (Addy Osmani, Aug 2025)
    - Linkedin post: https://www.linkedin.com/posts/addyosmani_ai-programming-softwareengineering-activity-7363819659109793793-6q6_
    - Full article: https://addyo.substack.com/p/the-reality-of-ai-assisted-software
-->




## Resources

For latest updates and news on Github Copilot:
- https://www.youtube.com/@code


Claude Code - Every Claude Code Concept Explained for Normal People
- https://www.youtube.com/watch?v=ZlDnsf_DOzg
- 27:00
- march 2026


Midudev - Curso Inteligencia Artificial para Programadores en 2026 (Conceptos, Herramientas, Claude Code)
- https://www.youtube.com/watch?v=2aN_-m1uU4k
- midudev, 1h40min.
- Spanish

