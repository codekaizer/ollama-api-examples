# Ollama API Examples

This repository contains example calls to the Ollama APIs (with an Ollama server assumed to be running on `localhost:9191`).

## Abstract  
This repo demonstrates how to interact with Ollama via HTTP API for loading models, generating embeddings, and chatting — with multiple variants of usage (streaming, behavior prompts, structured output, etc.).

## Tools  
- **[Bruno](https://github.com/usebruno/bruno)** — a GUI/API client; can be a useful alternative to Postman for testing these endpoints.

## Models Used for Demonstration  
| Model name | Approx size |
|------------|--------------|
| `hf.co/Qwen/Qwen3-Embedding-0.6B-GGUF` | ~ 500 MB |
| `qwen3:1.7b` | ~ 2 GB |

## Reference Documentation  
- [Ollama API specification](https://github.com/ollama/ollama/blob/main/docs/api.md)
- [Local LLM guide (blog)](https://codekaizer.com/ai/local_llm.html)

---

## Repository Structure & Use Cases  

Below is a description of each folder and the purpose of its examples.

### Folder: `models-related-api`  
Contains endpoints related to managing models (download, rename, inspect, delete, etc.)

- **01_pull_from_huggingface**  
   How to pull / download GGUF-format models from Hugging Face, especially those with embedding capabilities.

- **02_create_embeddings**  
   Example of generating embeddings from text.

- **03_copy_model_with_custom_name**  
   How to rename an existing model with a more readable alias.

- **04_list_local_models**  
   List all models currently present locally.

- **05_show_model_details**  
   Retrieve detailed metadata (config, capabilities, license, file paths, etc.) about a pulled model.

- **06_create_embeddings_custom_model**  
   Use the alias from step 3 to generate embeddings from that renamed model.

- **07_delete_model**  
   Remove a model from your local Ollama installation.

- **08_check_ollama_versions**
    Verify ollama version installed locally 
---

### Folder: `talk-to-llm`  
Examples of different ways to send prompts or dialogue to the model.

- **[Optional] 00_pull_small_model**  
  (Optional) Pull a compact model (e.g. `qwen3:1.7b`) for faster interactive testing.

- **01_generate_basic**  
   Send a simple prompt; the model returns a completion (e.g. “Explain the difference between Chat and Generate APIs”).

- **02_generate_disable_stream**  
   Same as above, but disables streaming (i.e. wait for the full response before returning).

- **03_generate_disable_stream_and_think**  
   In addition, instruct the model *not* to use “thinking” or intermediate rationale, to observe the difference in output.

- **04_generate_with_behavior**  
   Give the model constraints or personality instructions on how to respond.

- **05_generate_with_structured_output**  
   Combine behavior instructions *and* a structured output format (e.g. JSON) in your prompt.

- **06_chat_basic**  
   Use the Chat API in a basic single-turn fashion.

- **07_chat_with_history**  
   Use the Chat API with context / history to let the model preserve memory and build on previous turns.

---

### Folder: `vision-llm` (Bonus)  
Examples for interacting with models that support image inputs.

- **[Optional] 00_pull_vision_model**  
  Fetch a smaller model with vision capabilities.

- **01_describe_image**  
   Convert an image to base64, pass that to the model, and have it describe the content of the image.  
   > Note: The base64 image strings used can be found in the `environments` folder or files.

---