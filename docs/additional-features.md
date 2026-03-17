# Additional Features — AI-Powered Tools

## Overview

The platform includes four specialized tools that extend the core case analysis capabilities. These tools are accessible through the persistent sidebar and are powered by either Agent Builder workflows or RealmAI.

---

## 1. Smart Legal Search

### Overview

Smart Legal Search is a semantic search engine that enables users to retrieve relevant legal cases using natural language queries. 

![Smart Legal Search](../designs/wireframes/Smart_Legal_Search.png)


#### Search Bar
- Full-width input for natural language queries  
- Example: *"corporate fraud cases involving diversion of funds through shell entities"*  
- Search button triggers the pipeline  

#### Filter Bar

| Filter | Description |
|--------|------------|
| Court | Filter by court type |
| Domain | Filter by case category |

- Filters apply only when **Apply Filter** is clicked  

- Clicking **View** opens the case in Structured View  
- An AI-generated summary is displayed below the case list  

### Agent Builder Workflow

Pipeline:  
**Start → Human Input → LLM → Direct Reply → End**

![Smart Legal Search](../designs/architecture/agent-builder-smart-legal-search.png)

- **Human Input**: Receives query and filter parameters  
- **LLM**: Performs semantic search (RAG) on MongoDB, retrieves and ranks cases, and generates summaries  
- **Direct Reply**: Renders results and related queries  

---

## 2. AI Debate Bot

### Overview

The AI Debate Bot allows users to engage in structured legal discussions with an AI that assumes a specific courtroom role. It is useful for argument testing, legal training, and exploring multiple interpretations of a case.

![AI Debate Bot](../designs/wireframes/Debate_Bot.png)

### Role Selection

| Role | Behavior |
|------|---------|
| Judge | Evaluates arguments and asks questions |
| Lawyer | Builds counter-arguments |
| Petitioner | Argues the petitioner’s side |
| Respondent | Defends the respondent |


### Chat Interface

- Central chat panel with threaded conversation  
- Starts with a role-based prompt  
- Maintains conversational context  

### Input Bar

| Element | Function |
|--------|---------|
| + Button | Attach case document |
| Text Input | Enter argument |
| Microphone | Voice input |
| Send | Submit message |


### Backend (RealmAI Doc QA)

- Ingests uploaded case documents  
- Grounds responses in actual case data  
- Role defines system prompt and response behavior  
- Uses conversation history for contextual replies

---

## 3. AI Brief Drafter

### Overview

The AI Brief Drafter generates structured, court-ready legal documents based on user inputs and case data.

![AI Brief Drafter](../designs/wireframes/Legal_AI_Drafter.png)

### Top Bar

| Element | Function |
|--------|---------|
| Search CNR | Load case data |
| Import | Upload case PDF |

| Field | Options |
|------|--------|
| Document Type | Bail application, writ petition, etc. |
| Party Representation | Petitioner, Respondent |
| Tone | Formal, Neutral, Aggressive, Conciliatory |
| Additional Instructions | Custom input |

#### Right Panel — Output

- Displays generated legal draft  
- Actions available:

| Button | Function |
|--------|---------|
| Download | Save document |
| Copy Text | Copy content |

### Backend (RealmAI Doc QA)

- Uses case data as grounding context  
- Input fields define generation instructions  
- Ensures factual accuracy from source document  

---

## 4. Case Comparator

### Overview

The Case Comparator enables side-by-side comparison of multiple legal cases. It helps identify differences in verdicts, legal reasoning, and applied laws. Data is directlt accessed from DB2

![Case Comparator](../designs/wireframes/Case_comparator.png)


### Input Bar

| Element | Function |
|--------|---------|
| Case 1 CNR | First case |
| Case 2 CNR | Second case |
| + Button | Add additional cases |
| Compare | Trigger comparison |

### Output Panels

#### 1. Verdict Comparison
- Displays outcomes side by side  

#### 2. Case Profile Comparison

| Field | Description |
|------|------------|
| Domain | Case category |
| Court | Court name |
| Filing Year | Registration year |
| Decision Year | Judgement year |

#### 3. Laws Cited Comparison
- Lists all acts and sections used  
- Highlights similarities and differences  

---

## Summary

These additional features extend the platform beyond static case analysis by introducing interactive, AI-driven capabilities. Together, they enable semantic search, legal reasoning simulation, automated drafting, and comparative analysis — significantly enhancing the efficiency and depth of legal workflows.
