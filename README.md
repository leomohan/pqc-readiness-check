# Quantum-Safe Readiness Check

A 10-minute self-check of an organisation's readiness for post-quantum cryptography (PQC). It asks 30 questions across six areas and returns a readiness level, a score for each area, a ranked list of gaps and a 90-day starting plan, with regulatory notes for the UAE sector the user selects.

Everything runs in the browser. There is no backend, no analytics and no data collection. Answers are kept in the browser's local storage so a user can come back to them, and can be cleared from the start page.

## Areas assessed

| Area | What it covers |
| --- | --- |
| Governance and ownership | Executive owner, policy, funding, regulatory mapping, approved transition plan |
| Cryptographic inventory | Discovery coverage, CBOMs, certificate and key management, cloud and SaaS visibility |
| Risk and data priorities | Data confidentiality lifetime, harvest-now-decrypt-later exposure, migration order, long-lived signatures, risk register |
| Crypto-agility and architecture | Configurable algorithms, design standards, HSM and KMS support, library currency, PQC size impact |
| Vendors and supply chain | Vendor roadmaps, contract clauses, payment and partner networks, long-lived devices, partner skills |
| Migration and testing | Hybrid pilots, platform PQC features, skills, test environment, progress reporting |

Each answer scores 0 to 3, and "Not sure" scores 0. An area score is its total as a percentage of the maximum, and the overall score is the average of the six area scores. Gaps are answers scoring 0 or 1, ranked by how far they are from the top score and by the weight of their area (inventory, governance and risk carry the most weight).

| Overall score | Level |
| --- | --- |
| 0 to 19 | Level 1: Not started |
| 20 to 39 | Level 2: Aware |
| 40 to 59 | Level 3: Planning |
| 60 to 79 | Level 4: Migrating |
| 80 to 100 | Level 5: Crypto-agile |

## Customise

Open `index.html` and edit the `CONFIG` block near the top of the script:

```js
const CONFIG = {
  appName: 'Quantum-Safe Readiness Check',
  publisher: 'Evanssion',                     // shown in the footer
  ctaText: '...',                             // call-to-action text at the end of the results page
  ctaButton: 'Contact Evanssion',
  contactEmail: 'marketing@evanssion.com'     // Contact buttons open an email to this address; leave empty to hide them
};
```

The Contact button sits in the sticky header on every screen. On the results page, "Discuss these results with Evanssion" opens an email pre-filled with the user's scores, which they can review before sending. Nothing is sent unless the user sends that email themselves.

The logo is `evanssion-logo.png`. Replace the file to update it.

Questions, recommendations, area weights, maturity levels and the sector regulatory notes are in the `DOMAINS`, `LEVELS` and `REG` constants in the same file.

## Publish on GitHub Pages

1. Push this folder to a GitHub repository.
2. In the repository, open **Settings > Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*, choose `main` and `/ (root)`, and save.
4. The site goes live at `https://<owner>.github.io/<repository>/` within a minute or two.

## Run locally

Open `index.html` in a browser. No build step or server is needed.

## Disclaimer

This self-check gives an indicative view of post-quantum readiness. It is not an audit or a compliance certificate. Regulatory notes reflect public information as of October 2026 and should be checked against each regulator's latest publications.
