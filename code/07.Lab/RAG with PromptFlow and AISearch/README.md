## RAG with PromptFlow and AISearch

In this example, we will implement a Retrieval Augmented Generation (RAG) application leveraging Phi3 as SLM, AI Search as vectorDB and Prompt Flow as low-code orchestrator.

## Features

- Easy deployment using Docker.
- Scalable architecture for handling AI workflows.
- Low code approach using Prompt Flow

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Docker installed on your local machine.
- An Azure account with permissions to create and manage container resources.
- An Azure AI Studio and Azure AI Search instances
- An embedding model (Azure OpenAI models or OSS models from Model Catalog) to create the index
- Python 3.8 or later installed on your local machine
- An Azure Container Registry (or any registry of your choice)

## Installation

1. Create a new flow on your Azure AI Studio Project using the flow.yaml file.
3. Deploy a Phi3 Model from your Azure AI model catalog and create the connection to your project.
4. Create an index with the PDF Attention is All you need (or any documents of your choice) on the Azure AI Studio UI with the Azure AI Search connection.
5. Deploy the flow on a managed enpoint and use it in the prompt-flow-frontend.py file.
6. Clone the repository:

    ```sh
    git clone [[https://github.com/yourusername/prompt-flow-frontend.git](https://github.com/microsoft/Phi-3CookBook.git)](https://github.com/microsoft/Phi-3CookBook.git)
    cd code/07.Lab/RAG with PromptFlow and AISearch
    ```

7. Build the Docker image:

    ```sh
    docker build -t prompt-flow-frontend.py .
    ```

8. Push the Docker image to Azure Container Registry:

    ```sh
    az acr login --name yourregistry
    docker tag prompt-flow-frontend.py:latest yourregistry.azurecr.io/prompt-flow-frontend.py:latest
    docker push yourregistry.azurecr.io/prompt-flow-frontend.py:latest
    ```

## Usage

1. Run the Docker container:

    ```sh
    docker run -p 8501:8501 yourregistry.azurecr.io/prompt-flow-frontend.py:latest
    ```

2. Access the application in your browser at `http://localhost:8501`.

## Contact

Valentina Alto - [Linkedin](https://www.linkedin.com/in/valentina-alto-6a0590148/)

Full Article: [RAG with Phi-3-Medium as a Model as a Service from Azure Model Catalog](https://medium.com/@valentinaalto/rag-with-phi-3-medium-as-a-model-as-a-service-from-azure-model-catalog-62e1411948f3)
