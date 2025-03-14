# LlamaCloud RAG Demo

This repository contains a Streamlit application that demonstrates Retrieval-Augmented Generation (RAG) using LlamaCloud for document retrieval and SQL for structured data queries, powered by Gemini 2.0.

## Overview

The application showcases a hybrid approach to question answering by:
- Using a SQL database for structured city data (population statistics)
- Leveraging LlamaCloud for unstructured document retrieval
- Employing Gemini 2.0 for natural language understanding and response generation

This combination allows for precise answers to factual questions while maintaining the flexibility to handle nuanced, context-dependent queries.

## Features

- **Natural Language Queries**: Ask questions about US cities in plain English
- **Hybrid RAG Architecture**:
  - SQL database for population statistics
  - LlamaCloud for pre-indexed city documents
- **Smart Query Routing**: Automatically directs queries to the appropriate backend
- **Interactive Chat Interface**: Built with Streamlit for a user-friendly experience

## Demo Screenshot

![image](https://github.com/user-attachments/assets/b5292952-8458-4b25-a392-8c51dc082f99)


## Installation

### Prerequisites

- Python 3.8 or higher
- Google API key (for Gemini access)
- LlamaCloud API key and organization ID

### Setup

1. Clone this repository:
```bash
git clone https://github.com/pandyaved98/Assignment.git
cd Assignment
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate
```

3. Install the required packages:
```bash
pip install -r requirements.txt
```

## Required API Keys

This application requires the following API keys:

1. **Google API Key** for Gemini models:
   - Get your API key from [Google AI Studio](https://ai.google.dev/)
   - Required for both LLM inference and embeddings

2. **LlamaCloud Credentials**:
   - API Key
   - Organization ID
   - Project Name
   - Index Name

You can input these credentials directly in the Streamlit UI or set them as environment variables.

## Usage

1. Start the Streamlit application:
```bash
streamlit run app.py
```

2. Open your browser and navigate to `http://localhost:8501`

3. Input your API keys in the sidebar

4. Start asking questions about US cities like:
   - "What is the population of New York City?"
   - "Which city has the highest population?"
   - "Tell me about the history of Chicago."
   - "Compare the populations of Los Angeles and Houston."

## How It Works

The application follows this workflow:

1. **User Query Input**: The user enters a natural language question about cities
2. **Query Analysis**: The system determines if the query is about population/statistics or general information
3. **Query Routing**:
   - Population queries → SQL database (via direct SQL or NLSQLTableQueryEngine)
   - General information queries → LlamaCloud document retrieval
4. **Response Generation**: The appropriate data is retrieved and used to generate a natural language response
5. **Result Display**: The answer is shown to the user along with the source of information

## Architecture

![RAG_Text_to_SQL](https://github.com/user-attachments/assets/a5876be7-29c8-4ac6-a4f4-4f67d59e697f)

## Requirements

The project requires the following Python packages:

```
streamlit
llama-index
llama-index-llms-gemini
llama-index-embeddings-gemini
llama-index-indices-managed-llama-cloud
sqlalchemy
pandas
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
