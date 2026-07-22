# Notes

## 1. What is AI (Artificial Intelligence)?

Artificial Intelligence (AI) is the broad field of computer science that focuses on creating machines capable of performing tasks that normally require human intelligence.

### Examples

- Voice assistants (Siri, Alexa)
- Recommendation systems (Netflix, YouTube)
- Face recognition
- Self-driving cars
- Chatbots

> **Think of AI as the biggest umbrella.**

---

## 2. What is Generative AI (GenAI)?

Generative AI (GenAI) is a type of AI that creates new content instead of only analyzing data.

It can generate:

- Text
- Images
- Videos
- Music
- Code

### Examples

- ChatGPT → Text
- GitHub Copilot → Code
- DALL·E → Images

> **AI analyzes and predicts. GenAI creates.**

---

## 3. What is an LLM (Large Language Model)?

A Large Language Model (LLM) is a type of Generative AI trained on massive amounts of text to understand and generate human language.

An LLM can:

- Answer questions
- Write code
- Summarize text
- Translate languages
- Hold conversations

### Popular LLMs

- GPT (OpenAI)
- Gemini (Google)
- Claude (Anthropic)
- Llama (Meta)

> **An LLM is the "brain" that understands and generates text.**

---

## 4. What is GPT?

GPT stands for **Generative Pre-trained Transformer**.

- **Generative** → Creates text.
- **Pre-trained** → Trained on a huge amount of text before use.
- **Transformer** → The neural network architecture used to understand language.

GPT is an LLM developed by **OpenAI**.

---

## 5. What is ChatGPT?

ChatGPT is an AI-powered chat application developed by OpenAI that lets users interact with GPT models through a conversational interface.

ChatGPT includes features like:

- Chat interface
- Conversation history
- File uploads
- Voice mode
- Image generation (on supported plans)

> **GPT is the AI model. ChatGPT is the application that uses GPT.**

---

## 6. What is a Knowledge Cutoff?

A **knowledge cutoff** is the point in time up to which an AI model was trained on information.

This means the model only has built-in knowledge of events, facts, and data available **up to its training cutoff**. It does not automatically know about new events that happened afterward.

### Example

If a model has a knowledge cutoff of **June 2024**, it won't know about events that happened after June 2024 unless it can access the internet or is provided with that information.

### Why is this important?

Knowing the knowledge cutoff helps you understand:

- Why the AI may not know recent news.
- Why it may ask to search the web for up-to-date information.
- When you should verify recent or time-sensitive information.

> **A knowledge cutoff is the "last date" of the AI model's built-in knowledge.**

---

## 7. Is ChatGPT an AI or an LLM?

Neither exactly.

- **GPT** → The LLM (the AI model).
- **ChatGPT** → The AI application built on top of the GPT model.

When building a ChatGPT clone, you are building the **application**, not the LLM itself.

---

## 8. How does ChatGPT work?

A ChatGPT application is made up of three main parts:

1. **Frontend (Client)**
   - The user interface where users type messages and view responses.
   - Usually built with React, Next.js, Vue, or similar frameworks.

2. **Backend (Server)**
   - Receives the user's message.
   - Sends the message to an AI model through an API.
   - Receives the AI's response and sends it back to the frontend.
   - Often built with Node.js, Express, FastAPI, etc.

3. **AI Model**
   - The "brain" that understands the prompt and generates responses.
   - Examples include OpenAI GPT models, Gemini, Claude, Llama, and others.

Flow:

User → Frontend → Backend → AI Model → Backend → Frontend → User

---

# 9. Frontend vs Backend

## Frontend

The part of the application users see and interact with.

Examples:

- Chat interface
- Input box
- Send button
- Displaying messages

## Backend

The part users don't see.

Responsibilities:

- Receives user messages
- Calls the AI API
- Sends the response back
- Protects API keys
- Handles authentication and database operations

---

# 10. Client-Server Architecture

A ChatGPT application follows the Client-Server model.

```text
Client (Frontend)
        ↓
Backend (Server)
        ↓
AI API
        ↓
Backend
        ↓
Client
```

The **client** sends requests, and the **server** processes them and returns responses.

---

# 11. What is an API?

An **API (Application Programming Interface)** is a bridge that allows two applications to communicate with each other.

Instead of accessing a service directly, your application sends a **request** to an API, and the API returns a **response**.

### Example

When you send a message in ChatGPT:

```text
Your App → AI API → AI Response → Your App
```

> **Think of an API as a waiter in a restaurant.** You place an order (request), the waiter delivers it to the kitchen (server), and brings your food back (response).

---

# 12. What is an AI API?

An **AI API** allows developers to use powerful AI models without building or training one themselves.

Your application sends a prompt to the AI API, and the AI returns a generated response.

### Popular AI APIs

