---
layout: default
title: "RuralKG Dataset"
nav_order: 1
permalink: /
---

# RuralKG Dataset

RuralKG is a hierarchical data repository and knowledgbase generated from multiple federal sources (e.g., NSDUH, NIBRS, TEDS-A/D). It focuses on improving our understanding of risk environments (e.g., substance abuse, mental health crisis, and social justice) in the United States' rural communities and strengthening their resilience. It provides a complete data processing pipeline—from raw data extraction to deploying a retrieval-augmented generation (RAG) system—making it a robust resource for researchers, practitioners, and educators.

RuralKG is part of the Proto-OKN project, which is supported by the National Science Foundation (NSF) under grant number 2333836. This is a project undergoing so RuralKG is still evolving. The current update pace is twice per quarter.

## Target Audience
Beginners: Students and researchers who are new to the Knowledge Graph, Retrieval-Augmented Generation (RAG), and the social determinants of health and justice.

Intermediates: Practitioners who have some experience with one or more components of the knowledge graph and retrieval-augmented generation.

Advanced Users: Researchers who are familiar with the knowledge graph and retrieval-augmented generation and want to use RuralKG for their work.

Here are use cases for the target audience at different stages of their journey:

For Beginners: 
- Extract entities and relationships from the extended CSV file provided by RuralKG. The extended CSV file is the list of variables and their answer options in the codebook. In NSDUH, variables represent the questions in the survey. In the TSV format dataset provided by NSDUH, each row represents a respondent's answer to a question and each column represents a variable (question).
- Build ontology and knowledge graph based on the extracted entities and relationships.
- Build vector database to store the knowledge graph and auxiliary information, test different indexing methods and the traditional embedding based retrieval.

For Intermediates:
- Contruct the knowledge graph from the raw data. Enrich the knowledge graph with data from other sources.
- Build a RAG system using the PostgreSQL database in which the knowledge graph and auxiliary information are stored in the tables.
- Use the KG to regulate the RAG system.

For Advanced Users:
- Generate the knowledge graph and RAG system from the raw data using their own methods.
- Focus on the KG quality and conduct comprehensive evaluation.
- Deliver insights of the domain, instead of continuing the data processing pipeline. Try to find the potential research gaps and conduct social determinants analysis.


## Project Overview

Instead of a single dataset, RuralKG is dedicated to providing reliable and reusable datasets for all the components of the RuralKG pipeline. Datasets from different layers represent different aspects and readiness of the knowledge representation.

1. **Extended Variable List:**  
   Raw data from federal codebooks (e.g., NSDUH) is processed into an extended CSV format, capturing rich, structured information. This approach utilizes the structure of the codebooks that the most vital variable section in the codebook is organized in a table-like pattern.

   The scripts and methods for the extended CSV generation are available at [beginner-pdf-parsing](02-beginner-pdf-parsing.md).

   One generated extended CSV file for NSDUH 2022 codebook is available at [ndsuh_2022_codebook.csv](data/nsduh_2022_codebook.csv).

2. **Ontology & Knowledge Graph:**  
   The CSV data is used to build an ontology and a comprehensive knowledge graph that interconnects disparate data sources. 

   The scripts and methods for the ontology and knowledge graph construction are available at [03-ontology-construction](03-intermediate-ontology-construction.md).

   The generated RuralKG is submitted to the FRINK platform for the public use. You can find the RuralKG on the FRINK platform at [Query on FRINK](https://frink.apps.renci.org/?query=PREFIX+rdf:+%3Chttp://www.w3.org/1999/02/22-rdf-syntax-ns%23%3E%0APREFIX+rdfs:+%3Chttp://www.w3.org/2000/01/rdf-schema%23%3E%0ASELECT+*+WHERE+{%0A++?sub+?pred+?obj+.%0A}+LIMIT+10&sources=federation).

   You can also download the current TTL version of RuralKG from this maintained link [RuralKG](data/rural_kg.ttl).

   For users who prefer to use Neo4j, instead of RDF format and SPARQL queries, the Neo4j database dump for the seed ontology can be found at [RuralKG Neo4j Seed](data/nsduh.dump). This seed ontology is not complete, but it can be used as a starting point for building a knowledge graph.

3. **Database Integration:**  
   Leveraging the knowledge graph, a relational database is constructed to manage both intermediate and final data effectively.

4. **RAG System Deployment:**  
   All the processed materials support a retrieval-augmented generation system, facilitating intelligent query responses and data exploration for both academic research and public service applications.

![Project overview diagram](media/DCL.png)

## Alpha Version Demo

An alpha version of the RuralKG Web Service is available at [RuralKG Web Service](http://52.170.155.134:8050/).

In this demo, you can explore:
- **Knowledge Queries:** Retrieve background information and insights about the dataset components.
- **Data Queries:** Access detailed data on substances and related metrics.
- **Service Queries:** Find mental health treatment facilities and other public service providers in rural areas.

Test cases and further documentation are available at [RuralKG Test Cases](data/test_case.csv).