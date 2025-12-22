---
layout: page
title: Project Details & Documentation Strategy
---

# Project Details

## Purpose
This portfolio demonstrates a multi-disciplinary approach to technical communication, ranging from developer-facing API specifications and software version control workflows to high-level sales collateral and mission-critical industrial manuals.

---

## API Strategy and Design Choices

### **User Access API**
* **The Goal**: To automate the provisioning of user licenses and permissions within a Salesforce and Conga environment.
* **Key Design**: Standardizing the `license_type` and `permission_set` parameters ensures that external administrators can manage access without needing deep knowledge of the underlying database schema.

### **Webhook API**
* **The Goal**: To provide a push-based notification system for document lifecycle changes.
* **Key Design**: By using a subscription-based model (`POST /v1/webhooks/subscribe`), we reduce API overhead. The system notifies the developer immediately when a contract is signed or declined.

### **Salesforce Query and Pull APIs**
* **The Goal**: To bridge the data gap between CRM records and document templates.
* **Key Design**: I separated "Query" (for broad data fetching) from "Pull" (for specific record synchronization), providing developers with the flexibility to use either SOQL syntax or direct Record IDs.

---

## User Education & Tutorials: Software & Workflows
These guides demonstrate the "Docs-as-Code" methodology and the ability to document complex development toolchains.

### **MadCap Flare & Git Integration**
* **The Goal**: To standardize how technical writing teams use version control.
* **Key Design**: I documented the end-to-end lifecycle of a MadCap Flare project, from initial SSH binding to source control binding. This ensures that documentation stays synchronized with the software release cycle.

### **C# Programming Concepts**
* **The Goal**: To provide deep-dive educational content for developers working with numerical data.
* **Key Design**: In "Advanced Operations on Numbers," I focused on technical accuracy and code readability, explaining bitwise operations and precision in a way that is accessible to junior developers while remaining useful to seniors.

---

## Sales & Marketing Collateral
These assets demonstrate the ability to shift voice and tone to support sales cycles and executive-level decision-making.

### **Industrial Specifications**
* **The Goal**: To simplify the procurement of complex industrial engine starting systems.
* **Key Design**: Utilized a "Single Part Number" approach to highlight how prewired, factory-assembled units eliminate the need for separate battery, rack, and charger purchases.

### **Corporate Capabilities**
* **The Goal**: To position the organization as a strategic end-to-end technology partner.
* **Key Design**: Organized services into a "Consult, Build, Transform, Support" lifecycle to define the value proposition at every stage of the client relationship.

---

## Technical Reference: Industrial Manuals & Compliance
These documents represent long-term operational support and regulatory safety compliance.

### **Technical Manual**
* **The Goal**: To provide a definitive resource for the installation and maintenance of factory-packaged DC power systems.
* **Strategic Design**: Built to satisfy rigorous safety standards (**NFPA 70/CSA C22.1**). I utilized a strict information hierarchy to ensure high-voltage warnings are prominent, mitigating operational risk.

### **Git Command Reference**
* **The Goal**: To provide a "cheat sheet" for internal engineering teams and beginner Git users.
* **Strategic Design**: Categorized by intent (Navigation, Workflow, Branching) to reduce cognitive load. This reference supports a modern "Docs-as-Code" workflow by bridging basic terminal navigation with advanced Git collaboration commands.