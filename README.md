## ChatGPT API

This repository contains an API layer for [ChatGPT](https://chat.openai.com), powered by [chatgpt-io](https://github.com/PawanOsman/chatgpt-io). It allows users to send questions to a chatbot and receive responses in real-time.

To use this API, you will need to have a session token from ChatGPT. Set this token in the `CHATGPT_SESSION_TOKEN` environment variable. You can do this by creating a `.env` file in the root of the project and adding the line `CHATGPT_SESSION_TOKEN=YOUR_TOKEN_HERE`.

To start the API, run the following command:

```bash
npm start
```

The API will be listening on the `CHATGPT_PORT` environment variable (defaults to 3000). You can send a POST request to `/ask` with a `message` and optional `conversation_id` in the request body to ask the chatbot a question. The response will contain a `response` field with the chatbot's response.

Example request:

```bash
POST /ask
Content-Type: application/json

{
  "message": "What is your name?",
  "conversation_id": "abc123"
}
```

Example response:

```bash
Status: 200 OK
Content-Type: application/json

{
  "response": "My name is ChatGPT."
}
```

If the chatbot is not yet ready, the API will return a 503 status code and an `error` field with the message "Chatbot is not ready yet".
