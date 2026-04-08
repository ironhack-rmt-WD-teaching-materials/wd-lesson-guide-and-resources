

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



