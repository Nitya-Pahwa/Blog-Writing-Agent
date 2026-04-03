# Blog-Writing-Agent
An AI-powered blog generation system that automatically creates structured, high-quality technical blogs using a multi-agent workflow built with LangGraph, Groq LLM, and Hugging Face image generation.

## Features
- Smart Routing System
  - Decides whether research is required (closed_book, hybrid, open_book)
- Automated Research (Optional)
  - Fetches relevant evidence using Tavily API
  - Filters and structures results
- AI Blog Planning
  - Generates a structured outline (7–9 sections)
  - Each section includes:
    - Goal
    - 4–6 bullet points
    - Word targets
    - Tags and constraints
- Parallel Section Writing
  - Each section is generated independently by worker nodes
  - Ensures detailed and structured content
- AI Image Generation
  - Automatically inserts image placeholders
  - Generates visuals using Hugging Face (FLUX model)
  - Embeds images into the final blog
- Markdown Output
  - Clean, ready-to-use .md blog file
  - Supports image embedding
- Download Options
  - Markdown file
  - ZIP bundle (Markdown + images)
- Streamlit UI
  - Interactive blog generation

## Architecture

```bash
Router -> Research -> Orchestrator -> Workers -> Reducer (Images)
```

### Components:
- Router Node
  - Determines if research is needed
- Research Node
  - Collects and filters evidence
- Orchestrator Node
  - Creates structured blog plan
- Worker Nodes
  - Generate blog sections in parallel
- Reducer Subgraph
  - Merges content
- Decides images
  - Generates & embeds images

## Tech Stack
- LangGraph – Workflow orchestration
- Groq (LLaMA 3.3 70B) – Text generation
- Hugging Face Inference API – Image generation
- Streamlit – Frontend UI
- Pydantic – Schema validation
- Python – Core implementation

## Setup

1. Clone the repo
``` bash
[git clone https://github.com/your-username/blog-writing-agent.git
cd blog-writing-agent](https://github.com/Nitya-Pahwa/Blog-Writing-Agent.git)
```

2. Install dependencies
```bash
pip install -r requirements.txt
```

3. Create .env file
```bash
GROQ_API_KEY=your_groq_api_key
HF_API_TOKEN=your_huggingface_token
TAVILY_API_KEY=your_tavily_key   
```

5. Run the app
```bash
streamlit run app.py
```
## Project Structure
```bash
├── backend.py          # LangGraph workflow
├── app.py              # Streamlit UI
├── images/             # Generated images
├── *.md                # Generated blogs
├── .env                # API keys
└── README.md
```


## Limitations
- API Rate Limits
  - Uses Groq and Hugging Face APIs, which have strict rate limits
  - Can lead to:
      - Slower generation
      - Incomplete sections
      - Lower-quality outputs in some runs
- LLM Variability
  - Output quality may vary depending on:
  - Prompt complexity
  - API response consistency
- Image Generation Constraints
  - Image model (FLUX) does not support text rendering
  - Only supports artistic/photorealistic visuals
- Performance
  - Parallel workers + delays (simulated latency) can increase total runtime

## Glimpses of Project

<img width="1920" height="894" alt="Screenshot (1810)" src="https://github.com/user-attachments/assets/8a272e69-0744-4b89-b28d-7f2a3ba2bb57" /><br>

<img width="1920" height="889" alt="Screenshot (1811)" src="https://github.com/user-attachments/assets/f4fd7952-8a07-447e-a588-f1a097bcabeb" /><br>


<img width="1920" height="915" alt="Screenshot (1812)" src="https://github.com/user-attachments/assets/2296fa94-848a-4e0c-8179-c6bb636a1902" /><br>


<img width="1920" height="892" alt="Screenshot (1794)" src="https://github.com/user-attachments/assets/dbbb2f08-c7ea-405d-986a-ee016a9f9dbc" /><br>

<img width="1920" height="897" alt="Screenshot (1795)" src="https://github.com/user-attachments/assets/d1a9860b-352a-46f3-ab01-62cb9ee97603" /><br>


<img width="1920" height="862" alt="Screenshot (1796)" src="https://github.com/user-attachments/assets/76bd19e1-db24-4374-b67f-0350000849c4" /><br>

<img width="1920" height="888" alt="Screenshot (1797)" src="https://github.com/user-attachments/assets/d6f8c580-0794-4fcd-bab4-bf6f6ab0127f" /><br>


<img width="1920" height="888" alt="Screenshot (1798)" src="https://github.com/user-attachments/assets/63b790e2-1d0c-42d1-8d01-b5eca40b4a87" /><br>


<img width="1920" height="852" alt="Screenshot (1799)" src="https://github.com/user-attachments/assets/c152c0b7-7ec2-4993-a0a6-c4b938e66aa6" /><br>


<img width="1920" height="881" alt="Screenshot (1800)" src="https://github.com/user-attachments/assets/a80021a7-bb51-4ee5-9c07-b3c303318e08" /><br>


<img width="1920" height="902" alt="Screenshot (1801)" src="https://github.com/user-attachments/assets/e3888852-1eb3-4a88-ac35-a1402e96caaf" /><br>


<img width="1920" height="900" alt="Screenshot (1802)" src="https://github.com/user-attachments/assets/19b159c3-8078-4bce-a8d3-d845ac37af0a" /><br>





