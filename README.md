# LangChain Learning Repository

A hands-on learning experience exploring LangChain fundamentals through practical Jupyter notebooks. This repository helps you gain understanding of building LLM-powered applications from basic prompts to autonomous agents.

## 🎯 Purpose

This is a **learning project** designed for hands-on experience with LangChain. Work through the notebooks to understand core LLM application concepts including prompt engineering, memory management, chains, RAG (Retrieval-Augmented Generation), evaluation, and agents.

## 📚 Learning Path

The repository contains 6 progressive notebooks in the `src/` directory:

1. **Models, Prompts & Parsers** - Learn LLM basics, prompt templates, and structured outputs
2. **Memory** - Explore conversation context management strategies
3. **Chains** - Build multi-step LLM workflows and routing
4. **Question & Answer** - Implement RAG with document retrieval
5. **Evaluation** - Assess LLM application performance
6. **Agents** - Create autonomous systems with tool usage

Work through them in order for the best learning experience.

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- [Ollama](https://ollama.ai/) installed locally

### Setup
```bash
# Install Python packages
pip install langchain langchain-community langchain-core langchain-experimental
pip install huggingface-hub transformers sentence-transformers
pip install docarray wikipedia pandas jupyter

# Pull Ollama models
ollama pull llama3:8b
ollama pull llama2:7b
```

### Run the Notebooks
```bash
cd src/
jupyter notebook
# Open notebooks 1-6 in order
```

## 💡 Key Learning Takeaways

Through this hands-on experience, you'll learn:

- **Prompt Engineering**: Structure inputs and outputs for reliable LLM responses
- **Memory Management**: Balance token costs with conversation quality
- **Chains**: Compose modular, reusable LLM workflows
- **RAG**: Extend LLM knowledge with real-time document retrieval
- **Evaluation**: Assess application quality systematically
- **Agents**: Build autonomous systems that reason and use tools

## 📄 License

Educational repository for learning purposes. Feel free to use for your own learning journey.

---

**Built with LangChain 🦜⛓️ | Learning by Doing 🚀**
