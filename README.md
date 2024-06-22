# Local LLM Setup and Interaction

This project provides a hands-on experience with setting up and interacting with local Large Language Models (LLMs) using the Ollama framework on macOS. The primary goal is to download, install, and demonstrate the functionality of two different LLMs on a local machine: Llama3 and Gemma.

## Purpose

The purpose of this project is to:
1. **Learn to set up LLMs on a local machine**: Gain practical experience in downloading, installing, and configuring LLMs.
2. **Interact with LLMs using API**: Understand how to interact with LLMs via API calls.
3. **Compare the performance of different models**: By running and interacting with Llama3 and Gemma, compare their responses to similar prompts.

## Environment Setup

### Prerequisites

Ensure you have the following installed:
- macOS
- At least 8 GB of RAM

### Installing Dependencies

Install necessary dependencies (`go`, `cmake`, and `gcc`) as required by your setup.

## Download and Install Ollama

Download and install Ollama using the provided script:

```bash
curl -fsSL https://ollama.com/install.sh | sh
```

## Running Llama3
###Start the Llama3 Model
Start the Llama3 model to set up the model so it can accept API requests:
```bash
ollama run llama3
```
###Interact with Llama3 via curl
Send a prompt to the Llama3 model and receive a generated response:

```bash
curl http://localhost:11434/api/generate -d '{
  "model": "llama3",
  "prompt": "Why is the sky blue?"
}'

```
##Running Gemma
###Start the Gemma Model
Start the Gemma model to prepare the model for API requests:

```bash
ollama run gemma:2b
```

###Interact with Gemma via curl
Send a prompt to the Gemma model and receive a generated response:

```bash
curl http://localhost:11434/api/generate -d '{
  "model": "gemma:2b",
  "prompt": "Tell me a fun fact about space."
}'
```

##Results
###Llama3 Response
```bash
curl http://localhost:11434/api/generate -d '{
  "model": "llama3",
  "prompt": "Why is the sky blue?"
}'
# Response: {"text": "The sky is blue because molecules in the air scatter blue light from the sun more than they scatter red light."}

```

###Gemma Response
```bash
curl http://localhost:11434/api/generate -d '{
  "model": "gemma:2b",
  "prompt": "Tell me a fun fact about space."
}'
# Response: {"text": "A fun fact about space is that there is no sound in space because molecules are too far apart to transmit sound."}

```
