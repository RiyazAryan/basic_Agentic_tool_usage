# Agentic AI Notebooks Collection

This folder contains a set of hands-on Jupyter notebooks focused on LangChain-based agentic AI patterns, tool calling, tool binding, and custom tool development. The examples are designed for learning and experimentation with local models such as Ollama and with LangChain tool abstractions.

## Project overview

The notebooks in this collection demonstrate several core concepts:

- Defining and registering custom tools
- Grouping tools into a toolkit
- Binding tools to a model
- Executing tool calls returned by an LLM
- Building an end-to-end agent workflow with a real API-backed use case

## Files in this folder

### 1) `custom_agentic_tool.ipynb`
This notebook focuses on creating custom LangChain tools using `@tool` and structured tool patterns. It shows how to:

- import the tool decorator
- define a tool function with proper type hints
- invoke a tool manually
- inspect the tool metadata and JSON schema
- create a more explicit tool schema using `StructuredTool` and Pydantic

### 2) `Tool_kit.ipynb`
This notebook introduces the idea of a tool toolkit. It creates a `MathToolKit` with operations such as:

- `add`
- `sub`
- `mul`
- `div`

It demonstrates how a set of tools can be grouped and exposed as a reusable toolkit.

### 3) `Tool_calling&Tool_binding.ipynb`
This notebook explores the practical process of tool calling and tool binding with a local LLM. It covers:

- creating tool functions
- attaching them to a model using `bind_tools()`
- receiving `tool_calls` from the model
- invoking the selected tool with the generated arguments
- passing tool results back into the conversation

This is one of the most important notebooks for understanding how LLM tool execution works in LangChain.

### 4) `Built-in_agentic.ipynb`
This notebook continues the agentic learning flow and focuses on practical LangChain examples for tool usage in an agentic setup. It reinforces the concepts of:

- custom tool creation
- binding tools to models
- tool execution patterns
- conversational flow with agent-like behavior

### 5) `Currency_convertor using Agents/`
This directory is a separate mini-project that applies the same ideas to a real business workflow: currency conversion. It contains:

- `cc_tool.ipynb`: notebook that binds tool-based conversion logic to an Ollama chat model
- `flow.md`: explains the sequence of tool calls and the notebook logic
- `README.md`: project-specific setup and usage instructions

This project shows how an LLM can decide when to call a conversion tool, fetch live exchange-rate data, and produce a final answer using the tool result.

## Recommended learning order

To understand the project in the intended progression, open the notebooks in this order:

1. `custom_agentic_tool.ipynb`
2. `Tool_kit.ipynb`
3. `Tool_calling&Tool_binding.ipynb`
4. `Built-in_agentic.ipynb`
5. `Currency_convertor using Agents/cc_tool.ipynb`

## Tech stack

These notebooks typically rely on:

- Python 3.10+
- LangChain
- LangChain Core
- LangChain Community
- LangGraph
- Ollama
- Pydantic
- Requests
- Optional tools such as `duckduckgo-search` and `langchain_experimental`

## Setup

Create a virtual environment and install the core packages:

```bash
python -m venv .venv
source .venv/bin/activate
pip install langchain langchain-core langchain-community langgraph pydantic requests
```

For local model usage with Ollama:

```bash
ollama pull qwen2.5:3b
```

If you want to run the currency conversion mini-project, you will also need an API key for ExchangeRate-API and set it in the environment:

```bash
export API="your-api-key"
```

## Notes

- These are learning notebooks and are best explored interactively.
- Some examples depend on a local Ollama model being running.
- The currency conversion notebook uses a live external API and therefore needs internet access and a valid API key.
- The project is meant to demonstrate the structure of agentic tool use rather than serve as a production-ready application.

## Summary

This repository is a compact collection of agentic AI experiments showing how tools can be designed, grouped, bound to an LLM, and executed to complete tasks. Together, the notebooks form a practical progression from basic tool creation to real-world tool-augmented workflows.
# basic_Agentic_tool_usage
