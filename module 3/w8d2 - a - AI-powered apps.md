

# AI-powered apps



## Demo: integrating an AI model with your full-stack app


Follow the steps in this repo:
- https://github.com/ironhack-rmt-WD-student-materials/demo-ai-powered-apps
   <!-- @LT: remember to fork -->



Some extra notes on security:

- Prompt injection:
   - one way of mitigating that risk is to use a very strict system prompt
   - another technique would be tu use a guard model (e.g. Run a smaller model to classify: "Is this a prompt injection?")

- Setting cost limits:
   - Another useful measure is to define a rate limit for your API
   - note: this may depend on where you deploy (built-in in-memory rate limiting like express-rate-limit store, won't work well on Vercel because serverless functions are stateless).



## (Bonus) Implement AI image generation

Can be implemented with a coding agent. Example prompt:

   ```
   Implement functionality so that users can generate images with AI when they create a new recipe.
   Follow the same patterns as the existing "Generate Instructions with AI" feature.

   ## Requirements
   - Add a "Generate Image with AI" button to the new recipe form
   - On click: send a request to the backend to generate an image with AI and display a loading state.
   - When the image is ready, show a preview
   - The user can review the preview before submitting the form

   ## Reference implementation
   Mirror the existing "Generate Instructions with AI" feature:
   - Same trigger pattern (button click → loading state → result preview)
   - Same error handling and UX conventions
   ```


Example: 
- https://github.com/ironhack-feb2026-undefinedSquad/w8d2-demo-ai-powered-apps/commit/39891ff01859b85ff97f821b0cbdc7d1a2d3cb01
- Notes: 
   - the prompt can be improved to prevent prompt injection (as it is, that endpoint could be used to generate other types of images)
   - for this implementation, need to update the .env file, adding an api key for OpenAI (`OPENAI_API_KEY`)



