

# AI tools I - AI Coding Assistants


## GitHub Copilot

<!-- 
@LT: 
- for this demo, open a repo with an express application
- later on, can just create new files to demo this capabilities with React
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
        - `// GET /drinks`
    - example 3:
        - create file middleware/isOwner.js 
        - `// middleware function to verify if the user is the owner of the resource`

- (skip) inline chat and speech-to-text
    - note: now it's available in the copilot menu (at the top)
    - example 1: create a function that takes two arrays and returns true if they have exactly the same values
    - example 2: make this function generic, so that it works with any nested levels (ie. arrays of any depth).

- chat in sidebar:
    - choosing model (included vs. premium)
    - passing/defining context
        - instructions file (see below)
    - example 1: how do i uninstall an npm package ? / provide a list with all endpoints in this api.
    - example 2: create an endpoint that will give you the number of projects in the database
    - example 3: paste an error message
        - example - When I try to create a new project with Postman, I'm getting this error message: `Error while creating the project Error: Project validation failed: title: Path title is required.`
    - show options:
        - ask
        - edit
        - agent
            - example: uninstall mongoose & paste the error "mongoose is not defined"
    - providing context
        - tip: if you need to add all files as context, use `#codebase`
    - `@workspace` (e.g.: how many models we have)
    - `@vscode` (e.g.: whats the shortcut to change the language mode for the current file)

- Full demo:
    - In the backend: implement functionality for Clients (e.g. C+R)
    - In the frontend: implement functionality for Clients (e.g. C+R)


- sparkles (e.g. commit message)



## (skip) Custom instructions file

> Instruction files enable you to specify custom instructions in Markdown files. 
> You can use these files to define your coding practices, preferred technologies, and project requirements.

- `.github/copilot-instructions.md`: a single instruction file that contains all the instructions for your workspace. These instructions are automatically included in every chat request.

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

- more info: https://code.visualstudio.com/docs/copilot/copilot-customization



## Further examples and use cases

- Copilot can be really good at doing things with existing libraries and apis (especially if they're popular & not very recent)
    - e.g.: `// get most popular artists from spotify api`

- It can also be useful to generate unit tests
    - e.g. `unit tests for a function that will receive a string and verify if it's a valid email address`
    - e.g. `generate unit tests for all endpoints on the project model`

- And also to generate readme files (at least a first version).



## Popular AI Coding Assistants

- GitHub Copilot

- Cursor
    - Cursor Tutorial for Beginners: https://www.youtube.com/watch?v=ocMOZpuAMw4

- Windsurf

- Google Antigravity

- Claude Code


Copilot vs. Claude Code vs. Codex:
- https://chatgpt.com/c/6988d56d-a40c-832e-a8de-41734f4b93e9



A tip from Alberta Tech:
- > If you wanna be in the top 99% early adopters, you're gonna be using dozens of useless tools to find the ones that work
- > There's nothing wrong with being like a month behind on all these new AI coding tools 
- https://www.youtube.com/watch?app=desktop&v=zXsuj6GFQIo




## (skip) Asychronous Background Coding Agents

Example using Copilot directly on Github (Addy Osmani):
- https://www.linkedin.com/posts/addyosmani_ai-programming-softwareengineering-activity-7389186792706506752-BWnR



## Agent mode + MCP Servers

VS Code: Agent Mode + MCP Servers + BYOK
https://www.youtube.com/watch?v=dutyOc_cAEU


Demo: 
- Firebase MCP on VS Code



## Limitations

AI tools for Greenfield projects vs. commercial large codebases:
- https://www.linkedin.com/posts/gergelyorosz_something-i-hear-very-little-talk-about-activity-7333488796627349505-QZnw




## Recommendations

Here's a video with very useful tips from TheCodingSloth:
- https://www.youtube.com/watch?v=91B_v-wOaws
- Tips:
    - Learn how to program first
    - Be specific
    - Smaller tasks give better results (break down the problem in smaller tasks)
    - Do not let AI do all the thinking for you
    - Tell AI what you "don't" want
    - Tell AI to remember (generate an agents.md file / similar files depending on the tool)
    - MCPs can be very useful
    - Give AI a way to verify its work (e.g. unit tests)
    - Final thought: AI amplifies developers with good habits
    - Note: the video is full of sponsorship to a very specific tool (junie) but, despite that being very annoying, all the tips and recommendations are top quality.


Here's an interesting post from Addy Osmani:
- https://www.linkedin.com/posts/addyosmani_ai-programming-softwareengineering-activity-7420197342873735168-xmGX/
- Summary:
    - 1. Specs before code (define specs before you start coding)
    - 2. Context is king - without it, LLMs can make incorrect assumptions)
    - 3. Manage task granularity - just like with traditional engineering, do work in well defined tasks or chunks, not all at once
    - 4. Review and test what's important - LLMs are often an "over-confident pair programmer" 
    - 5. Git is your save point - commit early and often. 
    - Rely on the tools you know well, but try to make some time regularly to try out what's new.
    - "AI tools are incredible force multipliers, but they don't replace the need for engineering fundamentals. In fact, they reward them. The human engineer remains the director of the show."



## Warnings ⚠️ 

- As you can see, to be a prompt engineer, one "must" know how to code.

- Using AI to find quick solutions vs. learning
    - If you're learning a new technology, make sure you type things
    - "You will not learn a language by using Google Translator"

- Will AI replace developers? How to use AI to help you land a job?
    - https://chatgpt.com/share/6824e153-86ec-8003-a44f-33c5d9197b60


- (meme) When I try out vibe coding with AI:
    - https://thecodinglove.com/when-i-try-out-vibe-coding-with-ai



## Resources

Is AI really making software engineers 10x more productive? (Addy Osmani)
- Linkedin post: https://www.linkedin.com/posts/addyosmani_ai-programming-softwareengineering-activity-7363819659109793793-6q6_
- Full article: https://addyo.substack.com/p/the-reality-of-ai-assisted-software




## Resources

For latest updates and news on Github Copilot:
- https://www.youtube.com/@code


Claude Code - Every Claude Code Concept Explained for Normal People
- https://www.youtube.com/watch?v=ZlDnsf_DOzg
- 27:00
- march 2026


