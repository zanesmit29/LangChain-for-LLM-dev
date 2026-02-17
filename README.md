# LangChain for LLM Development

A comprehensive learning repository exploring LangChain framework fundamentals through practical Jupyter notebooks. This project demonstrates core concepts of building LLM-powered applications, from basic prompt engineering to autonomous agents.

## 📋 Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [What Has Been Done](#what-has-been-done)
- [Technologies Used](#technologies-used)
- [Key Concepts & Patterns](#key-concepts--patterns)
- [Lessons Learnt](#lessons-learnt)
- [Getting Started](#getting-started)
- [Future Improvements](#future-improvements)

## 🎯 Overview

This repository serves as a practical guide to building LLM applications using LangChain. It covers the complete journey from basic model interactions to creating autonomous agents, demonstrating real-world patterns for production-ready applications.

## 📁 Repository Structure

```
LangChain-for-LLM-dev/
├── src/
│   ├── 1. LangChain Models, prompts and parsers.ipynb
│   ├── 2. LangChain Memory.ipynb
│   ├── 3. LangChain Chains.ipynb
│   ├── 4. LangChain Question and Answer.ipynb
│   ├── 5. LangChain Evaluation.ipynb
│   ├── 6. LangChain Agents.ipynb
│   ├── Data.csv (Product reviews dataset)
│   └── OutdoorClothingCatalog_1000.csv (Product catalog)
└── README.md
```

## 🚀 What Has Been Done

### 1. Models, Prompts & Parsers
**Foundation of LLM Interactions**

Built the groundwork for structured LLM communication:
- **ChatOllama Integration**: Configured and initialized local LLM with temperature control
- **Dynamic Prompt Templates**: Created reusable templates with variable substitution
- **Output Parsing**: Implemented StructuredOutputParser to convert LLM string outputs into structured dictionaries
- **Real-World Example**: Built a translator that converts pirate speak to professional English

**Key Takeaway**: Structured inputs and outputs are essential for making LLM responses programmable and reliable.

### 2. Memory Management
**Maintaining Conversational Context**

Explored different memory strategies for conversational AI:
- **ConversationBufferMemory**: Stores complete conversation history
- **ConversationBufferWindowMemory**: Maintains sliding window of last k interactions
- **ConversationTokenBufferMemory**: Limits memory based on token count
- **ConversationSummaryBufferMemory**: Summarizes older conversations to reduce token usage

**Key Takeaway**: Memory management is crucial for balancing cost (token usage) with conversation quality. Different strategies suit different use cases.

### 3. Chains
**Composing Complex Workflows**

Demonstrated how to build multi-step LLM workflows:
- **LLMChain**: Basic building block combining prompt templates with LLMs
- **SimpleSequentialChain**: Linear pipeline where output feeds into next chain
- **SequentialChain**: Multi-input/output chains with explicit parameter routing
- **RouterChain**: Intelligent routing based on query characteristics
- **MultiPromptChain**: Dynamically selects specialized chains (physics, math, history, CS)

**Key Takeaway**: Chains enable modular, reusable, and composable LLM workflows. Routing chains allow intelligent task delegation.

### 4. Question & Answer over Documents
**Retrieval-Augmented Generation (RAG)**

Implemented semantic search over document collections:
- **HuggingFace Embeddings**: Converted text into vector representations
- **DocArrayInMemorySearch**: Vector database for similarity search
- **RetrievalQA**: Combined retrieval with question answering
- **Multiple Chain Types**: Explored Stuff, Map-Reduce, Refine, and Map-Rerank approaches
- **Use Case**: Searchable outdoor clothing catalog responding to customer queries

**Key Takeaway**: RAG bridges the gap between LLM knowledge cutoffs and real-time data. Different chain types optimize for document size and accuracy trade-offs.

### 5. Evaluation
**Systematic Performance Assessment**

Built evaluation pipelines for LLM applications:
- **QAGenerateChain**: Auto-generated Q&A pairs from documents
- **QAEvalChain**: LLM-based evaluation comparing predictions to expected answers
- **Debug Mode**: Enabled langchain.debug for step-by-step execution tracing
- **Grading System**: Implemented scoring mechanism for answer quality

**Key Takeaway**: LLM-assisted evaluation (using LLMs to evaluate LLMs) provides scalable quality assessment. Debugging tools are essential for understanding chain behavior.

### 6. Agents
**Autonomous Reasoning with Tools**

Created agents that reason and act independently:
- **AgentExecutor**: Framework for autonomous tool usage with CHAT_ZERO_SHOT_REACT_DESCRIPTION
- **Built-in Tools**: Integrated Wikipedia search, llm-math calculator, Python REPL
- **Custom Tools**: Built domain-specific tools using @tool decorator
- **Error Handling**: Implemented robust error handling with handle_parsing_errors=True
- **Use Cases**: 
  - Research queries via Wikipedia API
  - Mathematical calculations
  - Python code execution for data manipulation

**Key Takeaway**: Agents represent the highest level of LLM autonomy. They decide which tools to use, when, and how to combine results—enabling complex task automation.

## 🛠 Technologies Used

### Core Framework
- **LangChain**: Main orchestration framework
  - langchain-core
  - langchain-community
  - langchain-experimental

### Language Models
- **Ollama**: Local LLM deployment (llama3:8b, llama2:7b)
- **ChatOllama**: LangChain integration for Ollama models

### Embeddings & Vector Storage
- **HuggingFace Transformers**: Sentence embeddings
- **DocArray**: In-memory vector database

### Tools & Utilities
- **Wikipedia API**: Knowledge retrieval
- **Python REPL**: Dynamic code execution
- **llm-math**: Mathematical computations

### Data Processing
- **Pandas**: CSV data manipulation
- **Jupyter Notebooks**: Interactive development environment

## 💡 Key Concepts & Patterns

### 1. Progressive Complexity
The repository follows a logical learning path:
```
Foundation (Prompts) → Memory → Composition (Chains) → 
Retrieval (RAG) → Evaluation → Autonomy (Agents)
```

### 2. Context Management
Demonstrated trade-offs between memory size and conversation quality:
- Full history vs. sliding windows
- Token-based vs. turn-based limits
- Summary compression for long conversations

### 3. Modular Design
Chains as reusable building blocks:
- Single responsibility per chain
- Composability through sequential and router patterns
- Separation of concerns (retrieval, processing, generation)

### 4. Semantic Search
Embeddings enable meaning-based retrieval:
- Vector representations capture semantic similarity
- More powerful than keyword matching
- Foundation for modern RAG systems

### 5. LLM-Assisted Workflows
Using LLMs to enhance LLM applications:
- Evaluation chains assess quality
- Summary chains compress information
- Router chains make intelligent decisions

## 📚 Lessons Learnt

### Technical Lessons

1. **Prompt Engineering is Foundational**
   - Well-structured prompts significantly improve output quality
   - Template variables enable reusability and maintainability
   - Output parsers convert strings to structured data

2. **Memory Trade-offs Matter**
   - Token costs scale with conversation length
   - Different memory strategies suit different use cases
   - Summary strategies can preserve context while reducing costs

3. **Chains Enable Complexity**
   - Breaking complex tasks into discrete chains improves reliability
   - Router chains enable intelligent task delegation
   - Sequential chains create powerful multi-step workflows

4. **RAG Extends LLM Capabilities**
   - Embeddings bridge LLM knowledge gaps with real-time data
   - Vector databases enable semantic search at scale
   - Different retrieval strategies optimize for various scenarios

5. **Evaluation is Non-Trivial**
   - LLM-assisted evaluation provides scalable quality assessment
   - Debug mode is essential for understanding chain behavior
   - Automated Q&A generation speeds up testing

6. **Agents Require Careful Design**
   - Tool selection and description quality impact agent performance
   - Error handling is critical for robust autonomous systems
   - Limiting tool access reduces failure modes

### Architectural Lessons

1. **Start Simple, Add Complexity Gradually**
   - Begin with basic LLM chains before introducing memory, retrieval, or agents
   - Test each component independently before integration

2. **Token Efficiency is Critical**
   - Every token has a cost (financial and latency)
   - Memory management directly impacts application economics
   - Compression and summarization are essential at scale

3. **Evaluation Should Be Continuous**
   - Build evaluation into the development cycle
   - Use LLMs to generate test cases automatically
   - Monitor performance as chains evolve

4. **Tools Make Agents Powerful**
   - The right tools dramatically expand agent capabilities
   - Custom tools enable domain-specific functionality
   - Tool descriptions guide agent decision-making

### Best Practices Identified

1. **Temperature Control**: Lower temperatures (0) for deterministic outputs, higher for creativity
2. **Explicit Output Schemas**: Define expected output structure upfront
3. **Error Handling**: Always implement fallback mechanisms for agent failures
4. **Debug Mode**: Use langchain.debug during development to trace execution
5. **Modular Chains**: Keep chains focused on single responsibilities
6. **Context Windows**: Monitor and manage context size proactively

## 🏁 Getting Started

### Prerequisites
```bash
# Python 3.8+
# Ollama installed locally (https://ollama.ai/)

# Install required packages
pip install langchain langchain-community langchain-core langchain-experimental
pip install huggingface-hub transformers sentence-transformers
pip install docarray wikipedia pandas jupyter
```

### Setup Ollama Models
```bash
# Pull required models
ollama pull llama3:8b
ollama pull llama2:7b
```

### Running the Notebooks
```bash
# Navigate to the src directory
cd src/

# Start Jupyter Notebook
jupyter notebook

# Open notebooks in order (1 through 6) for the best learning experience
```

### Notebook Order Recommendation
1. **Start with Models, Prompts & Parsers** - Foundation concepts
2. **Then Memory** - Understand context management
3. **Move to Chains** - Learn composition patterns
4. **Explore Q&A** - Implement RAG
5. **Study Evaluation** - Build quality assessment
6. **Finally Agents** - Achieve autonomy

## 🔮 Future Improvements

### Potential Enhancements
- [ ] Add streaming responses for better UX
- [ ] Implement persistent vector stores (ChromaDB, Pinecone)
- [ ] Explore advanced agent frameworks (LangGraph)
- [ ] Add authentication and rate limiting examples
- [ ] Demonstrate cloud LLM integration (OpenAI, Anthropic, Google)
- [ ] Build a full-stack application example
- [ ] Add unit tests for chains and agents
- [ ] Implement observability and logging best practices
- [ ] Explore multi-modal capabilities (vision, audio)
- [ ] Add production deployment patterns (Docker, API endpoints)

### Learning Extensions
- [ ] Fine-tuning examples for domain-specific models
- [ ] Advanced prompt engineering techniques
- [ ] Cost optimization strategies
- [ ] Security and safety considerations
- [ ] Scaling patterns for production workloads

## 📄 License

This is an educational repository. Feel free to use the code and notebooks for learning purposes.

## 🤝 Contributing

This repository serves as a learning resource. If you find issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

---

**Built with LangChain 🦜⛓️ | Learning by Doing 🚀**
