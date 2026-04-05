# 🧠 AI Study Buddy (Cloudflare AI Assignment)

This is a full-stack, AI-powered study assistant built on Cloudflare's developer platform. It remembers the context of your conversation to help you study effectively.

## 🚀 Live Demo
[Click here to chat with the AI Study Buddy](https://cf-ai-studybot.gunasheelajo13.workers.dev)

## 🛠️ Architecture & Components
This project fulfills all the requirements of the Cloudflare AI App assignment:
* **LLM:** Cloudflare Workers AI using `@cf/meta/llama-3.3-70b-instruct-fp8-fast`.
* **Workflow / Coordination:** Cloudflare Workers handles the API routing, CORS, and orchestrates the connection between the frontend, the database, and the AI model.
* **User Input:** A vanilla HTML/JS chat interface served directly from the Worker (using the `public` directory feature).
* **Memory / State:** Cloudflare KV (Key-Value) store is used to save conversation history based on a unique Session ID, allowing the AI to remember previous context.

## 💻 How to run locally
1. Clone the repository.
2. Run `npm install` to install dependencies.
3. Run `npx wrangler kv namespace create CHAT_HISTORY` to create your local database. Update `wrangler.jsonc` with the new ID.
4. Run `npm run dev` to start the local server.
