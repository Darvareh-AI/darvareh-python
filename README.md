# Darvareh Python

Python examples and integration guides for connecting applications to the Darvareh AI Infrastructure Platform.

Darvareh provides a unified, OpenAI-compatible API that enables developers to access leading AI models through a single interface.

## 🚀 Overview

With Darvareh, developers can build AI-powered applications using:

- Text generation models
- Image generation models
- Audio models
- Video models
- Reasoning models
- AI Agents and RAG applications

without managing multiple providers, APIs, and integrations.

## 🔗 API Endpoint

Darvareh provides an OpenAI-compatible API endpoint:
https://api.darvareh.ir/v1


You can use existing OpenAI-compatible SDKs and frameworks with Darvareh.

---

# Quick Start

## Installation

Install the OpenAI Python SDK:

```bash
pip install openai

## Basic Chat Completion

from openai import OpenAI

client = OpenAI(
    api_key="YOUR_DARVAREH_API_KEY",
    base_url="https://api.darvareh.ir/v1"
)

response = client.chat.completions.create(
    model="MODEL_NAME",
    messages=[
        {
            "role": "user",
            "content": "Explain artificial intelligence in simple terms."
        }
    ]
)

print(response.choices[0].message.content)


## Streaming Responses
Darvareh supports streaming responses through the OpenAI-compatible API.

from openai import OpenAI

client = OpenAI(
    api_key="YOUR_DARVAREH_API_KEY",
    base_url="https://api.darvareh.ir/v1"
)

stream = client.chat.completions.create(
    model="MODEL_NAME",
    messages=[
        {
            "role": "user",
            "content": "Write a short story about AI."
        }
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="")

## Using AI Models
Darvareh provides access to multiple AI model providers through one unified API.

response = client.chat.completions.create(
    model="MODEL_NAME",
    messages=[
        {
            "role": "user",
            "content": "Analyze this text."
        }
    ]
)

print(response.choices[0].message.content)

## Replace:
MODEL_NAME
with the model available in your Darvareh dashboard.

## Image Generation
Example:

from openai import OpenAI

client = OpenAI(
    api_key="YOUR_DARVAREH_API_KEY",
    base_url="https://api.darvareh.ir/v1"
)

image = client.images.generate(
    model="IMAGE_MODEL",
    prompt="A futuristic AI infrastructure network"
)

print(image.data[0].url)

## LangChain Integration
Darvareh works with OpenAI-compatible frameworks such as LangChain.

from langchain_openai import ChatOpenAI

llm = ChatOpenAI(
    model="MODEL_NAME",
    openai_api_key="YOUR_DARVAREH_API_KEY",
    openai_api_base="https://api.darvareh.ir/v1"
)

response = llm.invoke(
    "Explain RAG architecture."
)

print(response.content)


## Use Cases
Build AI applications including:

AI chat applications
Customer support assistants
RAG systems
AI Agents
Content generation platforms
Enterprise AI applications
Developer tools
Features

✅ OpenAI-compatible API
✅ Access multiple AI models through one interface
✅ Unified authentication and billing
✅ Intelligent model routing
✅ Automatic fallback
✅ Usage monitoring
✅ Cost optimization

## Documentation

Documentation:
https://hub.darvareh.ir

Website:
https://darvareh.ir

## About Darvareh
Darvareh is an AI Infrastructure Platform that connects software applications to the AI ecosystem through a unified API.
Our mission is to simplify AI adoption by making advanced AI capabilities accessible to developers and businesses.

## License

This repository contains examples and integration guides provided by Darvareh.
