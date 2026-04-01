


## (Intro) Create a React App on Stackblitz/CodeSandbox [15m]

- See main.jsx:
  - import "React"
  - root.render()
- See App.js (component)
  - JSX: describe the UI.



## (Extra) ES6 modules [30m]

Slides: https://docs.google.com/presentation/d/1SqJP7b9cQ9UpvTmfVpdojcFXjsTL0g1HH_cn0sq3SLs/edit?usp=sharing




## (Extra) Intro to NPM [30m]

- (skip) see: "Node - Introduction.md"
- (skip) Watch: "What is npm?" (3min.)
  - https://www.youtube.com/watch?v=pa4dc480Apo

  <!--
  @todo: 

  Create a brief self-guided unit about NPM [30m.]
  - intro to npm
  - creating an npm project
  - installing a package (e.g. cowsay)
  - package.json 
  - explain package.json scripts ? (it can also be done later)

  Note: it can be linked to the concepts of ES6 modules
  e.g.:
  - students fork an initial repo with 2 files
  - explain ES6 modules
  - explain NPM & install one dependency

  -->


Demo: cowsay:
- mkdir module2
- cd module2
- mkdir npm-demo
- cd npm-demo
- touch index.js
- code -r .
- console.log("hello")
- node index.js
- npm init --yes
- npm install cowsay
- add code to index.js
  - see "Usage in the browser"
  ```js
  import { say } from 'cowsay';
  console.log(say({ text: 'hello world' }));
  ```
- fix: "cannot use import statement outside a module"
  - package.json:
    - add `"type": "module",`



## IMPORTANT: recommendations to prevents attacks from npm packages (supply chain attacks)


1. Run this command to disable lifecycle scripts:
  - `npm config set ignore-scripts true`
  
2. Consider pinning to exact versions in package.json (e.g., use `1.4.0` instead of `^1.4.0`)


Note: since npm v.11, there's also a new configuration `min-release-age` that allows you delay installs of newly published versions (this would give time for the community to spot malicious releases):
- https://docs.npmjs.com/cli/v11/using-npm/config#min-release-age
- It's relatively recent, I've tried and, at least for me, it didn't work.


<!--

Example of these types of hacks:

- Axios just got pwnd:
  - https://www.youtube.com/watch?v=5xWSezMFweE

- Me hackearon (midudev, Spanish):
  - https://www.youtube.com/watch?v=ikdCG4goKIE 

In both cases, disabling lifecycle scripts would have prevented the problem.

-->



