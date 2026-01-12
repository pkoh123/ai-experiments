## 🏦 Bank Loan Assessment Agent

This project implements a **multi-agent AI system** for assessing bank loan applications.  
The agent is designed to simulate how different roles in a bank collaborate to evaluate a loan request, using **LangChain**, **CrewAI**, and **Retrieval-Augmented Generation (RAG)**.

The system breaks the loan assessment process into specialized agents, each responsible for a specific task, and then combines their outputs to produce a final recommendation.

---

## 🧠 Multi-Agent Design

The loan assessment workflow is implemented using three main agents:

### 1. Applicant Information Agent
**Purpose:** Collect and structure user input

- Retrieves applicant details such as income, employment, loan amount, and other relevant information  
- Ensures the data is clean and well-structured for downstream processing  

---

### 2. Risk Assessment Agent (RAG-based)
**Purpose:** Evaluate applicant risk using policy documents

- Uses **Retrieval-Augmented Generation (RAG)** to query internal policy documents  
- Assesses the applicant’s risk profile based on:  
  - Credit policies  
  - Eligibility rules  
  - Risk thresholds  
- Outputs a risk evaluation with reasoning (e.g. low, medium, or high risk)

---

### 3. Interest Rate Agent (RAG-based)
**Purpose:** Determine applicable interest rates from policy documents

- Uses **RAG** to retrieve interest rate rules and tables from policy documents  
- Calculates the appropriate interest rate based on:  
  - Loan type  
  - Risk level  
  - Policy constraints  

---

## 📊 Final Recommendation

The outputs from all agents are aggregated to generate a final decision, including:

- **Approval or rejection**  
- **Recommended interest rate**  
- **Explanation / justification**

This approach demonstrates how multi-agent systems can be used to build **policy-driven, explainable decision workflows** for financial use cases.

---

## 🔄 High-Level Flow

1. User submits loan application data  
2. Applicant Information Agent collects and structures input  
3. Risk Assessment Agent evaluates risk using RAG  
4. Interest Rate Agent retrieves and applies pricing rules using RAG  
5. System outputs final recommendation