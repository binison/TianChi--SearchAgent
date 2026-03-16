# 🔬 DeepSearch Agent - Tianchi Research Agent Challenge Final Round Rank 13

[![Tianchi Competition](https://img.shields.io/badge/Tianchi-Research%20Agent%20Challenge-blue)](https://tianchi.aliyun.com/)
[![Final Round Rank](https://img.shields.io/badge/Final%20Round-Rank%2013-brightgreen)](https://tianchi.aliyun.com/)
[![Platform](https://img.shields.io/badge/Platform-Alibaba%20Cloud%20Bailian-orange)](https://bailian.aliyun.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> **Tianchi Research Agent Challenge - Final Round Rank 13 Solution**
>
> A Production-Grade Multi-Agent Consensus System for Deep Research and Fact Verification with Automated Multi-Source Evidence Collection.
>
> *First-time participant in Agent competitions. Due to time constraints, used workflow instead of code flow. Future improvement: migrate to code flow for greater flexibility.*

[中文文档](./README_CN.md)

---

## 🏆 Competition Results

- **Competition**: Alibaba Cloud Tianchi - Research Agent Challenge
- **Achievement**: Final Round **Rank 13**
- **Core Solution**: Multi-Agent Consensus-based Deep Research Framework

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| 🧠 **Multi-Model Consensus** | Triple parallel reasoning with conflict detection and resolution |
| 🔍 **Multi-Engine Search** | Unified scheduling of Aliyun IQS, Google, PubMed, arXiv, Bocha |
| 📚 **Academic Validation** | Automatic detection and retrieval of scientific papers |
| 🌐 **Knowledge Graph Integration** | Baidu Baike entity extraction and verification |
| 🔄 **Iterative Deep Research** | Self-correcting loop with up to 8 validation iterations |
| ⚖️ **Evidence Weighting** | Source-based reliability grading (Official > Academic > News > Social) |
| 🎯 **Format-Aware Output** | Respects user-specified formats (numbers only, English names, etc.) |

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│                           Input Layer                               │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────────────┐  │
│  │   Question  │  │  Chat Hist  │  │      Search History         │  │
│  └──────┬──────┘  └─────────────┘  └─────────────────────────────┘  │
└─────────┼───────────────────────────────────────────────────────────┘
          │
          ▼
┌─────────────────────────────────────────────────────────────────────┐
│              Parallel Reasoning Layer (3-Way)                       │
│  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐                │
│  │ Reasoner #1  │ │ Reasoner #2  │ │ Reasoner #3  │                │
│  │(Deep Think)  │ │(Deep Think)  │ │(Deep Think)  │                │
│  └──────┬───────┘ └──────┬───────┘ └──────┬───────┘                │
│         └────────────────┼────────────────┘                        │
└──────────────────────────┼──────────────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────────────┐
│                 Consensus & Conflict Detection                      │
│  ┌─────────────────────────────────────────────────────────────┐   │
│  │                  Cross-Model Consensus                      │   │
│  │                    Arbitrator Node                          │   │
│  └─────────────────────────┬───────────────────────────────────┘   │
│                            │                                        │
│              ┌─────────────┴───────────────┐                       │
│              ▼                             ▼                       │
│    ┌─────────────────┐         ┌─────────────────────┐             │
│    │    CONSENSUS    │         │      CONFLICT       │             │
│    │ → Direct Output │         │    → Enter Loop     │             │
│    └─────────────────┘         └──────────┬──────────┘             │
└───────────────────────────────────────────┼────────────────────────┘
                                            │
                                            ▼
┌─────────────────────────────────────────────────────────────────────┐
│              🔁 Iterative Research Loop (Max 8 Rounds)              │
│                                                                     │
│  ┌─────────────────────────────────────────────────────────────┐   │
│  │  Step 1: Search Strategy Generation                         │   │
│  │  • Cross-validation queries (A vs B comparison)             │   │
│  │  • Source-tracing (official docs, papers)                   │   │
│  │  • Time alignment (latest versions)                         │   │
│  └────────────────────────┬────────────────────────────────────┘   │
│                           │                                         │
│  ┌────────────────────────▼────────────────────────────────────┐   │
│  │  Step 2: Multi-Engine Parallel Search                        │   │
│  │  ┌──────────┐ ┌──────────┐ ┌─────────┐ ┌────────────────┐  │   │
│  │  │ Aliyun   │ │  Google  │ │ PubMed  │ │     arXiv      │  │   │
│  │  │   IQS    │ │(SerpAPI) │ │ (Med)   │ │   (Papers)     │  │   │
│  │  └────┬─────┘ └────┬─────┘ └────┬────┘ └───────┬────────┘  │   │
│  │       └─────────────┴────────────┴──────────────┘           │   │
│  └────────────────────────┬────────────────────────────────────┘   │
│                           │                                         │
│  ┌────────────────────────▼────────────────────────────────────┐   │
│  │  Step 3: Evidence Extraction & Verification                  │   │
│  │  • Web content scraping (Jina AI)                            │   │
│  │  • Baidu Baike entity verification                           │   │
│  │  • Information purification (LLM-based)                      │   │
│  │  • Atomic fact extraction (JSON)                             │   │
│  └────────────────────────┬────────────────────────────────────┘   │
│                           │                                         │
│  ┌────────────────────────▼────────────────────────────────────┐   │
│  │  Step 4: Conflict Resolution & Decision                      │   │
│  │  • Weight evidence by source reliability                     │   │
│  │  • Gap analysis                                              │   │
│  │  • Continue search OR Finalize answer                        │   │
│  └────────────────────────┬────────────────────────────────────┘   │
│                           │                                         │
│                           └──────────┐                              │
│                                      │                              │
│                              ┌───────▼────────┐                     │
│                              │   Loop Check   │                     │
│                              │ • Max 8 rounds │                     │
│                              │ • finish cmd   │                     │
│                              └───────┬────────┘                     │
│                                      │                              │
│                    ┌─────────────────┼─────────────────┐            │
│                    ▼                 │                 ▼            │
│            ┌──────────────┐          │        ┌──────────────┐      │
│            │    LOOP      │◄─────────┘        │    FINAL     │      │
│            │   CONTINUE   │                   │   OUTPUT     │      │
│            └──────────────┘                   └──────────────┘      │
└─────────────────────────────────────────────────────────────────────┘
                                            │
                                            ▼
┌─────────────────────────────────────────────────────────────────────┐
│                    Final Answer Synthesis                           │
│  ┌──────────────────────────────────────────────────────────────┐  │
│  │  • Format compliance check (numbers only, English, etc.)     │  │
│  │  • Zero-fluff output (no "The answer is...")                 │  │
│  │  • Language consistent with original question                │  │
│  └──────────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 🧩 Workflow Nodes

| Node | Type | Description |
|------|------|-------------|
| `start` | Input | Receives question, chat history, search history |
| `builtin_llm_7elZ/3DOK/QjFV` | LLM | Parallel reasoning engines (with thinking mode) |
| `builtin_llm_cngJ` | LLM | Consensus arbitrator - detects conflicts |
| `python_qCQ7` | Parser | Extracts JSON decision data |
| `condition_Wrtw` | Condition | Routes to search loop or direct output |
| `loop_R4iy` | Loop | Iterative research loop (max 8 rounds) |
| `builtin_llm_WT1d` | LLM | Search strategy generator (3D verification) |
| `python_OQEC` | Tool | Bocha web search |
| `python_hoyi` | Tool | Web content fetching via Jina AI |
| `python_EjsE` | Tool | Baidu Baike entity crawling |
| `python_789c/GrFW` | Tool | Academic paper search (PubMed + arXiv) |
| `builtin_llm_bp3Y` | LLM | Decision maker (continue search / finalize) |
| `builtin_llm_3xoL` | LLM | Final answer synthesis (format compliance) |
| `python_5ciE` | Tool | Output cleaning (remove brackets/punctuation) |
| `end` | Output | Final answer delivery |

---

## 💡 Core Design Philosophy

### 1. Why Multi-Agent Consensus?

**Problem**: Single-model reasoning can hallucinate or be overconfident, making it difficult to assess output reliability.

**Solution**: 3-Model Parallel Reasoning + Arbitrator Node
- Three independent reasoners analyze the question simultaneously
- Arbitrator node detects disagreements between models
- **Consensus** → Direct output; **Conflict** → Trigger evidence collection

**Advantages**:
- Natural confidence estimation (higher consistency = higher confidence)
- Reduces false positives in fact verification
- Uncertainty automatically triggers search, no manual intervention needed

### 2. Three-Dimensional Verification Strategy

When models disagree, the system generates targeted search queries:

| Dimension | Query Pattern | Purpose |
|-----------|---------------|---------|
| **Cross-validation** | `A vs B`, `difference between X and Y` | Force search engines to find comparison pages |
| **Source-tracing** | `official documentation`, `white paper` | Find primary sources, not summaries |
| **Time-alignment** | `2025`, `latest version` | Distinguish version-specific facts |

### 3. Evidence Reliability Hierarchy

```
Official Documentation > Academic Papers > Authoritative News > General Web > Social Media
```

The decision LLM weights evidence based on source type, not just occurrence frequency.

### 4. State Accumulation Pattern

```python
# Clue accumulation (across iterations)
existing_clues + new_extracted_clues → merged_clues

# Search history (prevents redundancy)
existing_history + current_queries → merged_history

# Deduplication with order preservation (deterministic output)
```

---

## 🔧 Configuration

### Environment Variables

```bash
# Required
export DASHSCOPE_API_KEY="your-dashscope-api-key"
export ALIYUN_IQS_KEY="your-aliyun-iqs-key"

# Optional (enhanced search capabilities)
export SERPAPI_KEY="your-serpapi-key"
export BOCHA_API_KEY="your-bocha-key"
```

### Workflow Parameters

Edit `flow.dag.yaml` to customize:

```yaml
# Maximum research iterations (default: 8)
max_iterations: 8

# LLM Models used
reasoning_model: qwen3.5-plus      # Deep thinking
search_model: qwen-plus            # Search & extraction
synthesis_model: qwen3.5-plus      # Final answer synthesis

# Search limits
web_search_limit: 3                # Results per keyword
academic_search_limit: 5           # Papers per round
```

---

## 📊 Use Cases

### Case 1: Direct Consensus (No Search Needed)

```
Q: "When was the first iPhone released?"
A: 2007

Process:
• 3 reasoners independently conclude 2007
• Consensus reached immediately
• Direct output: 2007
```

### Case 2: Multi-Hop Research (Search Triggered)

```
Q: "What is the English name of the club where Arthur Miller's wife worked?"

Process:
• Reasoners identify: Arthur Miller's wife → Inge Morath
• Disagreement on workplace location detected
• Search loop activated:
  - Search: "Inge Morath workplace club"
  - Discover: Bimbo's 365 Club
  - Verify across multiple sources
• Final answer: Bimbo's 365 Club
```

### Case 3: Academic Fact Verification (Academic Search)

```
Q: "What is the number of activated parameters in DeepSeek-V3's MoE architecture?"

Process:
• Reasoners disagree (236B vs 671B)
• Trigger academic search:
  - PubMed: No results (non-medical topic)
  - arXiv: Found DeepSeek-V3 technical report
  - Extract: 37B activated parameters per token, 671B total
• Final answer: 37B activated parameters
```

---

## 🎨 Design Principles

### 1. Evidence Hierarchy
```
Official Docs > Academic Papers > Authoritative News > General Web > Social Media
```

### 2. Zero-Fluff Output
- ❌ "The answer is..."
- ❌ "According to my research..."
- ❌ "Based on available information..."
- ✅ Direct factual statements

### 3. Format Compliance
- Follow explicit format requirements ("numbers only", "English name")
- Default to question's original language
- Handle special formats ("X and Y", name formatting)

---

## 🔬 Research Methodology

### Conflict Resolution Strategy

```
When models disagree:
1. Identify the specific point of disagreement
2. Generate targeted search queries
3. Weight evidence by source reliability
4. Re-evaluate with new evidence
5. Iterate until consensus or max rounds reached
```

---

## 📁 Project Structure

```
.
├── flow.dag.yaml              # Main workflow definition (Alibaba Cloud Bailian)
├── config/
│   └── application.yaml       # Application configuration
├── python_*.py                # Tool nodes
│   ├── python_qCQ7.py        # JSON consensus extractor
│   ├── python_EjsE.py        # Baidu Baike crawler
│   ├── python_hoyi.py        # Jina AI web fetcher
│   ├── python_789c.py        # PubMed academic search
│   ├── python_GrFW.py        # arXiv academic search
│   ├── python_OQEC.py        # Bocha web search
│   ├── python_iz5n.py        # Clue merger (list version)
│   ├── python_VzdU.py        # Clue merger (string version)
│   ├── python_MSdF.py        # Search history manager
│   └── python_5ciE.py        # Output cleaner
├── README.md                  # English documentation (this file)
├── README_CN.md              # Chinese documentation
└── requirements.txt          # Dependencies
```

---

## 🔮 Future Improvements

### 1. Citation Generation
- **Current**: Evidence is used but not cited
- **Improvement**: Add inline citations `[1]`, `[2]` with reference list
- **Value**: Academic and professional use cases

### 2. Confidence Scoring
- **Current**: Binary consensus/no-consensus
- **Improvement**: Continuous confidence score (0-100%)
- **Value**: Better uncertainty quantification

### 3. Domain-Specific Adaptation
- **Current**: General-purpose design
- **Improvement**: Domain adapters (medical, legal, scientific)
- **Value**: Higher accuracy in specialized fields

### 4. Interactive Clarification
- **Current**: Fully autonomous
- **Improvement**: Ask user for clarification on ambiguous queries
- **Value**: Better handling of underspecified questions

### 5. Multi-Modal Support
- **Current**: Text-only
- **Improvement**: Image, table, chart understanding
- **Value: Handle visual information in research

### 6. Self-Evaluation Metrics
- **Current**: Fixed iteration count
- **Improvement**: Dynamic stopping based on information gain
- **Value**: Faster responses when sufficient evidence exists

### 7. Knowledge Base Integration
- **Current**: External search only
- **Improvement**: Vector database for internal knowledge
- **Value**: Faster retrieval for common topics

### 8. Parallel Search Optimization
- **Current**: Sequential LLM calls
- **Improvement**: Batch LLM inference for search strategy
- **Value**: Reduced latency

---

## 🙏 Acknowledgements

- [DashScope](https://dashscope.aliyun.com/) - LLM API provider
- [Aliyun IQS](https://www.aliyun.com/) - Web search integration
- [SerpAPI](https://serpapi.com/) - Google Search API
- [Jina AI](https://jina.ai/) - Web content extraction
- [PubMed](https://pubmed.ncbi.nlm.nih.gov/) - Medical literature database
- [arXiv](https://arxiv.org/) - Scientific paper repository
- [Bocha](https://bocha.cn/) - Chinese web search API

---

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

---

<p align="center">
  <strong>🔍 DeepSearch Agent - Evidence-Driven Truth</strong>
  <br>
  <sub>Tianchi Research Agent Challenge 2024 - Final Round Rank 13</sub>
</p>
