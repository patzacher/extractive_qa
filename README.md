# extractive_qa

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
