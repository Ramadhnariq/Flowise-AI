# Flowise AI — RAG Chatbot

A Retrieval-Augmented Generation (RAG) chatbot project built with **Flowise**, Docker, Redis, and Qdrant. This project explores how large language models can retrieve relevant information from a knowledge base and use it to generate contextual responses.

## Overview

This project extends a Flowise deployment with additional services to support conversational AI workflows, vector search, and persistent data storage.

The system is designed to experiment with different LLM providers and connect AI workflows with external APIs.

## Features

- **RAG pipeline** — retrieve relevant context from a knowledge base before generating responses.
- **Visual AI workflows** — build and manage chatbot pipelines using Flowise.
- **Vector search** — use Qdrant to store and retrieve vector embeddings.
- **Conversational memory** — integrate Redis into the chatbot infrastructure.
- **Multiple LLM options** — experiment with supported models and providers, depending on the configured workflow.
- **API integration** — explore connections between AI workflows and external APIs using Postman for testing.

## Tech Stack

| Technology | Purpose |
|---|---|
| Flowise | Visual builder for LLM and RAG workflows |
| Docker Compose | Run and manage project services |
| Redis | Memory and supporting data services |
| Qdrant | Vector database for semantic retrieval |
| LLM providers | Generate responses based on the configured workflow |
| Embeddings | Convert text into vectors for retrieval |
| Postman | Test and inspect API requests |

## Architecture

```text
User Question
     |
     v
Flowise Chatflow
     |
     v
Embedding & Retrieval
     |
     v
Qdrant Vector Database
     |
     v
Relevant Context + User Question
     |
     v
Configured Language Model
     |
     v
Generated Response
     |
     v
User
```

Redis supports the configured memory or supporting services. The exact memory flow depends on how Redis is connected within the Flowise workflow.

## Getting Started

### Prerequisites

- Docker Desktop
- Git
- Configured LLM provider and credentials, if required by your workflow

### Run with Docker Compose

1. Clone this repository.

   ```bash
   git clone https://github.com/Ramadhnariq/Flowise-AI.git
   cd Flowise-AI
   ```

2. Open the Docker configuration directory.

   ```bash
   cd docker
   ```

3. Copy `.env.example` to `.env`, if the example file is available.

4. Configure the required environment variables.

5. Start the services.

   ```bash
   docker compose up -d
   ```

6. Open the Flowise interface using the port configured in your environment.

### Stop the services

```bash
docker compose down
```

## Configuration

Before running the project, configure the required settings for:

- Flowise server
- LLM provider and API credentials
- Embedding model
- Qdrant connection and collection
- Redis connection and memory configuration
- External API integrations

Never commit `.env` files, API keys, passwords, or other credentials to the repository.

## Project Status

This project is under development. Features and configuration details may change as the RAG workflow and integrations are refined.

## Acknowledgements

This project builds on [Flowise](https://github.com/FlowiseAI/Flowise). Refer to the upstream project and its license for the original source code and licensing terms.

