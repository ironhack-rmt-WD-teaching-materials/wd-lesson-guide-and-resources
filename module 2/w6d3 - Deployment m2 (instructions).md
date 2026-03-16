

# Deployment m2

<!-- 
@todo: 
- Record video "continuous deployment + branches" 
- (see slide 27)
-->


## Instructions (EN)

<!-- note: this video shows how to deploy on Netlify (rather than Vercel) -->

⛳ Deployment project 2:
- https://www.loom.com/share/915ec9d82f10412eb1e6fb4f77815cab?sid=1fc15197-4f5d-4336-8f92-e08640bd7d90


📌 Notes:

- Make sure both of you do deployment together.
- Even if your app seems to work, follow the whole video


📮 Submit project urls:

- As soon as you finish deployment, make sure both of you submit URLs in the Student Portal.
- Screenshot: https://drive.google.com/file/d/1DbOuV-w94tZqaKNWPlnx873xnf_hrsib/view?usp=sharing
- DEADLINE: today, 5pm




## Instructiones (ES)

<!-- note: this video shows how to deploy on Netlify (rather than Vercel) -->

⛳ Despliegue projecto 2:

- Video 1: https://www.loom.com/share/e87e35d239d74f5aad744c16119f98f6?sid=84660d28-f7e5-4085-b117-f16337f20861

- Video 2: https://www.loom.com/share/e51376d93d6e4245acdb688913784377?sid=7a380359-2e7f-4112-ac13-563673ca1104


📌 Notas:
- Aseguraos de que ambos seguís esta unidad y comprendéis el proceso.


📮 Enviar las URLs del proyecto:

- Tan pronto como hayas finalizado el despliegue de la app, enviad las URLs en el Student Portal (para proyectos en parejas, ambos debéis enviar las urls)

- Captura: https://drive.google.com/file/d/1DbOuV-w94tZqaKNWPlnx873xnf_hrsib/view?usp=sharing

- FECHA LÍMITE PARA ENVIAR LAS URL's: hoy a las 3pm
  - No significa que la app tenga que estar completamente lista, pero asegúrate de enviar las urls.

<!-- 
Note: 
- the recording in Spanish does not include the concept of environment variables (we actually don't need it for p2, so it can be explained in m3)
-->




## How to fix error on page reload

Fix error when user reloads the page on Netlify:

1. Create a file with the name _redirects in the public directory (so it's /public/_redirects)
2. In that file, add the following content: /* /index.html 200
  - Explanation: this will tell netlify that if there's any request to any path, it should always serve the index.html
3. Commit & push

Note: 
- Also explained in the video at 30:28
- https://www.loom.com/share/915ec9d82f10412eb1e6fb4f77815cab?t=1828&sid=c4fbdae9-5157-4aa0-8f64-db30f6d870ad

