# Extractive QA System Using Python and Haystack

## Overview
This is a repository for an Python code used to build an extractive Question-Answering model using [Haystack](https://haystack.deepset.ai/).

Haystack is an end-to-end open-source framework for creating Question-Answering models. Haystack has three primary components: the DocumentStore, Retriever, and Reader.

1. DocumentStore: This is exactly what it sounds like. The DocumentStore stores text documents and their meta data. Documents are typically split into smaller units (e.g.,
paragraphs) before indexing to enable higher accuracy and granularity to answers. In this example, documents consist of webscraped text from a list of URLs pointing either
to an article or a YouTube video. Rudimentary pre-processing of text data is completed prior to using Haystack's preprocessor.

3. Retriever: These are fast and simple algorithms to identify candidate passages from a large collection of documents. It allows a set of k-candidate documents to be sent to the
Reader. In general, the Retriever helps narrow the scope for the Reader, which will then perform a thorough search of the top-k documents for the best answer.

4. Reader: Takes passages of text as input and returns top-k answers with their corresponding confidence scores (range 0-1). Readers are powerful models that are able to make a
full search in the selected documents with the aim of finding the right answer.

The DocumentStore, Retriever, and Reader are connected using a querying pipeline. Querying pipelines are used to receive a query from the user and produce a result.

## Usage

### Enable GPU Runtime in Google Colab
- **Install Packages**: Update and install required packages.

### Initialize the ElasticsearchDocumentStore
- Download, extract, and set permissions for the Elasticsearch installation image.

### Start the server
- Start Elasticsearch server.

## Upload Files

### Option 1: Upload Your Own Data
- Upload your text data files and, if available, a metadata file.

### Option 2: Retreive Example Dataset from Haystack Tutorial
- Download a dataset from the Game of Thrones Wikipedia.

## Index Documents with a Pipeline
- Index documents by converting them into Haystack Documents using an indexing pipeline.

## Initialize the Retriever
- Initialize the Retriever to score and retrieve relevant documents.

### Option 1: EmbeddingRetriever
- Use a model for semantic search.

### Option 2: BM25 Retriever
- Use BM25Retriever for sparse retrieval.

## Route Documents
- Route documents for reading text and tables using different Readers.

## Initialize the Reader
- Initialize a Reader that extracts the top answer candidates.

## Create the Retriever-Reader Pipeline
- Combine the Reader and Retriever in a querying pipeline.

## Ask your Question
- Query the pipeline to ask a question and set top-k parameters for the Retriever and Reader.

## Filter by Score Threshold
- Filter documents based on a score threshold and set a default answer.

## Print out the answers the pipeline returns
- Print the filtered answers returned by the pipeline.
