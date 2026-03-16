

# Practice: technical interviews


Slides:

- Technical Interview Prep (EN):
    - https://docs.google.com/presentation/d/1HZzVFFIkaymfT7Wwg2itr3jFSY0NrlRWCNxcG3KVA4w/edit?usp=sharing

- Preparación para entrevistas técnicas (ES): 
    - https://docs.google.com/presentation/d/1V3OLq80lOE_j4fOwkOUCyi39eRpCv1wIpkgEZG-f3TQ/edit?usp=sharing




## Technical Interview - JavaScript I


Exercise 1 - Throwing Darts:
- Instructions (codewars): https://www.codewars.com/kata/525dfedb5b62f6954d000006
- Notes:
    - Solve directly on codewars
    - It's not particularly difficult, it requires some familiarity to JS & paying attention to details (instructions, edge cases, etc)
- Some possible solutions: 
    - private repo: https://github.com/luisjunco/katas-solutions-and-explanations/tree/main/codewars/9%20-%20(6kyu)%20Throwing%20Darts
    - stackblitz: https://stackblitz.com/edit/vitejs-vite-88ntpsvu?file=src%2Fmain.js


Exercise 2 - The rice and chessboard problem:
- Instructions: https://gist.github.com/luisjunco/dcec6ca49602eaf7b023947505fea6c6
- Notes: 
    - Much easier to solve if you think in binary
    - Based on this codewars kata: https://www.codewars.com/kata/5b0d67c1cb35dfa10b0022c7/
- Some possible solutions: 
    - private repo: https://github.com/luisjunco/katas-solutions-and-explanations/tree/main/codewars/20%20-%20(7kyu)%20The%20wheat-rice%20and%20chessboard%20problem
    - stackblitz: https://stackblitz.com/edit/vitejs-vite-szt9vlpv?file=src%2Fmain.js





Takeaways:
- Read instructions carefully.
- If in doubt, ask.
- In live coding sessions, explain what you're trying to do.



## Technical Interview - React I


Instructions: 
- https://gist.github.com/luisjunco/01fd5845f81460388040962b27062739

Q:
- If the API returns an empty array, display a message (`Sorry, no products to display`)
- Implement the API request with fetch instead of axios
- SearchBar





## Technical Interview - JavaScript II [1.5h]

<!-- 

@LT:
- 1 day in advance, send a formal invitation to the candidate. 
- In the invitation, mention that we use TDD.

---

Technical Interview Invitation – [Company Name]

Hi [CANDIDATE_NAME],

We'd love to invite you for a technical coding interview with [COMPANY_NAME].

Our team works extensively with JavaScript, React, and Express. For unit testing, we use Jest.

This session will focus on assessing your coding skills and problem-solving abilities.
It is expected to last about an hour.

Do you have availability for [DAY_OF_THE_WEEK] at 9am ?

Best,
[YOUR_NAME], 
[YOUR_ROLE],


-->


Task:
- Implement `String.prototype.indexOf()` without using native functions (can use only use `str.charAt()`).
- Bonus: Testing / TDD

How:
- Share with the candidate a pdf file with the instructions
- pdf: https://github.com/luisjunco/technical-interviews/
- Time: 1h

Solution:
- https://github.com/luisjunco/technical-interviews/blob/main/examples-i-have-done/2018.05%20-%20Grandvoyage/solution-1.js

Example of unit tests + setup with Jest:
- https://github.com/luisjunco/unit-testing-with-jest-example


Evaluation criteria:

- Essential criteria:
    - The code works and does what was requested
    - Presence of unit tests

- Auxiliary criteria:
    - Use of language mechanisms appropriate for the problem (break, continue, labeled loops)
    - Adherence to a common "coding standard" (consistent indentation, follow naming conventions, etc)
    - Proper naming (giving variables, functions, and other identifiers clear and descriptive names).
    - Use of a unit testing framework
    - No abandoned debugging code


Takeaways:
- You may not know things/technologies, and that's ok.
- Before a technical interview, try to get familiar with the technologies asked for that particular role.
- Read instructions carefully.
- Follow coding standards & good practices.
- Even if you're not able to solve all the tasks, show interest in learning and growing.
- If the test has a deadline, make sure to stick to it & submit before the deadline.




## Technical Interview - React II

<!--

@LT: 
- Explain that exercise is more like a take home, longer assignment.
- If done in class, start by displaying a list of books + focus on the core functionality

-->

Instructions: https://github.com/ironhack-rmt-WD-teaching-materials/technical-interview-react-ii


Update:
- March25, the student that volunteered (Oggy) had a real interview just two days later.
- He was asked to implement very similar functionality (render a list of things coming from an external API, searchbar, ...).
- https://drive.google.com/file/d/1kRfWS7ztv9lJoAjBFq5jBCuhUpkvS69X/view?usp=drive_link




## Alternative React Interview

- Initial code: https://github.com/ironhack-rmt-WD-teaching-materials/technical-interview-react
- Demo: https://technical-interview-react-demo.netlify.app/

Q:
- If no albums to display, display a message (`Sorry, no albums to display`)
- SearchBar
- In case data was coming from an API, how would you implement a loader/spinner.
- Implement native toast (e.g. after creating an album) / How would you implement it.


## Resources

Mock Technical Interview - Javascript Developer Junior Level (1h45m):
- https://www.youtube.com/watch?v=h4i4kjwncoU&t=10s
- Includes verbal questions (e.g. what's a rest api, explain login process)
- Includes coding challenges (palindrome, flatten an array, etc)
