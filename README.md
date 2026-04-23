
# Enterprise AI Agent Onboarding Assistant
### SharePoint‑Grounded Self‑Learning | Microsoft Teams Access Channel

This repository documents an **enterprise AI agent** designed to support **new‑hire onboarding and self‑learning** by guiding users through internal systems, workflows, and practices using **SharePoint as the authoritative knowledge source**, with **Microsoft Teams** as a conversational access channel.

This project emphasizes **governance, safety, and enablement**, not automation-for-automation’s sake.

---

## 1. Background & Motivation

New hires often face fragmented onboarding experiences:
- Documentation exists but is hard to navigate
- Knowledge is spread across multiple SharePoint pages
- Senior staff become ad‑hoc support channels
- Learning becomes reactive instead of self‑directed

The goal was **not** to replace documentation or expertise, but to:
> Make existing, approved learning content easier to discover, understand, and navigate.

---

## 2. Solution Summary

An internal Copilot Studio agent was introduced to act as a **learning companion** that:

- Lives alongside onboarding SharePoint pages
- Guides users to relevant systems and practices
- Answers contextual “where / how / what is this” questions
- Remains **non‑advisory and non‑authoritative**

The agent complements human processes instead of bypassing them.

---

## 3. Why Copilot Studio + SharePoint

This approach was selected deliberately:

- **SharePoint** remains the single source of truth  
- **Copilot Studio** provides governed orchestration and guardrails  
- **Microsoft Teams** provides low‑friction, day‑to‑day access  

This avoids:
- Knowledge duplication
- Shadow documentation
- Unreviewed AI outputs becoming “truth”

---

## 4. High‑Level Architecture
```text
New Hire
│
├─ SharePoint Onboarding Pages (Authoritative Content)
│        │
│        └─ Grounding Source for AI Responses
│
└─ Microsoft Teams
│
▼
Copilot Studio Onboarding Agent
├─ Conversation Start (Onboarding Context)
├─ Topic‑based Navigation Logic
├─ SharePoint‑referenced Responses
└─ Safeguards & Out‑of‑Scope Handling
```

## 5. Knowledge Sources

### Primary Sources
- Internal SharePoint onboarding pages
- System documentation pages
- Process and practice references

### Knowledge Principles
- Content **is not rewritten** by the agent
- Responses guide users **back to SharePoint**
- SharePoint owners retain responsibility for accuracy

> The agent is intentionally dependent on human‑maintained documentation.

---

## 6. Agent Capabilities

- Custom onboarding greeting
- Guided system discovery
- Process navigation assistance
- Contextual “help me find” interactions
- Teams‑based conversational access

### Example Greeting

Hello! I’m the onboarding assistant.
I help new hires navigate internal systems, practices, and self‑learning resources.
How can I help today?

---

## 7. Safeguards & Responsible AI Design

This agent was explicitly designed **with constraints**.

### Guardrails include:
- Reference‑only language patterns
- No regulatory or procedural advice
- No decision recommendations
- Clear redirection to official documentation
- Graceful handling of out‑of‑scope questions

### What the agent WILL NOT do
- Interpret policy or compliance requirements
- Replace approvals or ownership
- Act as a source of truth
- Provide step‑by‑step instructions for sensitive processes

These limits are enforced via topic design and system instructions.

---

## 8. Model & Platform Considerations

- Platform: Microsoft Copilot Studio
- Model: Microsoft‑managed enterprise LLM
- Orchestration Model: Claude Sonnet 3.5
- Hosting: Power Platform environment
- Data handling: Governed by Microsoft 365 controls
- **Reasoning Engine:** Selected Claude 3.5 Sonnet for its superior performance in following complex formatting instructions and maintaining high context window accuracy during RAG retrieval.

No prompts, logs, or internal documents are exported to this repository.

---

## 9. Performance & Accuracy (Validation)

To ensure the reliability of the RAG (Retrieval-Augmented Generation) process, the agent underwent systematic stress testing:

- **Test Iterations:** 8 complete test cycles.
- **Sample Volume:** 100 diverse onboarding queries per cycle (800 total).
- **Success Rate:** Achieved an **average accuracy of 89%**.
- **Validation Method:** Responses were cross-referenced against the authoritative SharePoint source to ensure zero "hallucinations" regarding company policy.

---

## 10. Operational Fit

The agent supports:
- Asynchronous learning
- Reduced onboarding friction
- Consistent knowledge access
- Reduced dependence on senior staff for basic navigation

It does **not** eliminate the need for:
- Human review
- Formal training
- Ownership of documentation

---

## 11. Evidence & Transparency

Screenshots are provided strictly to demonstrate:
- Deployment to Microsoft Teams
- Topic structure and greeting configuration
- Use of SharePoint as a knowledge source

All evidence is redacted to avoid exposing internal data.

See `/evidence`.

---

## 12. Success Criteria (How Value Is Measured)

- Fewer onboarding clarification questions
- Faster system navigation by new hires
- Improved discoverability of SharePoint content
- More consistent onboarding experience

---

## 13. Author

**Joao Victor**  
Technical Compliance Engineer  
Focus areas:
- Enterprise AI enablement
- Compliance‑aware system design
- Knowledge architecture & automation

---

## 14. Disclaimer

This repository is for professional portfolio and educational purposes only.  
It does not include proprietary data, prompts, or internal documentation.

---

## 15. Future Roadmap

To evolve this agent from a static knowledge assistant into a proactive onboarding partner, the following enhancements are planned:

- **Multilingual Support:** Expanding the grounding source to include Portuguese and Spanish documentation for global compliance teams.
- **Sentiment & Feedback Loop:** Implementing a "Helpful/Not Helpful" rating system to automatically flag and audit low-confidence responses.
- **Proactive Check-ins:** Configuring the agent to message new hires on Day 1, Day 7, and Day 30 to guide them through specific onboarding milestones.
- **Extended Integrations:** Connecting to the company's ticketing system.

---

**[Back to Top](#1-project-overview)**
