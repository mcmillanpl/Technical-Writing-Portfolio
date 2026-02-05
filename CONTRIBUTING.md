# Technical Documentation Style Guide

This guide defines the standards for all documentation within this repository. Adhering to these principles ensures consistency, accessibility, and technical authority across both software and hardware domains.

---

## 1. Voice and Tone
The goal is to be **authoritative, helpful, and concise.**

* **Active Voice**: Use active voice to drive action.
  * *Do:* "The system triggers a webhook when the status changes."
  * *Avoid:* "A webhook is triggered by the system..."
* **Imperative Mood**: For instructions, start with a strong verb.
  * *Do:* "Connect the DC terminals."
  * *Avoid:* "The user should then connect the DC terminals."
* **Avoid Fluff**: Omit "please," "simply," or "just." Instructions should be neutral and direct.

---

## 2. Formatting & Markdown Standards
Consistency in formatting reduces cognitive load for the reader.

* **Headings**: Use sentence case for all headings (except for proper nouns).
* **Bolding**: Use **bold** for UI elements, buttons, and high-stakes safety warnings.
* **Code Spans**: Use `backticks` for file names, paths, and inline variables (e.g., `license_type`).
* **Lists**: 
  * Use **bulleted lists** for features or non-sequential items.
  * Use **numbered lists** for chronological, step-by-step procedures.

---

## 3. Domain-Specific Conventions

### Software & API Reference
* **Placeholders**: Use angle brackets for user-defined variables: `https://api.conga.com/v1/<account_id>/status`.
* **Standardization**: Refer to "endpoints," "parameters," and "payloads" consistently.
* **Code Blocks**: Always specify the language for syntax highlighting (e.g., ```csharp).

### Hardware & Industrial Reference
* **Safety Signaling**: Adhere to ANSI Z535 standards.
  * **DANGER**: High risk of death or serious injury.
  * **WARNING**: Potential risk of injury.
  * **CAUTION**: Risk of equipment damage.
* **Units of Measure**: Always provide metric and imperial equivalents where applicable (e.g., **180°C / 356°F**).

---

## 4. Terminology Management
To maintain a "single source of truth," use the following preferred terms:

| Avoid | Use Instead | Context |
| :--- | :--- | :--- |
| Folder | Directory | Version Control / CLI |
| Hit / Click | Select | UI / Documentation |
| Battery Box | PowerCab Enclosure | Product Reference |
| Hook | Webhook | API Reference |

---

## 5. Review Workflow
Before merging any documentation update:
1. **Technical Accuracy**: Verified by a Subject Matter Expert (SME).
2. **Link Integrity**: All relative paths and external URLs must be validated.
3. **Style Compliance**: Ensure the document adheres to this guide.

---
*Questions? Contact me at [mcmillan.pld@gmail.com](mailto:mcmillan.pld@gmail.com).*