- OpenAI
- Google Gemini
- Anthropic Claude

> **In this project, you'll build the application, while the AI API provides the intelligence.**

---

# 13. What is JSON?

**JSON (JavaScript Object Notation)** is a lightweight format used to exchange data between applications.

Example:

```json
{
  "role": "user",
  "message": "Hello"
}
```

Almost every API sends and receives data in JSON format.

---

# 14. Request & Response Cycle

Whenever a user sends a message, the following process happens:

```text
User types a message
        ↓
Frontend sends request
        ↓
Backend receives request
        ↓
Backend calls AI API
        ↓
AI generates response
        ↓
Backend sends response
        ↓
Frontend displays response
```

This complete process is called the **Request-Response Cycle**.

---

# 15. What is a Prompt?

A **prompt** is the instruction or question you give to an AI model.

Examples:

- Explain React.
- Write a Python program.
- Summarize this article.

The quality of the prompt often affects the quality of the AI's response.

---

## 16. What is Prompt Engineering?

**Prompt Engineering** is the practice of writing clear and effective prompts to get better responses from an AI model.

A well-written prompt usually produces more accurate, useful, and relevant results than a vague one.

### Example

❌ Poor Prompt

```text
Tell me about JavaScript.
```

✅ Better Prompt

```text
Explain JavaScript closures in simple terms with a real-world example suitable for a beginner.
```

### Tips for Writing Good Prompts

- Be clear and specific.
- Provide enough context.
- Mention the desired format (list, table, code, etc.).
- Specify the audience (beginner, expert, etc.).

> **Better prompts lead to better AI responses.**

---

# 17. What are Tokens?

AI models don't read text word by word. Instead, they process **tokens**, which are small pieces of text.

Examples:

```text
"Hello, world!"
```

might be split into tokens like:

```text
Hello
,
world
!
```

API limits and pricing are usually based on the number of tokens processed.

---

# 18. Chat History (Conversation Context)

AI models don't permanently remember your conversation.

To maintain context, your application sends previous messages along with the latest one.

Example:

```text
User: Who is Elon Musk?
AI: ...

User: Where was he born?
```

The AI understands that **"he"** refers to Elon Musk because the earlier messages are included in the request.

---

# 19. Streaming Responses

Instead of waiting for the complete response, the AI can send it **piece by piece** as it is generated.

Example:

```text
H
He
Hel
Hello
Hello!
```

This makes the application feel faster and more responsive.

---

# 20. What is Markdown?

**Markdown** is a lightweight formatting language used to style text.

Examples:

````md
# Heading

**Bold Text**

- List Item

```js
console.log("Hello");
```
````

```

AI responses often use Markdown so your application can display formatted text, code blocks, headings, and lists.

```

---

## 21. What is CORS?

**CORS (Cross-Origin Resource Sharing)** is a browser security feature that controls whether a frontend can make requests to a backend hosted on a different origin (domain, port, or protocol).

For example:

```text
Frontend → http://localhost:5173
Backend  → http://localhost:3000
```

Since the frontend and backend use different ports, the browser treats them as different origins and blocks the request unless the backend explicitly allows it.

### Why do we need CORS?

CORS helps protect users from malicious websites making unauthorized requests on their behalf.

### How is it enabled?

In an Express backend, you can enable CORS using the `cors` package:

```js
import cors from "cors";

app.use(cors());
```

> **Without CORS, your frontend may not be able to communicate with your backend during development.**

## 22. What is the Responses API?

The **Responses API** is OpenAI's latest API for interacting with AI models. It allows your application to send a prompt to a model and receive an AI-generated response.

Unlike the older Chat Completions API, the Responses API provides a more flexible and unified way to work with text, images, tools, and other AI capabilities.

### Example

```js
const response = await client.responses.create({
  model: "gpt-4.1",
  input: "Explain JavaScript in simple terms."
});
```

The AI then generates a response based on the input.

### Why use the Responses API?

- Simpler and more flexible.
- Supports the latest OpenAI models.
- Designed for future AI features.
- Recommended by OpenAI for new projects.

> **The Responses API is the modern way to interact with OpenAI models.**

---

## 23. What is the Chat Completions API?

The **Chat Completions API** is OpenAI's older API used to generate responses in a conversation.

Instead of sending a single input, you send a list of messages with different roles (`system`, `user`, and `assistant`).

### Example

```js
const completion = await client.chat.completions.create({
  model: "gpt-4.1",
  messages: [
    {
      role: "user",
      content: "Explain JavaScript."
    }
  ]
});
```

The AI generates the next assistant message based on the conversation.

### Note

Many existing tutorials still use the Chat Completions API, but OpenAI recommends using the **Responses API** for new applications.

> **The Chat Completions API generates the next message in a conversation.**