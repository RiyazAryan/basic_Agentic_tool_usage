# Agentic AI Notebooks Collection

This folder contains a collection of Jupyter notebooks focused on LangChain-based agentic AI patterns, custom tool development, tool binding, and tool execution. The goal is to help you learn how an LLM can use tools to complete real tasks.

## Step 1: Understand the learning goal

This project demonstrates the core ideas behind agentic AI:

- creating tools
- registering them properly
- grouping them into toolkits
- binding tools to a language model
- executing tool calls returned by the model
- using tool results to continue the conversation

In short, these notebooks show how an LLM can go beyond text generation and actually act with tools.

## Step 2: Explore the custom tool examples

### `custom_agentic_tool.ipynb`
This notebook focuses on creating custom LangChain tools using `@tool` and structured tool patterns. It covers:

- importing the tool decorator
- writing a function with typed inputs and return values
- invoking the tool manually
- checking tool metadata and schema
- defining a Pydantic-based structured tool schema

This is the starting point for learning how tools are declared in LangChain.

## Step 3: Learn how toolkits work

### `Tool_kit.ipynb`
This notebook introduces a reusable toolkit design. It creates a `MathToolKit` with several operations:

- `add`
- `sub`
- `mul`
- `div`

It demonstrates how multiple tools can be organized and managed as a single collection, which is useful when building an agent with multiple capabilities.

## Step 4: Understand tool calling and tool binding

### `Tool_calling&Tool_binding.ipynb`
This notebook is the core example for tool calling and tool binding. It demonstrates:

- defining functions as tools
- binding tools to a local LLM using `bind_tools()`
- receiving `tool_calls` from the model
- passing the generated arguments into the chosen tool
- executing the tool and injecting the result back into the model conversation

This notebook helps explain how the LLM decides which tool to use and how the result flows back into the final answer.

## Step 5: Practice the full agentic workflow

### `Built-in_agentic.ipynb`
This notebook reinforces the earlier concepts in a more complete agentic setup. It shows how to:

- create custom tools
- bind tools to a model
- invoke them in a conversational flow
- continue the interaction after tool execution

This notebook connects the theory from the earlier steps into a more realistic interactive pattern.

## Step 6: Build a real-world example with API integration

### `Currency_convertor using Agents/`
This mini-project applies the same tool concept to a real use case: currency conversion. It includes:

- `cc_tool.ipynb`: a notebook that binds conversion tools to a local Ollama chat model
- `flow.md`: a detailed explanation of the workflow and execution sequence
- `README.md`: project setup and usage instructions

The notebook shows how an LLM can decide to call a conversion tool, fetch live exchange-rate data, and use that result to answer the user.

## Step 7: Install and run the project

### Environment setup

Create a virtual environment and install the required packages:

```bash
python -m venv .venv
source .venv/bin/activate
pip install langchain langchain-core langchain-community langgraph pydantic requests
```

For local LLM usage with Ollama:

```bash
ollama pull qwen2.5:3b
```

For the currency conversion example, set your API key:

```bash
export API="your-api-key"
```

Then open the notebooks in VS Code or Jupyter and run the cells from top to bottom.

## Step 8: Recommended learning order

To follow the project in a natural progression, use this order:

1. `custom_agentic_tool.ipynb`
2. `Tool_kit.ipynb`
3. `Tool_calling&Tool_binding.ipynb`
4. `Built-in_agentic.ipynb`
5. `Currency_convertor using Agents/cc_tool.ipynb`

This order moves from basic tool creation to toolkit design, then to tool binding, and finally to a practical API-backed workflow.

## Step 9: Tech stack

These notebooks typically rely on:

- Python 3.10+
- LangChain
- LangChain Core
- LangChain Community
- LangGraph
- Ollama
- Pydantic
- Requests
- Optional packages like `duckduckgo-search` and `langchain_experimental`

## Step 10: Notes

- These are learning notebooks designed for hands-on experimentation.
- Some examples depend on Ollama being installed and running locally.
- The currency conversion notebook requires internet access and a valid API key.
- The examples are educational and show the structure of agentic tool usage rather than being production-ready software.

## Final summary

This repository is a practical learning collection for agentic AI. It begins with simple custom tools, moves to toolkits, then covers tool binding and tool execution with a local LLM, and finally ends with a live currency-conversion example. Together, these notebooks provide a clear workflow for understanding how LLMs can use tools to complete meaningful tasks.

# basic_Agentic_tool_usage
