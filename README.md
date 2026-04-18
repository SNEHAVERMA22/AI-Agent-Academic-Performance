

#Academic Performance Agent

An intelligent multi-agent system designed to bridge the gap between institutional data and actionable academic insights for both students and faculty.

---

##System Architecture

It is built using a **Stateful Multi-Agent Orchestration pattern**. Unlike traditional linear systems, it incorporates feedback loops to ensure data integrity before generating insights.

### Architecture Diagram
![Architecture](./docs/architecture_diagram.png)

---

##Core Components

### 🔹 Orchestration Layer (The Brain)
- Powered by **LangGraph**
- Manages conversation state
- Dynamically decides:
  - When to fetch data
  - When to generate insights

---

### 🔹 Validation Engine
- Built using **Pydantic** and **Great Expectations**
- Ensures:
  - No missing/null values
  - Data consistency before analysis

---

### 🔹 RAG (Retrieval-Augmented Generation)
- Uses **ChromaDB** for vector storage
- Connects to:
  - Academic Policy Handbook
- Ensures:
  - Recommendations align with institutional rules

---

### 🔹 Persona-Based Generator
- Dual prompting system
- Generates:
  - Student-focused insights (growth-oriented)
  - Faculty summaries (trend & intervention focused)
- Ensures compliance with **FERPA/GDPR**

---

## Tech Stack & Justification

| Technology | Role | Justification |
|-----------|------|--------------|
| LangGraph | Orchestration | Supports cyclic workflows and decision loops |
| Python (Pandas) | Data Analysis | Efficient for trend and correlation analysis |
| ChromaDB | Vector Database | Enables semantic policy retrieval (RAG) |
| FastAPI | Deployment | High-performance async APIs |

---

## Decision Stages

### 1️⃣ Discovery
- Identifies user type:
  - Student → personal insights
  - Faculty → class-level analysis

---

### 2️⃣ Verification
- Checks availability of historical data  
- If insufficient:
  - Requests additional data  
  - Avoids speculative outputs  

---

### 3️⃣ Prioritization
- Uses weighted logic to detect **Critical Gaps**  
- Example:  
  - High grades + low attendance → attendance prioritized  

---

### 4️⃣ Synthesis
- Generates:
  - Actionable student recommendations  
  - Faculty intervention summaries  

---

## 📊 Example Output

###  Student
- Improve attendance to meet minimum criteria  
- Focus on weak subjects identified via trend analysis  

### Faculty
- Identify students at risk  
- Recommend targeted academic interventions  

---

##  Why This Approach?

- Modular architecture separates:
  - Data Layer  
  - Reasoning Layer  

- Ensures scalability:
  - Database changes (SQL → MongoDB) don’t affect agent logic  

- Enables:
  - Robust, reusable, and adaptable AI system  

---

##  Future Enhancements

- Real-time dashboards  
- LMS integration  
- Predictive analytics  
- Personalized learning pathways  

---


