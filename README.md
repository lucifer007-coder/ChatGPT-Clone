# ChatGPT-Clone

## ChatGPT Clone with Streamlit
This project demonstrates building a conversational chat interface to OpenAI's GPT-3 models using Streamlit. It allows users to have a natural dialogue with AI assistants directly in the browser.

## Usage
1. Clone this repository
2. Install dependencies (see requirements.txt)
3. Run streamlit run app.py
4. Provide your OpenAI API key
5. Chat with the assistant!

## Architecture
The app uses Streamlit components like sidebar, chat input/output to build the UI.
OpenAI API is called on each user input to get responses in real-time using the stream parameter.
Conversation state is maintained using Streamlit's session state.

## Requirements

- Streamlit
- OpenAI
- An OpenAI API key

## User Interface
The UI is built entirely with Streamlit components:

Sidebar - Used to input OpenAI API key securely
Chat area - Renders conversation history as scrollable chat bubbles
Input box - Accepts user messages to pass to assistant
Response area - Displays assistant responses

## Chat Logic
Each user message is:

1. Added to the conversation state in Streamlit session
2. Sent to OpenAI API using prompt and context
3. Streamlit displays loading indicator
4. API response is parsed and displayed line-by-line for real-time effect
5. Final response is appended to conversation state
6. This allows carrying on a persistent dialogue across sessions.

## OpenAI Integration
The openai client initializes with the API key to connect to ChatGPT models.
Messages are sent to the completions endpoint with stream=True to get a generator of response chunks. This is yielded incrementally to Streamlit for a polished UX.
Error handling catches API issues to prevent crashes.

## Future Enhancements
Some ideas to improve the app:

1. User authentication
2. Theme customizeation
3. Integrate different models
4. Add parsing/summarization of long responses
5. Offline caching of responses
6. Deploy as a proper web app

This serves as a proof-of-concept for building conversational interfaces on Streamlit. With more effort it could be production-ready.
