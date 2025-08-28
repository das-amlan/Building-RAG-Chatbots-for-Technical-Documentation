# Building RAG Chatbots for Technical Documentation

![A car dashboard with lots of new technical features.](dashboard.jpg)

## Project Overview

This project demonstrates how to build a context-aware chatbot by integrating technical documentation, specifically a car manual, with a Large Language Model (LLM) using Retrieval Augmented Generation (RAG). The goal is to create a chatbot that can provide guidance to drivers based on the information contained within the manual.

## Purpose

The primary purpose of this project is to experiment with and implement RAG to create a chatbot capable of understanding and responding to queries related to car warning messages and their meanings. This proof of concept aims to show how LLMs can be augmented with external knowledge sources to provide more accurate and contextually relevant information.

## Data Source

The project utilizes an HTML file named `mg-zs-warning-messages.html`. This file contains information on warning messages and their corresponding procedures from an MG ZS car manual.

## Project Steps

The project involves the following key steps:

1.  **Loading Data**: The HTML car manual data is loaded using LangChain's `UnstructuredHTMLLoader`.
2.  **Splitting Data**: The loaded document is split into smaller, manageable chunks using `RecursiveCharacterTextSplitter` to facilitate efficient retrieval.
3.  **Creating Embeddings**: Embeddings are generated for the document chunks using OpenAI's `text-embedding-3-small` model.
4.  **Setting up Vector Store**: The document chunks and their embeddings are stored in a Chroma vector database for efficient similarity search.
5.  **Initializing LLM and Prompt**: A `ChatOpenAI` model (`gpt-4o-mini`) and a `ChatPromptTemplate` are initialized to generate responses.
6.  **Defining RAG Chain**: A RAG chain is defined using LangChain Expression Language (LCEL), connecting the retriever (vector store), the prompt template, and the LLM.
7.  **Invoking RAG Chain**: The RAG chain is invoked with a user query to retrieve relevant information from the manual and generate a context-aware response.

## Technologies and Libraries Used

The following key Python libraries are used in this project:

*   `langchain-core`
*   `langchain-openai`
*   `langchain-community`
*   `unstructured`
*   `langchain-chroma`
*   `langchain-text-splitters`
*   `openai`

## How to Run

1.  **Clone the repository (if applicable):** Clone this project to your local machine.
2.  **Install Dependencies**: Run the following commands to install the necessary packages:

    ```bash
    pip install --upgrade pip
    ```
    The notebook includes a function `install_if_needed` to ensure specific versions of required packages are installed.
3.  **Setup OpenAI API Key**: You will need an OpenAI API key to run the embedding and LLM models. Set it as an environment variable named `OPENAI_API_KEY`.
4.  **Run the Notebook**: Execute the cells in the provided Jupyter notebook (`your-notebook-name.ipynb`) sequentially.

## Potential and Next Steps

This project serves as a foundational example of using RAG for technical documentation. Future steps could involve expanding the dataset to include more of the car manual, implementing more sophisticated retrieval techniques, and integrating with text-to-speech for a fully functional voice assistant in a vehicle.
