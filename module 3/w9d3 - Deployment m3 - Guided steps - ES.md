
# Module 3 Deployment


Slides (draft): 
<!-- @LT: can just use the first slide with the architecture -->
- https://docs.google.com/presentation/d/19VRo2Bjae3q8b5wNCMKpEG-DrlDN_4Z3-XdHcP4CHZo/edit?usp=sharing


Backend Repo: 
<!-- alternative: fork repo from the Student Portal + check code from prev. cohort -->
- https://github.com/ironhack-demos/demo-deployment-project-3-backend

Frontend Repo: 
<!-- alternative: fork repo from the Student Portal + check code from prev. cohort -->
- https://github.com/ironhack-demos/demo-deployment-project-3-frontend


---


## Paso 0:
- En el Frontend: asegurarnos de usar variables de entorno para la URL de la API


## Paso 1 - BD
- Desplegar la Base de Datos en MongoDB Atlas


## Paso 2 - Backend
- Desplegar el Backend en Vercel
    - Importante: para la variable de entorno con la localización de la base de datos, evitar la barra al final de la url (ie. evitar el "trailing slash")


## Paso 3 - Frontend
- Desplegar el Frontend en Vercel


## Paso 4 - Fix: conexión a la Base de Datos para que funcione en Vercel
- Example commit: https://github.com/ironhack-nov2025-theDevBlinders/demo-deployment-m3-backend/commit/567b2eae38cabe18dc1bc5be5bc1dc5c71eda075
- IMPORTANTE: reemplazar `project-management-server` con el nombre de tu BBDD.
- Files changed:
    - `db/index.js`: replace all the code in that file
    - `app.js`: import connectDB + add the code to invoke it for each request


## Paso 5 - Fix: error al recargar la página en el navegador
<!-- @LT: ask students to do some research and fix that by themselves -->
<!-- Step 5 + Step 6: can be done as a class activity  -->
- See here: https://chatgpt.com/share/6970e390-d304-8003-8fdc-9b3dcf124140


## Paso 6:
- Submit URLs in the Student Portal
- Screenshot: https://drive.google.com/file/d/1un8OZoDSpSr33VmqziNPOJT8qGVpAwch/view?usp=sharing
- Deadline: today, 5pm



