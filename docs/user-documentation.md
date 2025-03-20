# Alis User Documentation

## 1. Introduction
### What is Alis?
Alis is an **AI-driven development assistant** designed to help software engineers **write, refine, and review code and documentation** with structured, logical processes. Unlike standard AI models that provide unstructured responses, Alis ensures **controlled refinements, self-critiquing, and dependency tracking** for code and documentation. 

### Why Was Alis Created?
Alis was developed to address the **limitations of standard AI-driven development assistants** by introducing a **structured workflow** for software engineering tasks. It is built with a focus on **precision, transparency, and user control**, ensuring that users retain **full decision-making authority** over changes.

### How Is Alis Different From Standard GPT Models?
Unlike generic AI models that provide **open-ended answers**, Alis is optimized for structured **code editing, debugging, refactoring, and document-based guidance.** Key differences include:
- **Explicit user confirmations** before making changes.
- **Self-critiquing before proposing refinements.**
- **Step-by-step structured refinements instead of full overwrites.**
- **Trade-off analysis in recommendations instead of single-solution answers.**
- **Prevention of unintended modifications by always seeking clarification.**

---

## 2. Key Capabilities
### Chatbot-Style Guidance (`@guide` Mode)
Alis provides structured programming advice, best practices, and general development guidance. Unlike a free-form chatbot, Alis:
- **Balances depth and conciseness** based on user intent.
- **Handles multi-part questions logically**, ensuring a structured response.
- **Asks for clarifications when needed**, but avoids unnecessary redundancy.
- **Does not assume user intent**—instead, she verifies before making recommendations.

### Document-Based Assistance (`@design`, `@feature` Mode)
Alis refines and maintains structured documents, such as:
- **Architecture plans, technical documentation, and feature blueprints.**
- **Dependency-aware modifications** to prevent broken documentation.
- **Multi-step refinements that require explicit confirmation before proceeding.**
- **Section-by-section comparisons for full document rewrites instead of full replacements.**

### Code Editing & Refactoring (`@code` Mode)
Alis provides **step-by-step guidance** for modifying code, debugging, and refactoring. Her capabilities include:
- **Guiding users through changes instead of applying edits automatically.**
- **Ensuring refactors do not introduce unintended side effects.**
- **Debugging by asking for logs and error messages before suggesting fixes.**
- **Generating structured inline or block comments for documentation.**

---

## 3. Concept & Core Principles
### Maintaining Structure & Logical Consistency
- **Alis ensures refinements are structured, step-by-step, and logically consistent.**
- **She never assumes user intent and always asks for confirmation before modifying documents or code.**

### Explicit Confirmation Handling Before Refinements
- **Alis does not apply modifications without user approval.**
- **For multi-step processes, she pauses and waits for user confirmation before continuing.**
- **Users can batch-approve minor refinements to avoid excessive confirmation steps.**

### Self-Critiquing for Transparency
- **Before presenting a change, Alis critiques her own recommendations, highlighting trade-offs and potential drawbacks.**
- **If multiple approaches exist, Alis provides comparisons instead of assuming the best option.**

### Prevention of Full Code Dumps
- **Alis does not provide full code dumps after refinements.**
- **Instead, she explains changes step by step, allowing the user to apply them manually.**

### Dependency Impact Analysis Before Large-Scale Changes
- **Before modifying a document or codebase, Alis identifies and presents all affected dependencies.**
- **Users confirm which dependencies should be updated before any modifications occur.**

---

## 4. User Flow & Interaction Model
### Step-by-Step Workflow for Refinements
1. **User submits a request (e.g., "Refactor this function for efficiency").**
2. **Alis critiques the request (if necessary) and provides multiple refinement options.**
3. **User selects an option or requests further clarification.**
4. **Alis guides the user through step-by-step modifications, requiring confirmation at each step.**
5. **If dependencies are detected, Alis lists them and asks the user how to proceed.**
6. **User completes the refinement process and approves the final version.**

---

## 5. Why Alis Is More Powerful Than Standard GPT for Code Work
### 1. Structured Critique Format for Better Clarity
✅ **Alis follows a predictable critique structure**, making it more transparent and user-friendly than standard GPT:
- **✅ Strengths:** Highlights what works well.
- **⚠️ Issues & Considerations:** Identifies areas for improvement.
- **💡 Trade-Offs & Alternatives:** Presents options with pros and cons.
- **🛠️ Next Steps:** Asks the user how to proceed instead of assuming changes.

### 2. Step-Based Refinement Instead of Full Overwrites
- **Alis never replaces code or documents outright.**
- **All modifications happen in an iterative, user-controlled process.**

### 3. Trade-Off Analysis Instead of One-Size-Fits-All Solutions
- **Alis presents multiple solutions and explains their pros and cons.**
- **Standard GPT typically provides only one "best" answer without trade-offs.**

### 4. Context Awareness for Long-Term Refinements
- **Alis remembers prior steps in a session, ensuring refinements remain logically consistent.**
- **Standard GPT treats most interactions as isolated responses.**

### 5. Dependency-Aware Modifications
- **Alis detects and manages dependencies before making changes.**
- **Standard GPT does not perform dependency impact analysis.**

---

## 6. Strengths & Weaknesses
### ✅ **Strengths**
- Highly structured and logically consistent.
- Prevents unintended modifications with explicit confirmation handling.
- Ensures functional consistency before modifying code.
- Offers multi-step refinements instead of overwhelming the user.

### ⚠️ **Weaknesses**
- Slower than fully automated GPT-based AI.
- Requires explicit user confirmation for every step.
- Does not adapt to the user's tone or personality.
- Not ideal for brainstorming or open-ended ideation.

---

## 7. Frequently Asked Questions (FAQs)
**Q: How do I ask Alis to critique my code?**
- Use `@review` or explicitly ask for a critique.

**Q: What happens if I modify my request mid-process?**
- Alis pauses, confirms whether to integrate the change, and adjusts the refinement accordingly.

**Q: Can Alis fully rewrite a document?**
- Yes, but refinements are reviewed section-by-section before finalizing.

---

## 8. Conclusion
Alis is a **structured, step-by-step AI assistant** designed for **software engineers** who need **controlled refinements, in-depth critiques, and dependency-aware modifications.**

By prioritizing **transparency, logical consistency, and user control**, Alis provides a **more reliable alternative to standard GPT models** for software development tasks.
