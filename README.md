# Autonomous Scientific Research Assistant (LangGraph)

A multi-agent AI system built with LangGraph and Llama 3, designed to autonomously fetch, extract, and synthesize peer-reviewed microbiological literature directly from the NCBI/PubMed database.

## Project Origins & The "Plus One" Innovation

This project was built to demonstrate how foundational AI frameworks can be adapted to solve highly specific, real-world scientific problems. 

The core multi-agent architecture and state-routing logic were inspired by an excellent technical framework published by [AmanxAI](https://amanxai.com/2025/12/09/build-a-multi-agent-system-with-langgraph/). 

To push the technical boundaries beyond a standard implementation, I engineered a domain-specific "Plus One" feature: **I tailored the entire pipeline to autonomously validate my own award-winning microbiology research paper**, *POMELIQUID: Ekstrak Etanol Daun Matoa (Pometia pinnata) sebagai Agen Hayati Antibakteri Aeromonas hydrophila pada Budidaya Ikan Mas Koki*. 

Rather than allowing the AI to scrape the open web, I integrated the `Biopython` library to restrict the system strictly to the PubMed database. I then engineered the state schema to extract the exact variables measured in my laboratory methodology (phytochemical profiles, extraction methods, and inhibition zones).

## System Architecture

The system utilizes a deterministic Directed Acyclic Graph (DAG) to route tasks through three specialized micro-agents. To prevent the LLM from hallucinating biological data, the model temperature is strictly locked at `0.0`.

1. **The Researcher (Data Ingestion):** Bypasses generic search engines by utilizing a custom `Biopython` E-utilities tool to securely fetch verified biomedical abstracts directly from NCBI.
2. **The Analyst (Focused Extraction):** Utilizes isolated LLM micro-chains to parse dense abstracts. It specifically hunts for the metrics aligned with the POMELIQUID research: *Phytochemical Profiles (Flavonoids/Saponins/Tannins), Extraction Methodologies,* and *Quantitative Inhibition Zone Data*.
3. **The Critic (Synthesis):** Acts as a senior peer-reviewer. It takes the isolated variables from the Analyst and synthesizes them into a final comparative analysis that evaluates the core scientific hypothesis.

## Why This Matters

Conducting literature reviews is one of the most time-consuming aspects of laboratory research. Furthermore, standard Generative AI models are fundamentally unsafe for scientific research due to their tendency to hallucinate unverified experimental metrics. By creating a closed-loop system that only ingests verified data and processes it through specialized micro-chains, this project demonstrates a safe, reliable integration of AI into computational biology.

## How to Get Started

### Prerequisites
To run this project locally, you will require:
* **Python 3.10+**
* **Ollama** installed on your local machine with the `llama3` model pulled (`ollama run llama3`).

### Installation

1. Clone this repository to your local machine:
   ```bash
   git clone [https://github.com/YOUR-USERNAME/autonomous-scientific-research-ai.git](https://github.com/YOUR-USERNAME/autonomous-scientific-research-ai.git)
   cd autonomous-scientific-research-ai
