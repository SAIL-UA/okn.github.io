---
layout: default
title: "RuralKG Dataset"
nav_order: 1
permalink: /
---

# RuralKG Dataset

RuralKG is a hierarchical data repository and knowledgbase generated from multiple federal sources (e.g., NSDUH, NIBRS, TEDS-A/D). It focuses on improving our understanding of risk environments (e.g., substance abuse, mental health crisis, and social justice) in the United States' rural communities and strengthening their resilience. It provides a complete data processing pipeline—from raw data extraction to deploying a retrieval-augmented generation (RAG) system—making it a robust resource for researchers, practitioners, and educators.

RuralKG is part of the Proto-OKN project, supported by the National Science Foundation (NSF) under grant number 2333836. As an evolving project, RuralKG is updated twice per quarter.

## Target Audience

**Beginners:**  
Students and researchers new to knowledge graphs, retrieval-augmented generation (RAG), and the social determinants of health and justice.  
- **Use Case:** Extract entities and relationships from the extended CSV (derived from federal codebooks like NSDUH) to build a basic ontology and knowledge graph, and experiment with vector databases and indexing methods.

**Intermediates:**  
Practitioners with some experience in knowledge graphs and RAG systems.  
- **Use Case:** Construct and enrich the knowledge graph from raw data, build a RAG system using a PostgreSQL database that stores the KG and auxiliary data, and leverage the KG to regulate the RAG process.

**Advanced Users:**  
Researchers familiar with knowledge graphs and RAG who aim to develop custom methodologies, evaluate the quality of the knowledge graph, and derive domain insights.
- **Use Case:** Generate a custom knowledge graph and RAG system from raw data, conduct comprehensive evaluations of KG quality, derive domain insights, and identify research gaps in social determinants analysis.

## Project Overview

RuralKG is designed as a layered ecosystem, offering reusable datasets for every stage of the data processing pipeline:

1. **Extended Variable List**  
   - **What:** Raw data from federal codebooks (e.g., NSDUH) is processed into an extended CSV format that captures detailed, structured information.
   - **Resources:**  
     - [CSV Generation Scripts & Methods](02-beginner-pdf-parsing.md)  
     - Example: [NSDUH 2022 Codebook CSV](data/nsduh_2022_codebook.csv)

2. **Ontology & Knowledge Graph**  
   - **What:** The extended CSV is used to construct an ontology and a comprehensive knowledge graph that interconnects disparate data sources.
   - **Resources:**  
     - [Ontology & KG Construction Scripts & Methods](03-ontology-construction.md)  
     - Download the current TTL version: [RuralKG TTL](data/rural_kg.ttl)  
     - For Neo4j users: [RuralKG Neo4j Seed](data/nsduh.dump)

3. **Database Integration**  
   - **What:** A relational database is employed to effectively manage heterogeneous data sources, supporting both intermediate and final data for advanced analyses.
   - **Resources:**  
     - [Database Integration Scripts & Methods](04-advanced-knowledge-graph-database.md)
     - PostgreSQL database dump: [RuralKG PostgreSQL](data/okndb0123.tar)

4. **RAG System Deployment**  
   - **What:** All processed materials serve as foundational data for a retrieval-augmented generation system, enabling intelligent query responses and data exploration for both academic research and public service applications.


### Project Overview Diagram

![Project overview diagram](media/DCL.png)

## Alpha Version Demo

An alpha version of the RuralKG Web Service is available at [RuralKG Web Service](http://52.170.155.134:8050/).

In this demo, you can explore:
- **Knowledge Queries:** Retrieve background information and insights from the dataset.
- **Data Queries:** Access detailed data on substances and related metrics.
- **Service Queries:** Locate mental health treatment facilities and other public service providers in rural areas.

Test cases and further documentation can be accessed at [RuralKG Test Cases](data/test_case.csv).