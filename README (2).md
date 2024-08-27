
# RAG System for Myntra Dress Recommendations

This project implements a Retrieval-Augmented Generation (RAG) system that recommends dresses from the Myntra dataset based on user queries. The system uses a combination of retrieval and generative models to provide relevant and contextually appropriate product descriptions.

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Deployment](#deployment)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

The RAG system is designed to take user queries, preprocess them, retrieve relevant product descriptions from the Myntra dataset, and generate a cohesive response using a generative model. The primary components include:

- **Embedding Generation**: Converts product descriptions into embeddings using OpenAIEmbeddings.
- **Retrieval**: Uses FAISS to index and retrieve relevant product descriptions based on the query.
- **Generative Model**: Enhances the retrieved results using OpenAI’s generative model (`text-davinci-003`).

## Features

- Efficient similarity search with FAISS.
- Contextually relevant response generation using OpenAI's models.
- Easy to deploy and extend.

## Requirements

Ensure you have the following software and libraries installed:

- Python 3.7+
- OpenAI API Key
- Required Python packages:
  - `langchain-openai`
  - `faiss-cpu`
  - `pandas`
  - `numpy`

## Installation

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/your-username/myntra-rag-system.git
    cd myntra-rag-system
    ```

2. **Install Dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

3. **Setup API Key**:
   - Store your OpenAI API key in a file named `api_key.txt` in the root directory of the project:
     ```
     sk-your-api-key-here
     ```

4. **Prepare the Dataset**:
   - Ensure you have the Myntra dataset (`myntra_dresses.csv`) in the root directory.
   - The CSV should have a `description` column containing product descriptions.

## Usage

1. **Run the Script**:
    ```bash
    python run_rag_system.py
    ```

2. **Query the System**:
   - The system will prompt you to input a query.
   - Example: `I'm looking for a summer dress with floral patterns.`

3. **Get Recommendations**:
   - The system will process the query, retrieve relevant descriptions, and generate a response.

## Deployment

To deploy this system, you can follow these steps:

1. **Create a Virtual Environment**:
   - It is recommended to create a virtual environment for the project:
     ```bash
     python -m venv venv
     source venv/bin/activate  # On Windows use `venv\Scripts\activate`
     ```

2. **Install Dependencies**:
   - Install the required packages as mentioned in the [Installation](#installation) section.

3. **Run as a Service**:
   - You can set up the script to run as a web service using Flask or FastAPI for easier interaction.

4. **Containerization (Optional)**:
   - For production, consider using Docker to containerize the application:
     ```bash
     docker build -t myntra-rag-system .
     docker run -p 8000:8000 myntra-rag-system
     ```

## Troubleshooting

- **Rate Limit Errors**: If you encounter `RateLimitError` from OpenAI, consider implementing retry logic and batching as demonstrated in the code.
- **Deprecation Warnings**: Ensure you’re using the latest version of `langchain-openai` and follow any migration steps if required.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes.

## License

This project is licensed under the MIT License - see the `LICENSE` file for details.
