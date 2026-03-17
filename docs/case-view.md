# Case View — Structured Documentation

## Overview

The Case View is the primary interface for exploring legal case judgments.

---

## Table of Contents

1. Default State — Recent Judgements  
2. Case Loaded State — PDF Preview  
3. Structured View — Tab System  
   - Insights  
   - Sections Applied (Agent-powered)  
   - Arguments  
   - Evidence & Facts  
   - Precedents & Citations  
   - Metadata  
   - Court Reasoning  
   - Timeline (Agent-powered)   
4. Agent Builder Integration  

---

## 1. Default State — Recent Judgements

**Trigger:**  
User navigates to Case View without entering a CNR number or uploading a file.

![case-view](../designs/wireframes/Case_view_1.png)

### Interface Elements

#### Filter Bar

| Filter | Type | Options |
|--------|------|--------|
| Court Type | Dropdown | Supreme Court, High Court, District Court |
| Case Type | Dropdown | Civil, Criminal, Constitutional |
| Outcome | Dropdown | Allowed, Dismissed, Remanded |
| Starting Year | Year Picker | Numeric Input |
| Ending Year | Year Picker | Numeric Input |

#### Recent Case Judgements Panel

- Displays a list of recent cases  
- Clicking a case loads it into the **Case Loaded State**

---

## 2. Case Loaded State — PDF Preview

**Trigger:**  
User enters a valid CNR number or uploads a PDF.

![case-view](../designs/wireframes/Case_view_2.png)

### Case Identity Bar

| Field | Description |
|------|------------|
| CNR No. | Case reference number |
| Case Name | Full case title |
| Preview PDF | Default active view |
| Structured View | Switches to tab-based analysis |

### Behavior

- PDF preview limited to 5 pages for performance  
- Full document available via **View Full PDF**  
- Inline error displayed if CNR lookup fails  
---

## 3. Structured View — Tab System

**Trigger:**  
User clicks **Structured View**

- Replaces PDF preview with tab interface  
- Tabs represent different analytical perspectives  
- Active tab highlighted  
- Horizontal scrolling supported on smaller screens  

---

## 3.1 Insights Tab

**Purpose:**  
Provides high-level summary and key facts.

![case-view](../designs/wireframes/Case_view_Insights.png)




## 3.2 Sections Applied

**Purpose:**  
Displays all laws and sections referenced in the case.

![case-view](../designs/wireframes/Case_view_Sections_Applied.png)


### Glossary Panel - 
- **Powered by:** Agent Builder
- **Exact Text** — Original legal wording  
- **Simplifier** — Plain-language explanation  
- **Punishments** — Applicable penalties

![case-view](..designs/architecture/Agent_Builder_for_Sections_Applied.jpg)

---

## 3.3 Arguments Tab

**Purpose:**  
Displays arguments from both sides.

![case-view](../designs/wireframes/Case_view_Arguments.png)

---

## 3.4 Evidence & Facts Tab

**Purpose:**  
Provides structured evidence and factual summary.

![case-view](../designs/wireframes/Case_view_Facts_Evidence.png)

### Evidence Types

Documentary · Oral · Expert · Forensic · Digital · Physical

### Facts Panel

- Narrative summary  
- Chronological where possible
   
---

## 3.5 Precedents & Citations Tab

**Purpose:**  
Displays referenced cases and related citations.

![case-view](../designs/wireframes/Case_view_Precedants.png)

---

## 3.6 Metadata Tab

**Purpose:**  
Displays complete administrative case information.

![case-view](../designs/wireframes/Case_view_Metadata.png)

---

## 3.7 Court Reasoning Tab

**Purpose:**  
Visualizes the court’s reasoning process.

![case-view](../designs/wireframes/Case_view_CourtReasoning.png)

---

## 3.8 Timeline

**Purpose:**  
Displays chronological case progression and duration analysis.

![case-view](../designs/wireframes/Case_view_Timeline.png)

**Powered by:** Agent Builder
### Events

- Incident date  
- FIR filing  
- Hearings  
- Final arguments  
- Judgement  

### Metrics

- Total duration  
- Time between stages  
- Number of hearings
  
![case-view](..designs/architecture/Agent_Builder_for_timeline_and_case_duration.jpg)

---


## 5. Agent Builder Integration

### 5.1 Timeline Agent

| Property | Details |
|---------|--------|
| Input | Structured output from DB2 |
| Task | Extract events and compute durations |
| Output | Timeline + duration metrics |

---

### 5.2 Sections Applied Agent

| Property | Details |
|---------|--------|
| Input | Structured output from DB2 |
| Task | Extract legal sections |
| Output | Sections + explanations + punishments in simplified language|

---

## Summary

The Case View acts as the central intelligence interface of the system, transforming unstructured legal documents into structured, interactive, and analyzable insights across multiple dimensions.
