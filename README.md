# Advanced Information Retrieval System

This project is a sophisticated information retrieval system developed to search and rank documents based on user queries. It leverages preprocessing techniques, indexing, and both traditional and advanced NLP models for enhanced search accuracy and relevance. 

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Preprocessing](#preprocessing)
- [Indexing](#indexing)
- [Query Processing](#query-processing)
- [Query Expansion](#query-expansion)
- [User Interface](#user-interface)
- [Evaluation](#evaluation)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

This project utilizes the [CISI dataset](https://www.kaggle.com/datasets/your-link-here), which consists of:
- **Documents**: A file containing the documents to be searched.
- **Queries**: A file containing the queries to be processed.
- **Qrels**: A file containing relevance judgments for evaluating search accuracy.

The main objectives of this project are to:
1. Preprocess the data by tokenizing, stemming, and removing stop words.
2. Build an inverted index and posting list for efficient searching.
3. Implement query processing, retrieval, and ranking using TF-IDF and BM25 models.
4. Incorporate query expansion using the RM3 model to improve search accuracy.
5. Provide a simple user interface to interact with the system.

## Dataset

The CISI dataset is used for testing and evaluating the system. It includes files for documents, queries, and relevance judgments.

## Preprocessing

Implemented using [PyTerrier](https://github.com/terrier-org/pyterrier) and [NLTK](https://www.nltk.org/), the preprocessing steps include:
- **Tokenization and Stop Words Removal**: Splitting text into tokens and removing common stop words.
- **Stemming**: Reducing words to their root form.
- **Cleaning**: Removing unnecessary characters.

All of these functions are wrapped in a single `process` function that can be applied directly to queries and documents.

## Indexing

The system builds an **inverted index** and **posting list** for efficient document retrieval.

## Query Processing

1. Takes a query from the dataset.
2. Applies the `process` function for preprocessing.
3. Passes the processed query to a **TF-IDF** model to retrieve and rank relevant documents by score.

## Query Expansion

The system supports query expansion through:
- **BM25 Model**: Initial search to retrieve relevant documents.
- **RM3 Expander**: Expands the original query based on initial results.
  
The expanded query often improves retrieval accuracy, as shown by higher TF-IDF scores compared to the original query.

## User Interface

A simple UI is developed using:
- **Python, HTML, and CSS** via **Flask**.
- **Ngrok** integration for running the app on Colab for easy access.

Users can input queries, apply the RM3 expander, and utilize advanced models (Elmo, BERT) for improved results. The UI displays relevant documents, retrieval times, and document counts.

## Evaluation

Evaluation is conducted using `pt.Experiment` to measure performance across different models.

## Technologies Used

- **PyTerrier**: For building and evaluating retrieval models.
- **NLTK**: For text preprocessing.
- **TF-IDF and BM25**: For traditional information retrieval.
- **RM3**: For query expansion.
- **Elmo and BERT**: For deep semantic understanding and contextual relevance.
- **Flask and Ngrok**: For a user-friendly interface on Colab.

## Installation

To run this project locally, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/repository-name.git
    cd repository-name
    ```

2. Install required packages:
    ```bash
    pip install -r requirements.txt
    ```

3. Run the Flask app:
    ```bash
    python app.py
    ```

## Usage

1. Start the Flask app by running `app.py`.
2. Open the link provided by Ngrok to access the UI.
3. Enter a query and select options for query expansion or model use (Elmo, BERT).
4. View results, including retrieved documents, scores, retrieval times, and document counts.

## Contributing

Contributions are welcome! Please fork the repository, make changes, and submit a pull request.

## License

This project is licensed under the MIT License.
