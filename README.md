# Awesome Local AI Agents — March 2026 Edition

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

> Complete guide to local AI agents, models, and tools — self-hosted only, no cloud required.
> Privacy-first. Air-gap compatible. Your data stays yours.

## Table of Contents

- [Local LLM Runners](#local-llm-runners)
- [Best Local Models (March 2026)](#best-local-models-march-2026)
- [Hardware Requirements](#hardware-requirements)
- [Quantization Guide](#quantization-guide)
- [Local Agent Frameworks](#local-agent-frameworks)
- [Local RAG Tools](#local-rag-tools)
- [Privacy and Security](#privacy-and-security)
- [Quick Start Guide](#quick-start-guide)
- [Performance Benchmarks](#performance-benchmarks)
- [Related Lists](#related-lists)

---

## Local LLM Runners

| Runner | Stars | Platform | Interface | Key Feature |
|--------|-------|----------|-----------|-------------|
| [Ollama](https://ollama.com) | 110K+ | Mac/Linux/Win | CLI + REST | Easiest setup, 200+ model library, one-line pulls |
| [LM Studio](https://lmstudio.ai) | — | Mac/Win/Linux | GUI | GGUF model browser, built-in chat, local server |
| [llama.cpp / llama-server](https://github.com/ggml-org/llama.cpp) | 80K+ | All | CLI + REST | Raw performance, Metal/CUDA/CPU backends |
| [vLLM](https://github.com/vllm-project/vllm) | 50K+ | Linux (GPU) | REST | Production serving, PagedAttention, OpenAI-compat |
| [Jan.ai](https://jan.ai) | 28K+ | Mac/Win/Linux | GUI | Privacy-first desktop app, ChatGPT replacement |
| [GPT4All](https://gpt4all.io) | 72K+ | Mac/Win/Linux | GUI + CLI | Runs on CPU only, no GPU required |
| [LocalAI](https://localai.io) | 28K+ | All (Docker) | REST | Drop-in OpenAI API, multimodal, TTS, image gen |
| [koboldcpp](https://github.com/LostRuins/koboldcpp) | 10K+ | All | Web UI | KoboldAI backend, great for creative/roleplay tasks |
| [text-generation-webui](https://github.com/oobabooga/text-generation-webui) | 43K+ | All | Web UI | Advanced params, extensions ecosystem, multiple backends |

---

## Best Local Models (March 2026)

| Model | Parameters | VRAM (Q4) | Quant Available | Best For |
|-------|------------|-----------|-----------------|----------|
| **Llama 4 Scout** (Meta) | 8B active / MoE | 6 GB | Q4, Q5, Q6, Q8 | General chat, coding, fast inference |
| **Llama 4 Maverick** (Meta) | 70B active / MoE | 24 GB | Q2, Q4, Q5 | Complex reasoning, long context (1M tokens) |
| **Gemma 3 2B** (Google) | 2B | 2 GB | Q4, Q8 | Edge devices, embedded, Raspberry Pi |
| **Gemma 3 9B** (Google) | 9B | 6 GB | Q4, Q6, Q8 | Best quality-per-VRAM ratio, strong multilingual |
| **Gemma 3 27B** (Google) | 27B | 16 GB | Q4, Q5, Q6 | High quality, instruction following, reasoning |
| **Qwen 2.5 7B** (Alibaba) | 7B | 5 GB | Q4, Q8 | Code, math, multilingual (Chinese/English) |
| **Qwen 2.5 14B** (Alibaba) | 14B | 10 GB | Q4, Q6 | Balanced: coding + reasoning + chat |
| **Qwen 2.5 32B** (Alibaba) | 32B | 20 GB | Q4, Q5 | Near-GPT-4 quality, excellent function calling |
| **Qwen 2.5 72B** (Alibaba) | 72B | 40 GB | Q2, Q4 | Top-tier open weights, agentic tasks |
| **Qwen3 Coder 480B** (Alibaba) | 480B MoE | 48 GB+ | Q2 | State-of-the-art agentic coding |
| **DeepSeek V3** | 685B MoE | 32 GB+ | Q2, Q3 | Top reasoning, cheap to run via MoE sparsity |
| **DeepSeek R1** | 671B / distills | 8–40 GB | Q4 (distills) | Chain-of-thought reasoning, math, logic |
| **Mistral Small 3.1** | 24B | 14 GB | Q4, Q6 | Fast, function calling, 128K context |
| **Mistral Large** | 123B | 64 GB | Q3, Q4 | Enterprise-grade, multilingual, agentic |
| **Phi-4** (Microsoft) | 14B | 9 GB | Q4, Q6, Q8 | Reasoning punch above its weight, STEM tasks |
| **Command R+** (Cohere) | 104B | 56 GB | Q3, Q4 | RAG-optimized, 128K context, tool use |

> Distilled DeepSeek R1 variants (8B, 14B, 32B, 70B) offer strong reasoning at consumer VRAM levels.

---

## Hardware Requirements

| VRAM / RAM | Best Models | Use Case |
|------------|-------------|----------|
| **4–6 GB GPU** | Gemma 3 2B Q8, Llama 4 Scout Q4, Phi-4 Q2 | Light chat, fast responses, edge deployment |
| **8 GB GPU** | Gemma 3 9B Q4, Llama 4 Scout Q5, Qwen 2.5 7B Q8, Mistral 7B Q8 | Daily driver for coding and chat |
| **16 GB GPU** | Qwen 2.5 14B Q6, Gemma 3 27B Q4, Mistral Small Q4, Phi-4 Q8 | Strong coding, reasoning, agentic tasks |
| **24 GB GPU** | Qwen 2.5 32B Q4, Llama 4 Maverick Q4, DeepSeek R1 32B distill | Near-frontier quality for most tasks |
| **40–48 GB GPU** | Qwen 2.5 72B Q4, DeepSeek V3 Q2, Command R+ Q3 | Production-grade, multi-user serving |
| **64 GB+ GPU** | Full precision mid-size models, vLLM serving | High-throughput API servers |
| **CPU only** | Gemma 3 2B, Phi-4 Q2, GPT4All models | Air-gapped, no GPU, privacy boxes |

### Apple Silicon (M-Series) Recommendations

| Chip | Unified Memory | Recommended Models |
|------|---------------|-------------------|
| M3 / M4 (base) | 16 GB | Gemma 3 9B Q6, Llama 4 Scout Q5, Qwen 2.5 7B Q8 |
| M3 / M4 Pro | 24–36 GB | Qwen 2.5 14B Q8, Mistral Small Q4, Gemma 3 27B Q4 |
| M3 / M4 Max | 48–128 GB | Qwen 2.5 32B Q8, DeepSeek R1 32B distill Q8, Llama 4 Maverick Q4 |
| M3 / M4 Ultra | 192 GB | DeepSeek V3 Q3, Qwen 2.5 72B Q6, Command R+ Q6 |

> Ollama + llama.cpp both have excellent Metal acceleration — Apple Silicon is first-class for local AI.

---

## Quantization Guide

### Formats

| Format | Engine | Strengths | Weaknesses |
|--------|--------|-----------|------------|
| **GGUF** | llama.cpp, Ollama, LM Studio, koboldcpp | Universal, CPU+GPU, actively maintained | Slightly slower than native GPU formats |
| **AWQ** | vLLM, HF Transformers | Activation-aware, minimal quality loss | GPU-only, requires calibration data |
| **GPTQ** | vLLM, AutoGPTQ, text-gen-webui | Mature, broad support | Slightly more quality loss than AWQ |
| **EXL2** | ExLlamaV2 | Highest GPU throughput, flexible bits | Complex setup, GPU-only |
| **BitsAndBytes** | HF Transformers | Easy integration, 4/8-bit | Slower inference, research-grade |

### Quality vs Size Tradeoffs

| Quantization | Size vs FP16 | Quality Loss | Recommendation |
|-------------|-------------|--------------|----------------|
| Q2_K | ~25% | High | Last resort for extreme VRAM limits |
| Q3_K_M | ~35% | Moderate | Acceptable for very large models (70B+) |
| Q4_K_M | ~45% | Low | **Sweet spot** — default recommendation |
| Q5_K_M | ~55% | Very Low | When VRAM allows, clear quality gain |
| Q6_K | ~65% | Minimal | Near-lossless for most tasks |
| Q8_0 | ~80% | Negligible | Effectively full quality, if VRAM fits |

> Rule of thumb: prefer Q4_K_M as default, step up to Q5/Q6 if you have headroom.

---

## Local Agent Frameworks

| Framework | Stars | Language | Ollama Support | Best For |
|-----------|-------|----------|---------------|----------|
| [CrewAI](https://github.com/crewAIInc/crewAI) | 38K+ | Python | Native | Role-based multi-agent teams, easy API |
| [LangChain](https://github.com/langchain-ai/langchain) | 116K+ | Python/JS | Native | Complex pipelines, massive integration library |
| [LangGraph](https://github.com/langchain-ai/langgraph) | 19K+ | Python | Via LangChain | Stateful workflows, cyclical graphs, human-in-the-loop |
| [AutoGen](https://github.com/microsoft/autogen) | 50K+ | Python | Via OpenAI-compat | Conversational multi-agent, Microsoft research |
| [AnythingLLM](https://github.com/Mintplex-Labs/anything-llm) | 35K+ | TypeScript | Native | All-in-one: RAG + agents + chat UI, zero-config |
| [Open Interpreter](https://github.com/OpenInterpreter/open-interpreter) | 56K+ | Python | Native | Natural language computer control, code execution |
| [Aider](https://github.com/paul-gauthier/aider) | 26K+ | Python | Via Ollama | AI pair programmer, git-aware, multi-file edits |
| [Continue.dev](https://github.com/continuedev/continue) | 22K+ | TypeScript | Native | VS Code/JetBrains AI IDE extension, local first |
| [SmolAgents](https://github.com/huggingface/smolagents) | 15K+ | Python | Via HF | Minimal code agents (~1K LOC), HuggingFace ecosystem |
| [OpenHands](https://github.com/All-Hands-AI/OpenHands) | 45K+ | Python | Via Ollama | Full software dev agent, Docker isolation |
| [Dify](https://github.com/langgenius/dify) | 55K+ | Python/TS | Native | Visual workflow builder, RAG, multi-agent UI |
| [Flowise](https://github.com/FlowiseAI/Flowise) | 32K+ | TypeScript | Native | Drag-and-drop agent builder, no-code |
| [Agno](https://github.com/agno-agi/agno) | 35K+ | Python | Via Ollama | Multimodal agents, agent runtime + control plane |

### Quickstart: CrewAI + Ollama

```bash
pip install crewai crewai-tools langchain-ollama
ollama pull gemma3:9b
```

```python
from crewai import Agent, Task, Crew
from langchain_ollama import OllamaLLM

llm = OllamaLLM(model="gemma3:9b")

researcher = Agent(
    role="Research Analyst",
    goal="Find and summarize information on given topics",
    backstory="Expert researcher with attention to detail",
    llm=llm
)

task = Task(
    description="Research the latest advances in local AI models",
    expected_output="A concise summary with key findings",
    agent=researcher
)

result = Crew(agents=[researcher], tasks=[task]).kickoff()
print(result)
```

---

## Local RAG Tools

| Tool | Stars | Interface | Vector DB | Best For |
|------|-------|-----------|-----------|----------|
| [AnythingLLM](https://github.com/Mintplex-Labs/anything-llm) | 35K+ | GUI + API | LanceDB, Chroma, Pinecone | Zero-config all-in-one, multi-user workspaces |
| [PrivateGPT](https://github.com/zylon-ai/private-gpt) | 54K+ | API + UI | Qdrant | Fully local document Q&A, no leakage guarantee |
| [LocalGPT](https://github.com/PromtEngineer/localGPT) | 21K+ | CLI + Web | Chroma | GPU-accelerated, simple setup, document ingestion |
| [Khoj](https://github.com/khoj-ai/khoj) | 24K+ | Web + App | SQLite + pgvector | Personal AI assistant, notes, calendar, web search |
| [Chroma](https://github.com/chroma-core/chroma) | 18K+ | Embedded + Server | Native | Embedded vector DB, Python-native, zero infra |
| [Qdrant](https://github.com/qdrant/qdrant) | 22K+ | REST + gRPC | Native | High-performance, Rust-based, production-ready |
| [Weaviate](https://github.com/weaviate/weaviate) | 12K+ | REST + GraphQL | Native | Multi-modal, built-in vectorization, self-hosted |
| [Milvus](https://github.com/milvus-io/milvus) | 32K+ | REST | Native | Enterprise-scale vector search, GPU acceleration |

### Quickstart: AnythingLLM (Easiest Path)

```bash
# Docker one-liner — full RAG stack in 60 seconds
docker run -d -p 3001:3001 \
  -v ~/.anythingllm:/app/server/storage \
  mintplexlabs/anythinglm

# Open http://localhost:3001 → connect Ollama → upload docs → chat
```

---

## Privacy and Security

### Why Local AI Matters

| Concern | Cloud AI | Local AI |
|---------|----------|----------|
| Data leaves device | Always | Never |
| GDPR / DSGVO compliance | Complex, consent required | Inherent — no data transfer |
| HIPAA compliance | BAA required, complex | Achievable with proper infra |
| Air-gapped operation | Impossible | Native |
| Audit trail | Provider-dependent | Full control |
| Prompt injection via API | Risk of data exfil | Contained to local machine |
| Model updates you didn't ask for | Automatic | You decide |

### Air-Gapped Deployment Pattern

```bash
# 1. Pre-download models on a connected machine
ollama pull gemma3:9b
# Models stored at ~/.ollama/models/

# 2. Copy model files to air-gapped machine via USB/internal network
rsync -av ~/.ollama/models/ airgapped-host:~/.ollama/models/

# 3. Run Ollama on air-gapped host — fully offline
OLLAMA_HOST=0.0.0.0 ollama serve
```

### GDPR / DSGVO Checklist

- Data processing stays within your infrastructure (Art. 5 GDPR)
- No third-party sub-processors for AI inference
- No model training on your prompts/data
- Encryption at rest: encrypt the disk hosting model weights and vector DBs
- Logging: control what gets persisted, easy to implement right-to-erasure

---

## Quick Start Guide

### 30-Second Setup (Ollama)

```bash
# 1. Install Ollama (macOS/Linux)
curl -fsSL https://ollama.com/install.sh | sh

# Windows: download from https://ollama.com/download

# 2. Pull a model
ollama pull gemma3:9b        # 6 GB — best default choice
# ollama pull phi4           # 9 GB — strong reasoning
# ollama pull qwen2.5:14b    # 10 GB — best for coding

# 3. Start chatting
ollama run gemma3:9b

# 4. Use the OpenAI-compatible API
curl http://localhost:11434/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{"model":"gemma3:9b","messages":[{"role":"user","content":"Hello!"}]}'
```

### Agent Setup: Aider + Local Model

```bash
pip install aider-chat
aider --model ollama/gemma3:9b --no-auto-commits
```

### Agent Setup: Open Interpreter + Ollama

```bash
pip install open-interpreter
interpreter --model ollama/gemma3:9b
```

### Agent Setup: Continue.dev (VS Code)

1. Install the [Continue extension](https://marketplace.visualstudio.com/items?itemName=Continue.continue)
2. Open `~/.continue/config.json`
3. Add an Ollama provider — autocomplete, chat, and inline edits run fully local

---

## Performance Benchmarks

Approximate relative scores on common agent tasks (higher = better, community benchmarks, March 2026):

| Model | Coding | Reasoning | Chat Quality | Multilingual | Speed (tok/s, 8GB GPU) |
|-------|--------|-----------|--------------|--------------|------------------------|
| Gemma 3 9B Q4 | 7/10 | 7/10 | 8/10 | 8/10 | ~60 |
| Qwen 2.5 14B Q4 | 9/10 | 8/10 | 8/10 | 9/10 | ~35 |
| Phi-4 14B Q4 | 8/10 | 9/10 | 7/10 | 6/10 | ~30 |
| Llama 4 Scout Q4 | 8/10 | 8/10 | 8/10 | 7/10 | ~65 |
| Mistral Small 24B Q4 | 8/10 | 8/10 | 9/10 | 8/10 | ~20 |
| Qwen 2.5 32B Q4 | 9/10 | 9/10 | 9/10 | 9/10 | ~14 |
| DeepSeek R1 14B distill Q4 | 8/10 | 10/10 | 7/10 | 6/10 | ~28 |
| Gemma 3 27B Q4 | 8/10 | 9/10 | 9/10 | 9/10 | ~18 |

> Benchmarks vary heavily by task and hardware. Always test on your own use case.
> Speed measured on a single RTX 4090 (24 GB). Apple M4 Max is within 20% for most models.

---

## Related Lists

| Resource | Description |
|----------|-------------|
| [awesome-ai-agents-2025](https://github.com/e2b-dev/awesome-ai-agents) | Broad AI agents list, cloud + local, 24K+ stars |
| [awesome-agentic-coding](https://github.com/nickarls/awesome-agentic-coding) | AI coding tools, assistants, and IDEs |
| [awesome-llm](https://github.com/Hannibal046/Awesome-LLM) | LLM papers, tools, and resources |
| [awesome-local-llm](https://github.com/vince-lam/awesome-local-llms) | Focused local LLM tools comparison |
| [500-AI-Agents-Projects](https://github.com/ashishpatel26/500-AI-Agents-Projects) | Real-world agent implementations, 16K+ stars |
| [r/LocalLLaMA](https://reddit.com/r/LocalLLaMA) | 600K+ member community, hardware tips, model releases |

---

## Contributing

PRs welcome. Focus on self-hosted / local-only tools — no cloud services.
Please include: GitHub link, star count, brief description of what makes it worth adding.

See [CONTRIBUTING.md](CONTRIBUTING.md) for full guidelines.

## License

MIT — see [LICENSE](LICENSE).

---

**Star this repo** if it saved you time. [Report an Issue](https://github.com/Supersynergy/awesome-local-ai-agents/issues) | [Request a Feature](https://github.com/Supersynergy/awesome-local-ai-agents/issues/new)
