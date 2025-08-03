# Deep Research Workflow

This is a multi-agent deep research system built with LlamaIndex Workflows that generates comprehensive reports on any research topic.

## Setup

1. Install required dependencies:
   ```bash
   pip install llama-index-llms-openai tavily-python python-dotenv
   ```

2. Create a `.env` file in the project root with your API keys:
   ```
   OPENAI_API_KEY=your_openai_api_key_here
   TAVILY_API_KEY=your_tavily_api_key_here
   ```

3. Run the workflow:
   ```bash
   python deepresearch.py
   ```

## Workflow Overview

The Deep Research Workflow consists of multiple steps orchestrated by three specialized agents:

### Steps

1. **Setup**: Initialize the workflow with the research topic and prepare all agents
2. **Generate Questions**: Create relevant research questions about the topic
3. **Answer Questions**: Research and answer each question using web search
4. **Write Report**: Combine all answers into a comprehensive report

### Agents

#### 🤔 Question Agent
- **Purpose**: Generates research questions for a given topic
- **Tools**: None (uses LLM reasoning only)
- **Output**: List of specific questions to research

#### 🔍 Answer Agent  
- **Purpose**: Researches and answers individual questions
- **Tools**: Web search via Tavily API
- **Output**: Detailed answers based on web research

#### 📝 Report Agent
- **Purpose**: Synthesizes all Q&A pairs into a final report
- **Tools**: None (uses LLM reasoning only)
- **Output**: Comprehensive research report

## How It Works

1. User provides a research topic via terminal input
2. Question Agent generates relevant research questions
3. Multiple Answer Agents work concurrently to research each question
4. Report Agent combines all findings into a final comprehensive report
5. Progress updates are shown throughout the process

## Features

- **Concurrent Processing**: Multiple questions are researched simultaneously
- **Real-time Progress**: Live updates during research process
- **Web Integration**: Uses Tavily for up-to-date web search
- **Comprehensive Output**: Detailed final report combining all research
