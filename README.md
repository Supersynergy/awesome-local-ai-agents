# Awesome Local AI Agents

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

> A curated collection of local AI agent frameworks, tools, and resources for building autonomous AI systems that run entirely on your own hardware.

## Table of Contents

- [What Are Local AI Agents?](#what-are-local-ai-agents)
- [Why Local AI Agents Matter](#why-local-ai-agents-matter)
- [Quick Start Guide](#quick-start-guide)
- [Agent Frameworks](#agent-frameworks)
- [Local LLM Tools](#local-llm-tools)
- [Installation Guides](#installation-guides)
- [Use Cases](#use-cases)
- [Community Resources](#community-resources)
- [Contributing](#contributing)
- [License](#license)

---

## What Are Local AI Agents?

Local AI agents are autonomous software systems powered by large language models (LLMs) that run entirely on your own hardware without requiring cloud services. These agents can:

- **Reason and plan** - Break down complex tasks into manageable steps
- **Use tools** - Interact with APIs, databases, file systems, and external services
- **Maintain memory** - Remember context across conversations and sessions
- **Collaborate** - Work with other agents in multi-agent systems
- **Execute code** - Write, run, and debug code autonomously

Unlike cloud-based AI services, local agents process all data on your machine, ensuring complete privacy and control over your AI workflows.

## Why Local AI Agents Matter

### Privacy and Security

- **Data sovereignty** - Your data never leaves your machine
- **No external APIs** - Sensitive information stays private
- **Compliance** - Meet GDPR, HIPAA, and other regulatory requirements
- **Air-gapped operation** - Work in secure environments without internet

### Cost Efficiency

- **No API fees** - Eliminate per-token costs from cloud providers
- **Unlimited usage** - Run as many queries as your hardware allows
- **One-time investment** - Hardware costs amortize over time
- **Predictable expenses** - No surprise bills from heavy usage

### Performance and Control

- **Low latency** - No network round-trips
- **Customization** - Fine-tune models for your specific use cases
- **Offline capability** - Work without internet connectivity
- **Full control** - Choose your models, adjust parameters, and own the entire stack

### Development Benefits

- **Rapid prototyping** - Test ideas without API rate limits
- **Reproducibility** - Consistent results across environments
- **Debugging** - Full visibility into agent behavior
- **Integration** - Seamlessly embed into existing workflows

---

## Quick Start Guide

Get started with local AI agents in under 5 minutes:

### 1. Install a Local LLM Runtime

The fastest way to get started is with **Ollama**:

```bash
# macOS/Linux
curl -fsSL https://ollama.com/install.sh | sh

# Windows
# Download from https://ollama.com/download
```

### 2. Download a Model

```bash
# Pull a capable model for agent tasks
ollama pull llama3.1:8b

# Or for more advanced reasoning
ollama pull qwen2.5:14b
```

### 3. Install an Agent Framework

```bash
# Option A: CrewAI (easiest for multi-agent)
pip install crewai crewai-tools

# Option B: LangChain (most flexible)
pip install langchain langchain-community

# Option C: AutoGen (Microsoft's framework)
pip install autogen-agentchat
```

### 4. Create Your First Agent

```python
# Example with CrewAI and Ollama
from crewai import Agent, Task, Crew
from langchain_ollama import OllamaLLM

# Connect to local Ollama
llm = OllamaLLM(model="llama3.1:8b")

# Create an agent
researcher = Agent(
    role="Research Analyst",
    goal="Find and summarize information on given topics",
    backstory="You are an expert researcher with attention to detail",
    llm=llm,
    verbose=True
)

# Define a task
research_task = Task(
    description="Research the benefits of local AI agents",
    expected_output="A summary with key points",
    agent=researcher
)

# Run the crew
crew = Crew(agents=[researcher], tasks=[research_task])
result = crew.kickoff()
print(result)
```

---

## Agent Frameworks

A comprehensive list of frameworks for building local AI agents. For detailed information, see [FRAMEWORKS.md](FRAMEWORKS.md).

### Tier 1: Production-Ready Frameworks

| Framework | Stars | Language | Best For | Key Feature |
|-----------|-------|----------|----------|-------------|
| [LangChain](https://github.com/langchain-ai/langchain) | 116K+ | Python/JS | Complex workflows | Modular design, extensive integrations |
| [AutoGen](https://github.com/microsoft/autogen) | 50K+ | Python | Multi-agent systems | Conversational agents, Microsoft backing |
| [CrewAI](https://github.com/crewAIInc/crewAI) | 38K+ | Python | Team collaboration | Role-based agents, simple API |
| [LangGraph](https://github.com/langchain-ai/langgraph) | 19K+ | Python | Stateful workflows | Graph-based control flow |

### Tier 2: Specialized Frameworks

| Framework | Stars | Language | Best For | Key Feature |
|-----------|-------|----------|----------|-------------|
| [AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) | 170K+ | Python | Autonomous tasks | Self-planning, goal-driven |
| [Open Interpreter](https://github.com/OpenInterpreter/open-interpreter) | 56K+ | Python | Code execution | Natural language to code |
| [OpenHands](https://github.com/All-Hands-AI/OpenHands) | 45K+ | Python | Software development | Docker isolation, file editing |
| [Dify](https://github.com/langgenius/dify) | 55K+ | Python/TS | Visual building | GUI workflow builder |

### Tier 3: Emerging Frameworks

| Framework | Stars | Language | Best For | Key Feature |
|-----------|-------|----------|----------|-------------|
| [SmolAgents](https://github.com/huggingface/smolagents) | 15K+ | Python | Minimal footprint | ~1000 lines of code |
| [Agno](https://github.com/agno-agi/agno) | 20K+ | Python | Multimodal agents | Teams of agents |
| [Pydantic AI](https://github.com/pydantic/pydantic-ai) | 10K+ | Python | Type safety | Validated outputs |
| [Goose](https://github.com/block/goose) | 8K+ | Python | Extensibility | Block's framework |
| [Letta](https://github.com/letta-ai/letta) | 12K+ | Python | Persistent memory | Vector database integration |
| [Flowise](https://github.com/FlowiseAI/Flowise) | 32K+ | TypeScript | Drag-and-drop | Visual node editor |

---

## Local LLM Tools

Tools for running language models locally. For detailed comparisons, see [LOCAL-LLM-TOOLS.md](LOCAL-LLM-TOOLS.md).

### Runtime Comparison

| Tool | Interface | Ease of Use | Model Support | Best For |
|------|-----------|-------------|---------------|----------|
| [Ollama](https://ollama.com) | CLI | Excellent | 100+ models | Developers, automation |
| [LM Studio](https://lmstudio.ai) | GUI | Excellent | Extensive | Beginners, experimentation |
| [GPT4All](https://gpt4all.io) | GUI | Very Good | Curated | Privacy-focused users |
| [Jan](https://jan.ai) | GUI | Very Good | Good | ChatGPT replacement |
| [LocalAI](https://localai.io) | API | Good | Many formats | OpenAI compatibility |
| [text-gen-webui](https://github.com/oobabooga/text-generation-webui) | Web | Good | Very flexible | Advanced users |
| [Haplo AI](https://apps.apple.com/app/haplo-ai) | App | Very Good | Limited | iOS/macOS users |
| [Msty](https://msty.app) | GUI | Very Good | Good | Desktop users |

### Recommended Models for Agents

| Model | Parameters | RAM Required | Agent Capability | Speed |
|-------|------------|--------------|------------------|-------|
| Llama 3.1 8B | 8B | 8GB | Good | Fast |
| Qwen 2.5 14B | 14B | 16GB | Excellent | Medium |
| Mistral 7B | 7B | 8GB | Good | Very Fast |
| DeepSeek V3 | Various | 16GB+ | Excellent | Medium |
| CodeLlama 13B | 13B | 16GB | Code-focused | Medium |

---

## Installation Guides

### Setting Up Ollama + CrewAI

```bash
# 1. Install Ollama
curl -fsSL https://ollama.com/install.sh | sh

# 2. Start Ollama service
ollama serve &

# 3. Pull models
ollama pull llama3.1:8b
ollama pull nomic-embed-text  # For embeddings

# 4. Create Python environment
python -m venv agent-env
source agent-env/bin/activate  # or `agent-env\Scripts\activate` on Windows

# 5. Install CrewAI
pip install crewai crewai-tools langchain-ollama

# 6. Verify installation
python -c "from crewai import Agent; print('CrewAI ready!')"
```

### Setting Up LM Studio + LangChain

```bash
# 1. Download LM Studio from https://lmstudio.ai
# 2. Launch and download a model (e.g., Llama 3.1 8B)
# 3. Start the local server (default: http://localhost:1234)

# 4. Install LangChain
pip install langchain langchain-openai

# 5. Use with LangChain
```

```python
from langchain_openai import ChatOpenAI

llm = ChatOpenAI(
    base_url="http://localhost:1234/v1",
    api_key="not-needed",
    model="local-model"
)

response = llm.invoke("Explain local AI agents")
print(response.content)
```

### Setting Up Jan + AutoGen

```bash
# 1. Download Jan from https://jan.ai
# 2. Launch and download a model
# 3. Enable API server in settings (default: http://localhost:1337)

# 4. Install AutoGen
pip install autogen-agentchat

# 5. Configure AutoGen
```

```python
import autogen

config_list = [{
    "model": "jan-model",
    "base_url": "http://localhost:1337/v1",
    "api_key": "not-needed"
}]

assistant = autogen.AssistantAgent(
    "assistant",
    llm_config={"config_list": config_list}
)
```

---

## Use Cases

### Software Development

- **Code generation** - Write functions, classes, and entire applications
- **Code review** - Analyze code for bugs, security issues, and improvements
- **Documentation** - Generate and update documentation automatically
- **Testing** - Create unit tests and integration tests
- **Refactoring** - Improve code structure while preserving functionality

### Research and Analysis

- **Literature review** - Summarize papers and extract key findings
- **Data analysis** - Process and interpret datasets
- **Report generation** - Create comprehensive reports from raw data
- **Competitive analysis** - Research and compare products or companies

### Content Creation

- **Technical writing** - Create tutorials, guides, and documentation
- **Marketing copy** - Generate product descriptions and ad copy
- **Translation** - Translate content between languages
- **Editing** - Proofread and improve existing content

### Automation and Workflows

- **Email processing** - Categorize, summarize, and draft responses
- **Data entry** - Extract information from documents
- **Scheduling** - Manage calendars and coordinate meetings
- **System administration** - Generate scripts and manage infrastructure

### Personal Assistants

- **Note-taking** - Summarize meetings and organize information
- **Task management** - Plan and track projects
- **Learning** - Create study materials and explanations
- **Decision support** - Analyze options and provide recommendations

---

## Community Resources

For an extensive list of community resources, see [AWESOME-LISTS.md](AWESOME-LISTS.md).

### Official Documentation

- [LangChain Docs](https://python.langchain.com/)
- [AutoGen Docs](https://microsoft.github.io/autogen/)
- [CrewAI Docs](https://docs.crewai.com/)
- [Ollama Docs](https://github.com/ollama/ollama/blob/main/docs/README.md)

### Learning Resources

- [LangChain Academy](https://www.langchain.com/langchain-academy) - Free courses
- [Hugging Face Course](https://huggingface.co/learn) - AI/ML fundamentals
- [DeepLearning.AI](https://www.deeplearning.ai/) - Agent courses

### Community Forums

- [r/LocalLLaMA](https://reddit.com/r/LocalLLaMA) - 534K+ members
- [LangChain Discord](https://discord.gg/langchain)
- [Ollama Discord](https://discord.gg/ollama)

### GitHub Awesome Lists

- [awesome-llm-agents](https://github.com/kaushikb11/awesome-llm-agents)
- [awesome-agents](https://github.com/kyrolabs/awesome-agents)
- [awesome-langchain](https://github.com/kyrolabs/awesome-langchain)

---

## Repository Statistics

This repository covers:

- **15+ Agent Frameworks** - From enterprise-ready to experimental
- **8+ Local LLM Tools** - Various interfaces and capabilities
- **10+ Recommended Models** - Tested for agent workflows
- **5+ Installation Guides** - Step-by-step setup instructions
- **20+ Use Cases** - Real-world applications
- **50+ Community Resources** - Awesome lists, tutorials, papers

---

## Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details on:

- Adding new frameworks or tools
- Improving documentation
- Fixing errors
- Sharing use cases and examples

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

Thanks to all the developers and researchers building the local AI ecosystem:

- The LangChain team for pioneering modular agent design
- Microsoft for AutoGen and pushing multi-agent research
- The CrewAI team for simplifying agent collaboration
- Ollama for making local LLM deployment accessible
- The r/LocalLLaMA community for continuous testing and feedback

---

**Star this repo** if you find it useful! Your support helps others discover these resources.

[Report an Issue](https://github.com/your-username/awesome-local-ai-agents/issues) | [Request a Feature](https://github.com/your-username/awesome-local-ai-agents/issues/new)
