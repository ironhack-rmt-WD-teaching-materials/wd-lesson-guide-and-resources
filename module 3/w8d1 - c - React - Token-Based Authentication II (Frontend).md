

# React - Token-Based Authentication II (Frontend)


<!-- 

Methodology:
- self-guided 

-->


New topics introduced in this unit:

- You will have 2 apps running (front & back)
  - Express API (Ironlauncher) - `npm run dev` (port 5xxx)
  - React App (Vite) - `npm run dev` (port 3xxx)
  <!-- @LT: show them (ie. run both apps on my computer) -->
  - naming:
    - frontend / client / react app
    - backend / server / express app

- (context API)
  <!-- - see code in the Student Portal -->
- local storage for the token
  <!-- 
    - see MDN + make quick demo on the dev tools console
    - mention: localStorage operates under the same-origin policy (protocol, port, domain)
  -->
- send token in headers of http request with axios ("Set Request Headers")
  <!-- - see code in the Student Portal -->
- Private Pages ("Private Pages")
  <!-- - see code in the Student Portal -->


Diagram jwt: https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/m3/token-auth/jwt-authentication-flow-1.png



Sections in the student portal:
- Auth Context
  > NOTE: refresh context API (provider + consumer)
- Sign Up Page
  - Create the Signup Page (component with form, w/o sending request)
  - Send a Sign Up Request
    > NOTE: if axios request fails, error message is available in `error.response.data.message`
    > NOTE 2: make sure we're consistent when we send errors from the API (in the Student Portal we have the property "message" + ironlauncher sends them in the property "errorMessage")
  - Render the SignupPage Component
- Login Page
  - Create the Login Page
  - Send a Login Request with axios
- Set up the Authentication Logic
  - Save the Token in the localStorage
    > EXPLAIN: localStorage
    - mdn: https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage
    > NOTE: we could also store the token in state instead of localStorage (but if user refreshes the page it will not be logged in)
  - Verify the Token upon Login
    > EXPLANATION:
      - token now stored in local storage
      - we may still want to check against backend (e.g. if the app reloads)
  - Verify the Token upon Initial App Load
    - if the user reloads the page and there's a token in local storage, we want to  "login the user"
  - Remove the Token on Logout
  - Update the Logout button in the Navbar
- Custom route components
  - Private Pages
  - Anonymous Pages (available only if you are NOT logged in)
  - Establish Public and Private Pages
- (Extra) Do not display "delete" button if user not logged in  
  - (conditional rendering)
- Set Request Headers
  (for all requests to the api, we need to send JWT in the header)



## Extra challenges and improvements:
- After signup, automatically login the user
- Add a component library

