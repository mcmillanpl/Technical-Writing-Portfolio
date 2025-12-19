---
layout: page
title: Project Details & Documentation Strategy
---

# Project Details

## Purpose
This portfolio demonstrates a multi-disciplinary approach to technical communication, ranging from developer-facing API specifications to high-level sales enablement collateral and end-user tutorials.

---

## API Strategy and Design Choices

### **User Access API**
* **The Goal**: To automate the provisioning of user licenses and permissions within a Salesforce and Conga environment.
* **Key Design**: Standardizing the `license_type` and `permission_set` parameters ensures that external administrators can manage access without needing deep knowledge of the underlying database schema.

### **Webhook API**
* **The Goal**: To provide a push-based notification system for document lifecycle changes.
* **Key Design**: By using a subscription-based model (`POST /v1/webhooks/subscribe`), we reduce API overhead. Instead of polling for updates, the system notifies the developer immediately when a contract is signed or declined.

### **Salesforce Query and Pull APIs**
* **The Goal**: To bridge the data gap between CRM records and document templates.
* **Key Design**: I separated "Query" (for broad data fetching) from "Pull" (for specific record synchronization). This provides developers with flexibility to either search for records using SOQL or directly target a known Salesforce ID.

---

## User Education & Tutorials
These guides focus on "Day 1" user success and long-term system maintenance, translating technical features into actionable instructions.

* **Onboarding & Setup**: Designed to reduce friction during initial installation by translating complex environment prerequisites into a logical, step-by-step sequence.
* **Process Automation**: A deep dive into workflow logic, demonstrating how to bridge the gap between business requirements and system capabilities.
* **Troubleshooting**: A proactive resource that categorizes common failure points and provides prescriptive recovery steps to minimize support overhead.

---

## Sales & Marketing Collateral
These assets demonstrate the ability to shift voice and tone to support sales cycles and executive-level decision-making across different industries.

### **Industrial Specifications (SENS)**
* **The Goal**: To simplify the procurement of complex industrial engine starting systems.
* **Key Design**: Utilized a "Single Part Number" approach to highlight how prewired, factory-assembled units eliminate the need for separate battery, rack, and charger purchases.

### **Corporate Capabilities (OnX)**
* **The Goal**: To position the organization as a strategic end-to-end technology partner.
* **Key Design**: Organized services into a "Consult, Build, Transform, Support" lifecycle to define the value proposition at every stage of the client relationship.

---

## Technical Reference: Industrial Manuals & Compliance
These documents represent the final stage of the documentation lifecycle: long-term operational support and regulatory safety compliance.

### **SENS PowerCab2 Technical Manual**
* **The Goal**: To provide a definitive resource for the installation and maintenance of factory-packaged DC power systems.
* **Strategic Design**: Built to satisfy rigorous safety standards (NFPA 70/CSA C22.1). I utilized a strict information hierarchy to ensure high-voltage warnings and safety protocols are prominent, mitigating operational risk for the end-user.
* **Documentation Management**: Managed via formal Document Change Notices (DCN) and version control to ensure accuracy across long product lifecycles.

### **SuperTorque 8ZR Quick-Start Guide**
* **The Goal**: To accelerate "Time-to-Power" for field technicians.
* **Strategic Design**: Shifted from text-heavy descriptions to a visual-first layout. By using annotated engineering drawings and simplified wiring diagrams, I enabled technicians to complete complex floor mounting and AC/DC connections without needing to consult the full technical manual.