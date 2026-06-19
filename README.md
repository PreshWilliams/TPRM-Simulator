# Northwind Cinemas Ltd: Third-Party Risk Simulator

An interactive third-party risk management (TPRM) simulator with an information-security focus. It walks through the supplier-risk lifecycle for a fictional UK cinema business, Northwind Cinemas Ltd, and is built to show risk judgement, not just risk detection: how vendor risk is scored, how systemic concentration risk is exposed, and how treatment decisions are reached.

**Live demo:** https://preshwilliams.github.io/TPRM-Simulator/

## The 60-second sell

Most vendor-risk tools stop at scoring individual suppliers. This one goes further. It scores each vendor (inherent versus residual), then shows that a portfolio which looks diversified across six suppliers actually collapses onto a handful of shared fourth parties, then stress-tests that exposure with threat scenarios and records a defensible treatment decision for each. It is a compact, end-to-end demonstration of the discipline a TPRM analyst practises.

## Problem statement

A growing business signs vendors one at a time and assesses them one at a time. Each vendor can look acceptable in isolation while the portfolio quietly concentrates risk: the same cloud region, the same identity provider, the same payment rails sitting behind several suppliers at once. Vendor-by-vendor scoring cannot see that, and a single shared failure can take down services that appeared independent. This artefact makes that systemic risk visible and ties it to treatment decisions and recognised frameworks.

## What it shows

- **Portfolio (Identify and Assess):** six vendors scored on inherent risk (data sensitivity, business criticality, access level), a SIG-lite control questionnaire, and simulated OSINT-style signals, producing a residual score, a criticality tier and a residual rating. Control posture and signals are editable so you can watch the residual recompute.
- **Dependency map (Expose):** a vendor to fourth-party matrix that computes a concentration finding (AWS eu-west-2 underpins four of six vendors, including all three Critical-tier vendors). A colour-lens toggle re-tints the matrix by tier or by residual risk.
- **Scenarios (Stress-test and Decide):** three scenarios (cloud-region outage, software supply-chain compromise with a MITRE ATT&CK path, payment-processor breach with a UK GDPR Article 33/34 assessment), each producing a recommended treatment decision with rationale and a risk-acceptance note.
- **Risk register:** the consolidated analyst output: tier, inherent, residual, treatment decision, owner, review date and acceptance note.
- **Methodology and Frameworks:** the scoring model in full, and an honest mapping to the standards below.

## Frameworks mapped

- ISO/IEC 27036 (supplier relationship security)
- ISO/IEC 27001:2022 Annex A 5.19 to 5.23 (supplier security), A.5.7 (threat intelligence), A.5.30 (ICT readiness for business continuity)
- MITRE ATT&CK (the supply-chain scenario)
- NIST CSF (Identify, Protect, Detect, Respond, Recover) as a cross-reference

Indirect links are marked as indirect rather than forced.

## Synthetic data and scope

All vendors, questionnaire answers, signals and scenarios are synthetic. No real organisation is ever probed or scanned, and the application makes no calls to fetch vendor data. This is a deliberate professionalism choice: a risk artefact should never probe a real third party without authorisation. The model is deterministic and illustrative: it demonstrates a defensible scoring structure rather than predicting real-world breach probability. Anything illustrative rather than rigorous is labelled as such in the Methodology tab.

## Built with

React 18, Vite, Tailwind CSS and lucide-react. No backend, no API keys, no data network calls and no browser storage; all state is held in the client.

## Author

Developed by Presh Williams as a third-party risk management portfolio piece. Northwind Cinemas Ltd is fictional and all data is synthetic.
