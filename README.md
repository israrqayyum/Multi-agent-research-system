# Multi-Agent Research System

An AI-powered research assistant that uses specialized agents to search, scrape, analyze, and synthesize information into structured reports. Built with LangChain and Streamlit.

## Overview

This system orchestrates four specialized AI agents in a pipeline to produce high-quality research reports:

1. **Search Agent** - Queries the web for recent and reliable information using Tavily
2. **Reader Agent** - Scrapes and extracts detailed content from relevant URLs
3. **Writer Chain** - Synthesizes research into a structured report
4. **Critic Chain** - Reviews and scores the report for quality assurance

## Features

- Multi-agent architecture with specialized roles
- Web search integration via Tavily API
- Intelligent content scraping and extraction
- Automated report generation with structured formatting
- Built-in quality review and scoring
- Interactive web interface powered by Streamlit
- Command-line interface for programmatic usage

## Installation

Clone the repository:

```bash
git clone <repository-url>
cd Multi-agent-research-system
```

Create and activate a virtual environment:

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Configuration

Create a `.env` file in the project root:

```env
OPENAI_API_KEY=your_openai_api_key
TAVILY_API_KEY=your_tavily_api_key
```

Get your API keys:
- OpenAI: https://platform.openai.com/api-keys
- Tavily: https://tavily.com

## Usage

### Web Interface

Launch the Streamlit app:

```bash
streamlit run app.py
```

The interface will open in your browser. Enter a research topic and click "Run Research Pipeline" to generate a report.

### Command Line

Run the pipeline from the terminal:

```bash
python pipeline.py
```

You'll be prompted to enter a research topic, and the system will process it through all four stages, displaying results in the console.

## Architecture

```
┌─────────────────┐
│  User Input     │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Search Agent    │  ← Tavily API
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Reader Agent    │  ← Web Scraping
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Writer Chain    │  ← GPT-4o-mini
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Critic Chain    │  ← Quality Review
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Final Report    │
└─────────────────┘
```

## Project Structure

```
Multi-agent-research-system/
├── app.py              # Streamlit web interface
├── pipeline.py         # CLI pipeline runner
├── agents.py           # Agent and chain definitions
├── tools.py            # Web search and scraping tools
├── requirements.txt    # Python dependencies
├── .env               # API keys (create this)
└── README.md          # This file
```

## Dependencies

- langchain - Framework for building LLM applications
- langchain-openai - OpenAI integration for LangChain
- streamlit - Web interface framework
- tavily-python - Web search API client
- beautifulsoup4 - HTML parsing for web scraping
- requests - HTTP library
- python-dotenv - Environment variable management

## Example Topics

- "Quantum computing breakthroughs in 2025"
- "Recent developments in CRISPR gene editing"
- "Progress in fusion energy research"
- "LLM agents and multi-agent systems 2025"

## Report Structure

Generated reports include:

- **Introduction** - Context and overview
- **Key Findings** - At least three well-explained points
- **Conclusion** - Summary and implications
- **Sources** - URLs referenced during research

## Quality Assurance

The critic chain evaluates each report on:

- Factual accuracy
- Structural clarity
- Depth of analysis
- Source quality

Feedback includes a score out of 10, strengths, areas for improvement, and a verdict.

## License

MIT

## Contributing

Contributions are welcome. Please open an issue first to discuss proposed changes.
