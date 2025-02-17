# RDF Knowledge Graph Construction with LLMs

This repository provides sample data and structured prompts used for generating RDF graphs from medical terms using LLMs.

---

## Repository Structure

```
├── data/              # Medical terms sample data (xlsx)
├── prompts/           # JSON files with structured prompts
└── README.md          # This documentation file
```

---

## Prompts Format

Prompts are provided in JSON format to ensure clarity and reproducibility. Each JSON file contains the LLM mode, roles, and RDF graph generation instructions.

### Sample Prompt (Located in `prompts/rdf_snomed_prompt.json`):

```json
{
  "model_mode": "chat",
  "prompts": [
    { "role": "system", "text": "You are an RDF graph expert ..." },
    { "role": "user", "text": "HDL" },
    { "role": "assistant", "text": ":HDL rdf:type owl:DatatypeProperty ..." },
    { "role": "user", "text": "Patient" },
    { "role": "assistant", "text": ":Patient rdf:type owl:Class ;
    rdfs:label \"Patient\" ;
    rdfs:comment \"The main class representing a patient.\" ;
    skos:related [http://snomed.info/id/116154003](http://snomed.info/id/116154003) ." }
  ]
}
