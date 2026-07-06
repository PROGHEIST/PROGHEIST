LangChain + DRF Learning Roadmap

## Module 1: Introduction to LLMs

* What is an LLM?
* Tokens
* Context window
* Prompt vs Completion
* Chat Models
* OpenRouter overview
* Choosing the right model
* Temperature, max tokens, top_p

**Practice**

* Your first `llm.invoke()`

---

## Module 2: LangChain Basics

* Install LangChain
* `ChatOpenAI`
* `AIMessage`
* `invoke()`
* `stream()`
* Environment variables
* Model parameters

**Practice**

* Build a simple AI chatbot in Python

---

## Module 3: Prompt Templates

* Why prompt templates?
* `ChatPromptTemplate`
* Variables
* System messages
* Human messages
* AI messages
* Prompt engineering basics

**Practice**

* AI blog title generator

---

## Module 4: LCEL (LangChain Expression Language)

* What is LCEL?
* `|`
* Chains
* Runnable objects
* `invoke()`
* `batch()`
* `stream()`

**Practice**

* Blog summary generator

---

## Module 5: Output Parsers

* Why parse outputs?
* `StrOutputParser`
* JSON output
* Structured outputs
* Pydantic models

**Practice**

* Return blog data as JSON

---

## Module 6: Building AI APIs with DRF

* Project structure
* Organizing AI code
* `llm.py`
* `prompts.py`
* `APIView`
* `ViewSet`
* Error handling

**Practice**

* AI API endpoint

---

## Module 7: Chains

* Sequential chains
* Multi-step workflows
* Passing outputs between steps

**Practice**

* Blog → SEO title → Meta description

---

## Module 8: Memory

* Conversation history
* Chat history
* Session-based memory

**Practice**

* Chatbot API

---

## Module 9: Document Loaders

* PDF
* DOCX
* TXT
* CSV
* Web pages

**Practice**

* Read a PDF and answer questions

---

## Module 10: Text Splitters

* Why chunk documents?
* Chunk size
* Chunk overlap

**Practice**

* Split large documents

---

## Module 11: Embeddings

* What are embeddings?
* Vector representations
* Similarity search

**Practice**

* Compare two documents

---

## Module 12: Vector Databases

* Chroma
* FAISS
* PGVector
* Storing embeddings

**Practice**

* Save and search documents

---

## Module 13: Retrieval (RAG)

* What is RAG?
* Retriever
* Context injection
* Retrieval chain

**Practice**

* Chat with your own PDF

---

## Module 14: Tools

* What are tools?
* Custom Python functions
* Tool calling

**Practice**

* Calculator tool
* Weather tool (mock)

---

## Module 15: Agents

* What is an agent?
* Agent execution flow
* ReAct pattern
* Tool selection

**Practice**

* AI assistant with tools

---

## Module 16: Streaming Responses

* Streaming tokens
* Streaming in DRF

**Practice**

* Live AI response endpoint

---

## Module 17: Async LangChain

* Async models
* `ainvoke()`
* Async views

**Practice**

* High-performance AI API

---

## Module 18: AI Blog Generator Project

Features:

* Generate title
* Generate content
* Generate tags
* Generate slug
* Generate SEO metadata
* Estimate reading time
* Return JSON to DRF
* Save to PostgreSQL

---

## Module 19: AI CareerViQ Project

Build an AI service for your CareerViQ project:

* Blog generation
* Resume analysis
* Career roadmap
* Interview questions
* Skill recommendations

---

## Module 20: Production Best Practices

* Project structure
* Rate limiting
* Caching
* Logging
* Cost optimization
* Error handling
* Model fallback
* Security

---

# Final Capstone Project

You'll build a complete AI backend with DRF that includes:

* Authentication
* Blog generation
* JSON responses
* RAG over documents
* Agent with tools
* Conversation memory
* PostgreSQL storage
* Async endpoints
* Production-ready architecture

---
