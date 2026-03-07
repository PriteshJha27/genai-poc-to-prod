# Research Paper Chat Application

A simple yet powerful chat application. No conversation history is kept - each message is processed independently.

## Quick Start

```bash
python main.py                    # CLI mode
chainlit run app.py               # Web UI
python main.py --provider openai  # Use OpenAI
```

----

## Learning path for beginners

- Go to Branch : explore
    Read the notebook where langchain basics are explored.
- Go to Branch : feature/beginners-app
    This branch does the following:
  - a minimalistic project structuce with logging, configs, pydantic models and exceptions.
  - a chat capability with llm providers (ollama / openai)
  - a simple UI using chainlit as a chat interface & a cli based chat system.
- Go to Branch : feature/memory
  - Read the notebook explore_memory.ipynb
  - refer the docs.
  - refer /sql/init.sql with pgadmin or postgresql instance your your machine.
  - Check the updates in /src/memory/

**What initial application version (branch : beginners-app) was lacking with?**

- Query is directly sent to the llm; without actually understanding what the user needs (intent), how complex the query can be?
- Chat conversations have no history present. Only the current message context is being used.
- Application intelligence does not improve over time in this design  
- Responses will be limited to the knowledge LLM is trained on. This cannot be used as it is to answer any question which the llm has not been trained on.
- Harmful content, jailbreaking are not handled.
- No way of evaluating the responses as of now.
- No additional tools integrated with the llms.
- Cannot work as a long workflow based on just system prompts.
- Chat application is not built to support multiple users.

**These points will be the checklists that we intend to solve through out journey in this repo.**

- Query Analysis
- Memory
- Feedback Learning
- RAG
- Guardrails
- Evaluations
- Tool calling
- Workflows & Agents
- A good system design!

----

**What has been covered from the checklist:**

- [x] **Memory** — PostgreSQL-backed conversation history per user per session. History is injected as context into every LLM call.
- [x] **Multi-user support** — Login with email/password. Each user sees only their own sessions and messages.

**Still to address:**

- [ ] Query Analysis / Intent detection
- [ ] Feedback Learning
- [ ] RAG
- [ ] Guardrails
- [ ] Evaluations
- [ ] Tool calling
- [ ] Workflows
- [ ] Agents

----

## License

See LICENSE file for details.