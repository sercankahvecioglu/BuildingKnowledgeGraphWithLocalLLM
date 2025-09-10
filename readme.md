# Knowledge Graph Triplet Extraction and Visualization

This repository contains a pipeline for extracting knowledge-graph-ready triplets from text, processing them, and visualizing the resulting knowledge graph. The project leverages a combination of natural language processing (NLP), graph processing, and visualization tools to build and query a knowledge graph.

## Features

- **Triplet Extraction**: Extracts entity–relation–entity triplets from text using a language model.
- **Data Processing**: Cleans and sanitizes extracted triplets for high-quality knowledge graph construction.
- **Graph Construction**: Builds a directed graph from the triplets using NetworkX.
- **Visualization**: Visualizes the knowledge graph interactively using PyVis.
- **Querying**: Supports querying the knowledge graph for relevant facts and relations.

## Project Structure

```
.
├── all_triplets.pkl          # Serialized triplets data
├── data.pdf                  # Input document for triplet extraction
├── graph_metam_kafka.html    # Interactive graph visualization
├── kg_generate.ipynb         # Main notebook for triplet extraction and graph generation
├── system_prompt.txt         # Prompt for the language model (v1)
├── system_promptv2.txt       # Updated prompt for the language model (v2)
```

## Usage

### 1. Extract Triplets
Run the `kg_generate.ipynb` notebook to extract triplets from the input text in `data.pdf`. The triplets are saved to `all_triplets.pkl`.

### 2. Visualize the Graph
The notebook generates an interactive visualization of the knowledge graph in `graph_metam_kafka.html`. Open this file in a browser to explore the graph.

### 3. Query the Knowledge Graph
Use the `search_kg2` function in the notebook to query the graph for relevant facts and relations. Example queries are provided in the `queries` list.

### 4. Save and Load Triplets
Triplets are serialized to `all_triplets.pkl` for reuse. Use the `save_obj` and `pickle.load` functions to save and load triplets.

## Example

### Input
Text from `data.pdf`:
```
John's eating food. It is daytime. He sits on the chair.
```

### Output
Extracted Triplets:
```json
[
  {"head_entity": {"entity": "John", "attribute": ""}, "relation": {"relation": "eat", "attribute": ""}, "tail_entity": {"entity": "food", "attribute": ""}},
  {"head_entity": {"entity": "John", "attribute": ""}, "relation": {"relation": "sit_on", "attribute": ""}, "tail_entity": {"entity": "chair", "attribute": ""}}
]
```

### Visualization
The triplets are visualized as a undirected graph in `frontendbookKG.html`.