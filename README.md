# Tach Agent — browser chat client

This repository contains a single-page web client for a remote assistant API. Despite the repository name, the code here is a browser application, which comunicates with the CHAT Ai Agent ,allowing you to talk and interact with the CHAT Ai agent.

## Features in the client

- Send text prompts in **Fast** or **Deep** mode and display the returned response as Markdown.
- Record microphone audio in the browser and send it to the audio endpoint; display returned text and play audio when the response includes an audio URL.
- Start a new client session, with a newly generated chat ID, and use the responsive sidebar on narrow screens.

The current frontend points to `https://manxaneletso-chat-dev-space.hf.space`. Its text and audio requests use `/api/chat/text` and `/api/chat/audio`. The server is external to this repository, so its availability and behavior are not guaranteed by this codebase.

## Run locally

The page has no build step. It loads Tailwind CSS, Marked, and Font Awesome from CDNs, so an internet connection is needed for those assets and the remote API.

```bash
git clone https://github.com/Atty3333/Chat-Personal-Ai-assistant-agent.git
cd Chat-Personal-Ai-assistant-agent
python3 -m http.server 8000
```

Open `http://localhost:8000`. Microphone recording requires browser permission and a secure context such as localhost or HTTPS. To use a different API, update `API_BASE` in the inline script in `index.html` and provide the expected endpoints and response fields (`response`, and optionally `text_response` and `audio_url`).

## Current limitations

- The repository contains no backend source, model configuration, Android code, or chat-history retrieval. The browser keeps the visible transcript in the current page; starting a new session clears it and rotates the client chat ID.
- The button titled “Live Audio WebSocket (Pending)” currently changes the interface animation only; the code does not open a WebSocket connection.
