# G1 — Ethics and Indigenous professional capability (integrated reflection)

**Student:** ChengYi Li · **Student ID:** 25526411  
**Subject:** 43030 Professional Practice in Computing · Autumn 2026  
**Length:** ~1,200 words (portfolio evidence for Goal 1)

---

## 1. Purpose and scope

This reflection integrates learning from the **Working Ethically** and **Indigenous Professional Capability** modules required in my Professional Learning Plan (Assessment Task 1, Goal G1). At the start of the plan I self-assessed ethics and Indigenous capability at SFIA **Level 1 — Follow**: general awareness without formal application in IT or Indigenous contexts. G1 aimed to move toward **Level 2 — Assist** by completing both modules and documenting how ethical and Indigenous-led frameworks change how I design, describe, and ship software.

I anchor examples in my side project **SUNishop** (MERN e-commerce) because it handles user accounts, orders, and marketing copy — areas where ethical choices are visible to users and collaborators. The reflection is not a checklist of module titles; it explains what changed in my reasoning and what I will do differently as a computing professional in Australia.

---

## 2. Working Ethically — from rules to practice

The **Working Ethically** module reframed professional ethics beyond “do not copy code.” The **ACS Code of Professional Conduct** (2014) emphasises public interest, competence, honesty, and professional development. Three principles stood out for my pathway toward platform / reliability engineering:

1. **Honesty in representation** — I must not present a system as production-ready when critical paths are incomplete. On SUNishop I had previously described features in ways that implied full API integration when some flows were still UI-first. After the module I revised documentation to distinguish **“UI implemented”** vs **“API integrated and tested”**, reducing the risk that collaborators or future employers misread maturity.

2. **Competence and diligence** — Shipping fast is not the same as shipping responsibly. Ethics here connects to **G2 (cybersecurity)**: claiming “secure” without validation middleware, tests, or rate limits would violate competence. The module gave language to justify time spent on “unseen” work (input sanitisation, CI) as ethical duty to users, not optional polish.

3. **Respect for stakeholders** — E-commerce involves buyers, sellers (if expanded), and operators. Ethical practice includes clear privacy expectations, fair handling of errors (no silent data loss on checkout), and avoiding dark patterns. I reviewed SUNishop’s registration and profile fields and removed non-essential data collection ideas (e.g. optional demographic fields I had considered for “personalisation”) in favour of **data minimisation**.

**Concrete change:** Before G1 I treated ethics as compliance (“don’t plagiarise”). After G1 I treat it as **design input**: documentation accuracy, scope honesty, and security work are ethical obligations to people who trust the software.

---

## 3. Indigenous Professional Capability — implications for IT work

The **Indigenous Professional Capability** module introduced Indigenous-led frameworks for professional practice, including respect for **Indigenous data sovereignty** and the principle that Indigenous peoples should control how their knowledge and data are collected, stored, and shared (see AIATSIS resources on Indigenous protocols and data governance).

As a non-Indigenous developer building general consumer software, I do not claim expertise in Indigenous cultural protocols. The module’s relevance for my work is structural:

| Theme from module | How I apply it in IT practice |
|-------------------|-------------------------------|
| **Self-determination** | Do not design features that extract identity or cultural information without a clear, consented purpose and governance model. |
| **Data sovereignty** | Default to minimal storage; document *why* each field exists; plan deletion/export paths before adding “analytics” fields. |
| **Cultural safety in teams** | In group projects, avoid treating Indigenous topics as tick-box content; listen when Indigenous colleagues or module materials centre Indigenous voices. |
| **Representation** | Avoid stereotypical imagery or naming in product branding without community engagement — not directly an issue in SUNishop’s current scope, but relevant if I localise marketing. |

**SUNishop example:** The app stores account and order data in MongoDB. Applying sovereignty thinking does not require Indigenous-specific data fields; it requires **restraint**. I documented that SUNishop should not collect government ID, ethnicity, or location beyond what checkout needs unless a future feature has explicit user benefit and consent flow. If I later add “community” or charity features involving Indigenous organisations, the module’s lesson is to **partner and co-design**, not to ship features unilaterally.

**Broader professional identity:** Australian tech employers (including my reference roles at Google and Microsoft Australia) expect socially responsible practice. G1 positioned Indigenous capability not as a separate “soft” topic but as part of **how responsible systems are scoped** — especially when systems scale and data becomes hard to retract.

---

## 4. Integration across goals and projects

G1 connects to other plan goals:

- **G2 (Cybersecurity):** Ethical duty to protect user credentials and payment-related flows aligns with OWASP-aware design documented in [G2 — SUNishop security](../G2-cybersecurity/security-threats-and-mitigations.md).
- **G3 (Tools):** CI/CD is an ethical safeguard — automated tests reduce the chance of shipping known regressions that harm users.
- **G4 (Architecture):** Honest architecture documentation (monolith vs scale-out, paused AWS deploy when credits ended) reflects transparency about reliability limits.

Prior work on **CAKE** (RBAC, documented in [G2 — CAKE RBAC](../G2-cybersecurity/cake-rbac-baseline.md)) showed role separation; G1 added the **why** behind access control — not only “admins can delete” but “power must match accountability”.

Project context: [SUNishop profile](../../projects/sunishop.md).

---

## 5. Limitations and continued learning

I completed both Canvas modules and this reflection; I have not yet led a project with formal Indigenous community partnership. My growth area is moving from **individual ethical awareness** to **team-level practices** (ethics checkpoints in design reviews, Indigenous consultation when scope touches community data).

I will revisit ACS and AIATSIS materials when scoping new features that collect personal or cultural information, and I will keep portfolio reflections separate from product READMEs so public repos stay product-focused while coursework evidence remains traceable.

---

## References

Australian Computer Society (2014). *ACS Code of Professional Conduct*.  
AIATSIS (n.d.). Indigenous knowledge and protocols. https://aiatsis.gov.au/  
University of Technology Sydney (2026). *43030 Professional Practice in Computing* — Working Ethically; Indigenous Professional Capability (Canvas modules).
