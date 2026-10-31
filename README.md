# 🏛️ SAMARTH-APAAR: AICTE Regulation Bureau Platform
### *Automated Student Lifecycle Intake, 4-Tier Statutory Anomaly Engine & Verifiable Credential Architecture*
**Problem Statement ID:** PS 26263 | **Bureau:** AICTE Regulation Bureau • Ministry of Education, Government of India

---

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Prototype%20Complete-emerald.svg)]()
[![AICTE](https://img.shields.io/badge/AICTE-APH%20Chapter%20II%20Compliant-1D4ED8.svg)]()
[![Verhoeff](https://img.shields.io/badge/Algorithm-Verhoeff%20D5%20Mod%2010-8B5CF6.svg)]()
[![Zero Trust](https://img.shields.io/badge/Security-Ed25519%20Zero--Trust-059669.svg)]()

---

## 📌 Executive Summary & Problem Context

Under the **National Education Policy (NEP 2020)** and the **National Student Data Management** directives, technical institutions approved by the **All India Council for Technical Education (AICTE)** must enforce strict adherence to statutory intake capacities, eliminate ghost enrollments, and guarantee verifiable academic credentialing.

Historically, regulatory audits have been paper-intensive, reactive, and vulnerable to:
1. **Intake Overruns:** Institutions exceeding their approved division ceilings under the AICTE Approval Process Handbook (APH).
2. **Ghost / Concurrency Fraud:** Candidates concurrently holding full-time regular seats in multiple institutions or across state boundaries.
3. **Data Typographical Corruption:** Transposition and keystroke errors in 12-digit national student identifiers (APAAR IDs).
4. **Name Inconsistencies:** Slight naming discrepancies between high school records, college admissions, and national registries (DigiLocker / Aadhaar) stalling admissions.
5. **Degree Forgery & Slow Background Checks:** Fraudulent degrees lacking cryptographically verifiable dual identifiers (Institutional Roll Number + National APAAR ID).

**SAMARTH-APAAR** resolves these critical bottlenecks with an autonomous, mathematically rigorous, client-side regulatory management and zero-trust verification platform.

---

## 🚀 Key Modules & System Architecture

```
┌───────────────────────────────────────────────────────────────────────────────┐
│                           SAMARTH-APAAR PORTAL                                │
└──────┬──────────────────────┬───────────────────────┬───────────────────┬─────┘
       │                      │                       │                   │
       ▼                      ▼                       ▼                   ▼
┌──────────────┐      ┌──────────────┐        ┌──────────────┐    ┌──────────────┐
│  Workspace 1 │      │  Workspace 2 │        │  Workspace 3 │    │ Workspaces 4 │
│ Institutional│      │  Algorithmic │        │  Apex Bureau │    │  & 5: Degree │
│  Intake &    │───►──│  4-Tier      │────►───│  Telemetry   │    │  Studio &    │
│  Ingestion   │      │  Anomaly     │        │  Cockpit     │    │  Zero-Trust  │
│  Meters      │      │  Engine      │        │  (Charts/NBA)│    │  Verifier    │
└──────────────┘      └──────────────┘        └──────────────┘    └──────────────┘
```

### 1. Institutional Intake & Ingestion Workstation
- **AICTE Approval Process Handbook (APH) Chapter II Compliance Engine:** Real-time visual capacity gauges automatically calibrate to institution quotas:
  - **Sanctioned Approved Intake:** Base non-expandable merit quota (e.g., 120 seats).
  - **Tuition Fee Waiver (TFW 5%):** Supernumerary quota computed per Clause 2.50.
  - **Foreign National / OCI (15%):** Supernumerary quota computed per Clause 2.5.
  - **NRI Quota (Max 5%):** Subsumed within the base intake limit.
- **Pre-Flight Batch Staging Grid:** Staging table validates student records *before* final commit to the central national registry.
- **Single & Batch Onboarding:** Interactive form with live 12-digit Verhoeff badge calculation and demo autofill.

### 2. 4-Tier Algorithmic Anomaly Engine
The platform implements multi-layer automated verification that catches regulatory discrepancies at ingestion:
- **Tier 1 (Syntactic & Structural Integrity):** Dihedral Group ($D_5$) Verhoeff mod 10 permutation check catching 100% of single-digit and transposition errors in 12-digit APAAR numbers with zero network overhead.
- **Tier 2 (Statutory Capacity Enforcement):** Dynamic inequality engine enforcing $\sum E_{\text{regular}} \le I_{\text{sanctioned}}$. Instantly triggers an administrative freeze and quarantine upon detecting intake overruns.
- **Tier 3 (Cross-Institutional Concurrency Trap):** Concurrency lock matching tuple hashes $H = \text{hash}(\text{APAAR} + \text{Session} + \text{Mode})$. Prevents duplicate active full-time enrollment across colleges (e.g., simultaneous enrollment at COEP and BVCOE).
- **Tier 4 (Demographic Reconciliation):** Jaro-Winkler string similarity metric ($d_w$) automatically reconciles minor typographical variations between institutional admission records and national civil registries (DigiLocker).
- **Audit Console:** Real-time chronological audit trail capturing all system events and regulatory triggers.

### 3. AICTE Apex Regulatory Cockpit
- **National Telemetry Overview:** Live national capacity utilization (91.4%), total verified active APAAR records, flagged intake overruns, and blocked dual enrollments.
- **State-Wise Admission Density:** Comparative Chart.js bar telemetry tracking Sanctioned vs. Actual Enrolled across key states (Maharashtra, Tamil Nadu, Karnataka, Delhi NCR, Gujarat).
- **Quota Distribution Telemetry:** Dynamic doughnut chart showing Merit vs. Supernumerary quota allocations.
- **Accreditation Export:** 1-Click generation of verified institutional compliance packages for NBA (National Board of Accreditation) and NAAC Tier-1 evaluations.

### 4. Verifiable Dual-Identifier Degree Studio (Requirement 10)
- **Mandatory Dual-Identity Display:** Legally pairs the Degree Awarding Body Roll No (e.g., `BVCOE-CS-2024-042`) and the National APAAR ID (e.g., `8472-9104-3821`).
- **Cryptographic 2D QR Seal:** Generates an official QR code embedding the canonical payload hash (`SHA-256`) and Ed25519 digital signature.
- **Print-Ready Canvas:** Fully styled with `@media print` CSS rules for high-fidelity certificate printing.

### 5. Public Zero-Trust Verifier
- **Dual Verification Modes:**
  - **Live Gateway Mode:** Queries the national central registry and confirms active DigiLocker Universal Resource Identifier (`in.gov.nad:award:...`).
  - **Offline Zero-Trust Mode (Ed25519 PKI):** Verifies the authenticity and cryptographic integrity of student credentials offline without internet connectivity, utilizing embedded root public keys.

---

## 🧮 Mathematical & Algorithmic Specifications

### 1. Verhoeff Checksum Algorithm ($D_5$ Dihedral Group)
APAAR IDs use the Verhoeff algorithm based on the dihedral group of order 10 ($D_5$). It evaluates permutations over decimal digits:

$$c = \sum_{i=0}^{n-1} d(c, p(i \pmod 8, a_i)) = 0$$

- **Multiplication Table ($d$):** Non-commutative group operation on $\{0, \dots, 9\}$.
- **Permutation Table ($p$):** Applies permutations iteratively to catch adjacent and non-adjacent transposition errors:
  - Catches **100%** of single-digit transcription errors.
  - Catches **100%** of adjacent transposition errors ($ab \to ba$).
  - Catches **over 95%** of twin errors ($aa \to bb$).

### 2. Jaro-Winkler Metric ($d_w$) for Identity Reconciliation
To prevent false-positive rejections due to minor typographical differences (e.g., initials or missing middle names):

$$d_j = \frac{1}{3} \left( \frac{m}{|s_1|} + \frac{m}{|s_2|} + \frac{m - t}{m} \right)$$

$$d_w = d_j + \ell \cdot p \cdot (1 - d_j)$$

- $m$: Number of matching characters within $\lfloor \max(|s_1|, |s_2|) / 2 \rfloor - 1$.
- $t$: Half the number of transpositions.
- $\ell$: Length of common prefix at the start of string (up to 4 characters).
- $p = 0.1$: Constant scaling factor.
- **Decision Boundary:**
  - $d_w \ge 0.90$: Auto-reconciled (High Confidence).
  - $0.80 \le d_w < 0.90$: Soft warning for registrar review.
  - $d_w < 0.80$: Quarantined for physical KYC verification.

### 3. Ed25519 Cryptographic Signature Verification
Digital credential authentication utilizes asymmetric Ed25519 public-key cryptography:
- Canonical payload structured as RFC 8785 JSON.
- Signed with institutional / AICTE private key ($SK$).
- Verifiable by employers, universities, and foreign visa authorities with the root public key ($PK$) in sub-millisecond execution times.

---

## 💻 Tech Stack

| Component | Technology | Rationale |
|---|---|---|
| **Core Architecture** | HTML5 / ES6+ JavaScript | Zero external dependencies; native browser compatibility |
| **Styling & Design System** | Tailwind CSS (CDN) | Clean government portal design system (`#1E3A8A`, `#2563EB`) |
| **Iconography** | Lucide Icons | Accessible, crisp sovereign UI icons |
| **Telemetry & Visualization**| Chart.js (v4) | Responsive Canvas rendering for telemetry dashboards |
| **Dynamic QR Generation** | QRCode.js | Client-side 2D barcode generation |
| **Deployment Model** | Static Single-Page App (SPA) | Instant hosting via GitHub Pages, Vercel, or Apache/Nginx |

---

## 📂 Repository Structure

```
Samarth-Apaar/
├── index.html                 # Main application entry point (GitHub Pages ready)
├── Appar prototype.html       # Source prototype file
├── README.md                  # Comprehensive technical documentation & manual
├── LICENSE                    # MIT Open Source License
└── .gitignore                 # Standard clean gitignore
```

---

## ⚡ Quickstart & Local Setup

### Option 1: Direct Browser Launch (No Installation Required)
Simply double-click `index.html` or open it with your browser:
```bash
# Windows
start index.html

# macOS
open index.html

# Linux
xdg-open index.html
```

### Option 2: Local HTTP Server
Using Python:
```bash
python -m http.server 8000
# Open http://localhost:8000 in your browser
```

Using Node.js (`npx`):
```bash
npx serve .
```

---

## 🌐 Deploy to GitHub Pages in 30 Seconds

1. Push this repository to GitHub:
   ```bash
   git init
   git branch -M main
   git add .
   git commit -m "feat: initial commit of SAMARTH-APAAR regulatory platform"
   git remote add origin https://github.com/<YOUR_GITHUB_USERNAME>/<YOUR_REPOSITORY_NAME>.git
   git push -u origin main
   ```
2. On GitHub, navigate to **Settings** > **Pages**.
3. Under **Build and deployment** > **Source**, choose **Deploy from a branch**.
4. Select branch `main` and folder `/ (root)`, then click **Save**.
5. Your live interactive prototype will be accessible at:
   `https://<YOUR_GITHUB_USERNAME>.github.io/<YOUR_REPOSITORY_NAME>/`

---

## 🧪 Interactive Demonstration Guide (For Evaluators)

| Test Flow | How to Run | Expected System Behavior |
|---|---|---|
| **1. Compliant Batch Ingestion** | Click `Intake & Ingestion` tab > Click `Load Compliant Batch` | Pre-loads 5 candidate records, updates APH quota meters, marks all as `VALID`. |
| **2. Intake Overrun Violation** | Click `Anomaly Center` > Click `Trigger 125/120 Intake Breach` | Simulates 125 admissions for a 120-seat limit. The 5 excess students turn red with `APH Intake Exceeded`, meter turns red, and Cockpit counter updates. |
| **3. Dual Enrollment Collision** | Click `Anomaly Center` > Click `Inject Duplicate APAAR Collision` | Simulates an APAAR ID concurrently enrolled at COEP Pune attempting admission at BVCOE. Flagged as `PROVISIONAL HOLD`. |
| **4. Dihedral Checksum Sandbox** | Click `Anomaly Center` > Type in the Verhoeff Sandbox | Change any digit in `847291043821` to see immediate detection of transcription and transposition errors. |
| **5. Fuzzy Demographic Match** | Click `Anomaly Center` > Edit the names in Tier 4 | Live recalculation of Jaro-Winkler similarity coefficient ($d_w$). |
| **6. Official Degree Certificate** | Click `Dual-ID Degree (Req 10)` > Click `Print Official Degree` | Renders the tamper-evident certificate with both Roll No and APAAR ID, along with the signed QR code. |
| **7. Zero-Trust Verification** | Click `Public Verifier` > Toggle `Offline Zero-Trust` > Click `Verify` | Demonstrates cryptographic verification of the academic credential without needing an active internet connection. |

---

## 📜 Statutory Alignment & NEP 2020 Compliance

- **AICTE Approval Process Handbook (APH):** Strictly encodes Chapter II norms governing approved intake ceilings, Tuition Fee Waiver (TFW), and supernumerary admissions.
- **National Education Policy (NEP 2020):** Powers the Academic Bank of Credits (ABC) framework through authentic APAAR identity binding.
- **Information Technology Act, 2000 (Section 9A):** Incorporates digital signatures and zero-trust verification mechanisms conforming to national electronic record standards.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE) - see the LICENSE file for details.

---

<p align="center">
  <b>Built for AICTE Regulation Bureau • National Student Data Management Platform (PS 26263)</b><br>
  Developed by <b>Nishant Dattatray Gaikwad</b>
</p>
