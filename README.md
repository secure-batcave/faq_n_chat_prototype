# Faq and Chat Prototype

A quick prototype that includes a notebook and data.
It was made to query a local LLM, but the endpoint can probably be edited to point to any LLM as it uses openai api style queries.

## Setup
```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

Load the notebook (eg. via VSCode), edit the below lines to your endpoint and model:
```
client = openai.OpenAI(
    # base_url sets your (local) LLM endpoint
    base_url="http://localhost:8080/v1",
    api_key="sk-no-key-required"
)
```

```
model="gemma-2-9b-it",  # Edit if switching models
```

## Overview
Simple prototype that fetches data from a local .json file, initiates a client, and queries the LLM to summarize the content and provide example questions to ask.

## Future Plans
1. Build up the data
2. Create a robust back and forth chat system
3. Implement a vector embeddings database for the data that is used when the user asks a question. There will be some process to extract a semantic search query from the user question, pulls it from the vector db, check if the data can adequately answer the question, to then be given to the llm to use for its response.
4. Graphical Interface
