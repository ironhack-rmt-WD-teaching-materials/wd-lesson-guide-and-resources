

# React - Integrating React App with backend



<!-- 

status: draft


API_URL: 
- create config/api.js
- declare as const an export/import
- (don't introduce environment variables yet)


Note:
- day is heavy (we see a lot of code).
- try to make it as light & fast as possible

@todo: 
- create quick exercise (e.g. bug hunt with functionality for "Project details page")


repo:
- follow repo from prev. cohort

-->


- navigate to module2 directory
- `npm create vite@latest react-project-management -- --template react`
- 'Install with npm and start now?': select 'no'
- cd react-project-management
- code -r .
- npm install
- npm run dev

To run on a specific port:
- npm run dev -- --port=3002


<hr />



Intro: 
- explain goal + show API endpoints (see Student Portal "Endpoints")
- provide a list of milestones to follow (for each milestone, discuss how to implement it)

Roadmap:
- [ ] Initial setup
      - create app
      - setup repo + upload to github
      - cleanup initial code
      - copy index.css (get `index.css` from the Student Portal)
      - create `components/Navbar`, `pages/HomePage` and `pages/ProjectListPage`
      - setup routing
- [ ] List of projects
- [ ] Create new projects
- [ ] Navbar
- [ ] Project details page
- [ ] Edit projects
- [ ] Delete projects
- [ ] Create new tasks
      - display list of tasks
      - functionality to create tasks
- [ ] (skip) Extracting Components (project card + task card)


Extra:
- show: keep constants in a specific file (e.g. config/api.js)
- show: vs code source control
- show: loader (e.g. https://cssloaders.github.io/)
- mention: toast


  ```jsx
    if (projects === null) {
      return <div className="loader"></div>;
    }

    // or...
    if (projects === null) {
      return <Loader />;
    }
  ```
- show: responsive list of items


Steps (in more detail):
- [ ] Getting Started (initial setup)
- [ ] React Router Setup
- [ ] Project Management API (explains API and available endpoints)
- [ ] Project List Page
      - ProjectListPage.jsx
      - path="/projects"
- [ ] Create Project Page
  - CreateProjectPage.jsx
  - exact path="/projects/create"
  - form
  - POST /projects
- [ ] Project Details Page
  - ProjectDetailsPage.jsx
  - path="/projects/:projectId" 
- [ ] Edit Project Page (form must be pre-populated)
  - EditProjectPage.jsx
  - path="/projects/edit/:projectId"
  - form (pre-populated)
  - PUT /projects/:id
- [ ] Delete the Project 
  - modify EditProjectPage.jsx (add function "deleteProject" + button)
- [ ] Add Task Form
  - to display tasks:
    - `?_embed=tasks`
  - create component `<AddTask>` (form + controlled component)
  - render it in `<ProjectDetailsPage>`
  - modify `AddTask.jsx`:
    - on submit: POST /tasks
      - Note: make sure to pass projectId as a number (passing it as a string will not work)
      - Example: https://github.com/ironhack-fulltime-degenerates-oct2023/codealong-integrating-react-app/blob/86c78481f9c62bdde49ec1eca5f475af1f9d886b/src/components/AddTask.jsx#L15
    - after a task is created, refresh project details: `props.refreshProject();`

- [ ] (skip) Extracting Components (project card + task card)



<hr />


## Do I need useEffect ?

When do you need useEffect ?
- 👉 I want to send an API request as soon as the component is mounted → useEffect()
- 👉 I'm not in a rush... I will send the API request when the user submits a form or clicks on a button → you don't need useEffect()

<!-- 

(ES)

Cuándo usar useEffect...
- 👉 Quiero enviar la petición a la API tan pronto como se muestre el componente → useEffect()
- 👉 No tengo prisa... enviaré la petición a la API cuando el usuario envie el formulario o haga click en un botón → no necesitas useEffect()

-->


## Axios common methods:

- axios.get(url)
- axios.post(url, data)
- axios.put(url, data)
- axios.delete(url)
