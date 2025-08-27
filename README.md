# BlogSmithAI

A small proof-of-concept project that generates SEO-friendly blog titles and full blog content using a Groq LLM and a state-driven graph. The project wires together:

- Graph definition and orchestration: [`src.graphs.graph_builder.GraphBuilder`](src/graphs/graph_builder.py) (graph available as [`src.graphs.graph_builder.graph`](src/graphs/graph_builder.py))
- LLM adapter: [`src.llms.groqllm.GroqLLM`](src/llms/groqllm.py)
- Blog node logic: [`src.nodes.blog_node.BlogNode`](src/nodes/blog_node.py)
- State typing: [`src.states.blogstate.BlogState`](src/states/blogstate.py)
- HTTP endpoint: [`app.create_blogs`](app.py)

Files
- [app.py](app.py) — FastAPI app and endpoint
- [src/graphs/graph_builder.py](src/graphs/graph_builder.py) — graph setup and compilation
- [src/llms/groqllm.py](src/llms/groqllm.py) — Groq LLM helper
- [src/nodes/blog_node.py](src/nodes/blog_node.py) — title and content generation nodes
- [src/states/blogstate.py](src/states/blogstate.py) — state model
- [langgraph.json](langgraph.json) — graph entry for langgraph tooling
- [request.json](request.json) — example request payload
- [requirements.txt](requirements.txt), [pyproject.toml](pyproject.toml)

Quickstart

1. Prerequisites
   - Python 3.13+
   - Create a virtual environment and install dependencies:
     ```sh
     python -m venv .venv
     source .venv/bin/activate  # or .venv\Scripts\activate on Windows
     pip install -r requirements.txt
     ```