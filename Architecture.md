# System Architecture

## 1. Architectural Overview
This project is built as a **self-contained, browser-first single-page application (SPA)** inside `index.html`. Following the Vibe Sprint build rules, all user interface rendering, input validation, business logic, and sample data management run directly in the client's web browser without external servers, APIs, or authentication dependencies.

## 2. Component Structure
All application layers are organized cleanly inside `index.html`:
* **Presentation Layer (HTML5 & CSS3):** Semantic layout, responsive styling, forms, interactive controls, and visual feedback states.
* **Application & Validation Layer (JavaScript):** Event listeners, real-time form/input validation, calculations, and dynamic DOM updates.
* **Data Layer (In-Browser State):** Pre-loaded fictional mock data stored in JavaScript arrays/objects (and `localStorage`, if applicable) for instant testing.

## 3. Data Flow (End-to-End User Journey)
```text
[User Opens index.html]
        │
        ▼
[Browser Loads Fictional Sample Data & Initial UI]
        │
        ▼
[User Interacts / Submits Form] ──(Invalid Input)──▶ [Client-Side Validation Error]
        │
   (Valid Input)
        │
        ▼
[ Processes Logic & Mid-Event Twist]
        │
        ▼
[DOM Updates with Visible Result / Confirmation State]
```

## 4. Security & Data Privacy Design (OWASP Principles)
* **Zero Secrets Exposure:** No API keys, tokens, or credentials exist anywhere in the codebase.
* **Fictional Data Only:** All pre-loaded records use synthetic placeholder values—no real personal, financial, or sensitive data is stored or processed.
* **Client-Side Input Sanitization:** User inputs are validated before processing to prevent broken UI states or invalid calculations.
*