The final part of this project is present in this repository: [Link](../CrewAI/)


# Initial Research Workflow

This repository is intended to do the implementation of a research synthesis workflow designed to automate query processing and web searching and to compile the research using a single-agent architecture. The system is designed to demonstrate integrated tool usage, with which the agent (Oracle) selects from and the basic architecture present for research automation.

![xaxa](./workflow.png)

## Features

- Single-Agent Workflow:  
  A single "oracle" agent manages all subtasks and integrates different tools for final research synthesis.
  
- **Integrated Tools**:  
  - `rag_search_filter`: Filters retreived text documents according to relevance.  
  - `rag_search`: Retrieves relevant result sets from preloaded Redis databases.  
  - `fetch_arxiv`: Searches among research papers on Arxiv dataset.  
  - `web_search`: Fetches information from the web using DuckDuckGo.  
  - `final_answer`: Aggregation of information obtained into a final research report.  

- **Database**:  
  Creates a Redis database for effective storage and retrieval of documents.

- **Language Model (LLM)**:  
  Uses Cohere in the generation and synthesis of textual information

- **Web Search**:  
  Integrates DuckDuckGo for searching the web privately and efficiently.
---

## Architecture

The same workflow is enabled by a single oracle node to manage subtasks. Each tool has its usage limits to prevent looping indefinitely. This is a very simple design and decision-making can be easily centralized, which makes it good for small research but cannot be scaled or flexible at all.


## Limitations

- **Single-Agent Bottleneck**: All tasks are handled by one agent, leading to inefficiencies for complex workflows.  
  
- **Static Query Generation**: The queries are derived directly from human input, without optimization for context or relevance.  
  
- **Limited Iteration**: The system lacks mechanisms for iterative improvements based on critiques or feedback.  
  
- **Potential Infinite Loops**: Tool usage is capped, but the architecture still struggles with managing recursive workflows.

---

## Results
The system prompt used is show in the below figure
![system_prompt](./system_prompt.png)

The final report generated is shown in the below figure
![cascac](./final_report.png)


