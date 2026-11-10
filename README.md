# NearHire (Systems Case Study & Architectural Prototype)

A lightweight recruiting operations case study and prototype designed to solve multi-unit location routing and eliminate screen-switching friction during candidate screening calls.

> **Status:** Conceptual Architecture & Operational Prototype. Built to test workflow optimization and client-side data processing for high-volume, multi-location talent acquisition.

---

## 📌 Executive Summary & Problem Statement

In distributed, multi-location retail hiring environments, identifying whether a candidate is viable for alternative nearby locations traditionally requires recruiters to juggle three disconnected tools:
1. **Spreadsheet Tracker:** Monitoring active requisition IDs, status, and recruiter notes.
2. **Mapping Tool (Google Maps):** Looking up physical store locations and proximity.
3. **Manual Navigation & Calculation:** Manually entering a candidate's ZIP code, calculating driving radius, and cross-referencing open headcount before continuing the candidate intake.

**The Impact:** This manual loop created 3 to 4 minutes of dead time per call, leading to delayed candidate follow-ups and missed opportunities to cross-recruit candidates into nearby stores with urgent hiring needs.

---

## 💡 The Solution

**NearHire** unifies location proximity and requisition availability into a single, instant lookup interface. 

Instead of switching tabs, a recruiter enters the candidate's ZIP code to immediately view nearby operating stores sorted by distance, along with active requisition titles, IDs, and statuses for each location.

---

## ⚙️ Architecture & Technical Workflow

NearHire was designed around a **client-side architecture** (zero external database or cloud server footprint), processing structured data directly in the browser environment.

## 🛠️ Technologies & Skills Applied

* **Talent Operations & Workflow Design:** High-volume recruitment workflow mapping, cross-unit candidate re-routing, and recruiter productivity optimization.
* **ATS Configuration & Data Hygiene:** Structured relational schema design (`Stores` and `Requisitions`), error reduction, and duplicate-record auditing.
* **Geospatial & Data Processing Logic:** Coordinate mapping (Geocoding), great-distance proximity calculations (Haversine formula), and client-side `.xlsx` parsing.
* **Client-Side Application Logic:** Single-page application structuring (HTML/JavaScript) with zero server-side database dependencies or external API hosting risks.
* **Data Governance & Privacy:** Air-gapped architecture enforcing strict candidate PII minimization and operational metadata isolation.

| Stage | Process | Technical Mechanism |
| :--- | :--- | :--- |
| **1. Data Schema** | Store details and role requisitions structured across dedicated workbook tabs (`Stores`, `Requisitions`). | Relational spreadsheet data modeling |
| **2. Ingestion** | Local parsing of structured datasets directly inside the browser environment. | Client-side file parsing |
| **3. Geocoding** | Translating physical store street addresses into latitude and longitude coordinates. | Coordinate mapping (Geocoding) |
| **4. Distance Logic** | Measuring straight-line geographic proximity between the candidate’s ZIP code and store coordinates. | Great-circle distance calculation (Haversine formula) |
| **5. Filtering & Output** | Dynamic rendering of locations within a user-defined radius (in miles), sorted by nearest proximity. | Array filtering & distance-based sorting |

* **Quick-Access Workflow Concept:** Designed with a companion browser action extension layout enabling recruiters to trigger the interface directly from any active ATS or sourcing tab without context switching.

---

## 🔒 Data Governance & Privacy Compliance

This system architecture was designed following strict data minimization principles:
* **Zero Candidate PII:** The framework does not ingest, process, or store candidate names, resumes, contact details, or personal records.
* **Public/Operational Metadata Only:** Operates strictly on non-confidential operational data (store addresses, public job titles, open requisition counts).
* **Air-Gapped Processing:** Designed to operate offline—no third-party data transmission or direct ATS integration risks.

---

## 🚀 Key Features & Capabilities

* **Proximity Matching:** Real-time ZIP code lookup with instant radius sorting.
* **Role-Based Filtering:** Filter proximity results by specific requisition titles or operational categories.
* **Zero Infrastructure Footprint:** Self-contained single-page application structure requiring no server setup or database maintenance.
* **Workflow Integration:** Rapid accessibility layout designed for high-volume desk environments.

---

## 📈 Measured Operational Impact (Testing Environment)

Simulated testing against baseline high-volume recruiting workflows demonstrated:
* **Time Savings:** Eliminated manual map cross-referencing, reducing workflow duration by **3–4 minutes per candidate screening call**.
* **Improved Conversion:** Enabled recruiters to recommend adjacent open requisitions in real time during initial phone intake, preventing candidate drop-off across distributed store networks.

---

## 👤 Author

**Nidhi Patel**  
*Talent Acquisition Specialist & Greenhouse ATS Administrator*  
[LinkedIn Profile](https://www.linkedin.com/in/nidhi-patel-connect/)
