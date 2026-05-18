---
name: pdm-playbook
description: Produce a v0.1 strategy brief for a new business or product idea using a personal product-management playbook that combines a structured business-plan template (Situational Analysis → Strategic Alternatives → Selected Strategy → Marketing Mix → Appendix) with frameworks from Crossing the Chasm (Geoffrey Moore) and Competitive Strategy (Michael Porter). Use this skill whenever the user is sketching a new business or product idea — concrete signals include "I have an idea for...", "let's plan a new product", "thinking about a startup", "should I build X for Y", "help me think through this venture", "business plan for...", "strategy brief for...", "do an STP analysis", "let's lean-canvas this", or when the user has shared customer-discovery interviews and asks how to synthesize them. The skill produces a working-draft markdown brief that walks the full template: Objectives, Situational Analysis (SWOT, Structural Gaps, Competition Set with Porter Five Forces, Customers with Empathy Templates and JTBD/Pains/Gains, Hypothesis Tracking), three Strategic Alternatives, a Selected Strategy with full STP and 4 P's Marketing Mix, and an Appendix containing Financial Analysis, Monitors and Controls, Contingency Plans, Lean Canvas, Business Model Canvas, Market and Product Requirements, Marketing Strategy, Sales Plans, and Production Plans. Best applied to early-stage ideas; the brief is a thinking tool, not a polished investor deck. Apply this skill even when the user does not name the playbook explicitly — any time they want to think through a new product or business is the right moment.
---

# PdM Playbook

A skill for producing a v0.1 strategy brief for a new business or product idea. The brief is built on a structured template that combines:

- A practitioner-grade business-plan structure (Objectives → Situational Analysis → Strategic Alternatives → Selected Strategy → Marketing Mix → Appendix)
- Crossing the Chasm (Geoffrey Moore) — Whole Product Model, Technology Adoption Life Cycle, Competitive-Positioning Compass
- Competitive Strategy (Michael Porter) — Five Forces, Competitor Analysis framework, Wheel of Competitive Strategy
- An empathy-template format for customer analysis with prescribed adjective and noun vocabulary
- Lean Canvas and Business Model Canvas as one-page compressions

## When to use

Trigger whenever the user is sketching a new business or product idea. Concrete examples:

- "I have an idea for a CRM for X."
- "Let's plan a new product for Y."
- "I'm thinking about a startup that does Z."
- "Help me think through this venture."
- "Should I build X for Y customer?"
- "Write a business plan for..."
- "Make a strategy brief for..."
- "Lean canvas this idea."
- "Do an STP analysis on this."

Also trigger when the user has shared customer-discovery interviews, user-research notes, or competitor analysis and asks how to synthesize them into a plan.

Do NOT trigger for: features within an existing product, technical design decisions, marketing collateral, financial-model spreadsheets alone, or one-off questions about a single framework ("explain Porter's Five Forces" is not a trigger).

## What this skill produces

A single markdown file, typically `Business-Plan-v0.1.md` or `<idea-name>-v0.1.md`, containing a working-draft strategy brief. The brief is a thinking tool, not an investor pitch.

Optionally, on request, produce a short companion `STRATEGY.md` (1-2 pages) for engineering / partner audiences that strips competitive analysis and internal observations. See "Sharing-safe extract" below.

## Core philosophy

The template is a checklist that forces completeness, not a form to fill in. Each section should produce real insight, not bullet points dressed up as analysis. If a section cannot be filled with something specific, write "Open question — needs validation" and move on. Hypothesis Tracking is one of the most valuable sections — it scopes the next phase of customer discovery.

Four commitments that hold the brief together:

1. **Honest hypothesis posture.** Mark numbers as hypotheses. Mark training-derived content as hypothesis. The reader should be able to tell what is known from what is guessed.
2. **Insight before features.** The Structural Gaps sub-section (what makes the incumbent ecosystem exist) is the most valuable analytical move. Earn the right to talk about product by getting this right first.
3. **Three real alternatives, then pick.** Generating three substantively different strategies forces you to consider the second-best option you're rejecting — and to defend why your pick wins.
4. **Working-draft, not polished pitch.** Label as v0.1. Ship to iterate, not to impress.

## Process

### Before drafting

- If the user has shared customer-discovery material (interview notes, user research, sales call transcripts), read it first. Pull insights directly from it. Do not paraphrase past the point of recognition.
- If the audience, depth, or format is ambiguous, ask 1-3 focused clarifying questions via AskUserQuestion. Typical defaults: audience = founder / co-founders; depth = ~12-page strategy brief; format = markdown.
- Decide whether the brief is for a new business idea, a new product within an existing company, or a customer-discovery synthesis. Adjust language accordingly.

### Drafting

Walk the sections in order. Each section is meant to be falsifiable.

---

## Section guide

### Title

Working title for the idea. Add a small header block below: Status (Working draft), Audience, Method (which playbook frameworks are applied), Date.

### Objectives

What the company / product exists to do. Three short statements in plain language:

- **What** — what we are building, in one sentence.
- **How** — the mechanism that makes the what possible.
- **Why** — the human or commercial reason it matters.

Pull from any user-provided source material. If none, ask the user before generating.

---

### Situational Analysis

#### Summary

Three paragraphs. (1) What we are building and for whom, in one sentence. (2) The core structural insight that justifies this company existing. (3) The beachhead, and the compelling reason a beachhead customer would buy.

#### SWOT

Two sub-sections — keep the focus on the external forces, not internal feelings:

- **Tail Winds** — what's pushing this market in our direction (regulatory shifts, technology curves, demographic changes, capital availability). One paragraph.
- **Head Winds** — what's pushing against (procurement friction, regulatory caution, switching costs, founder credibility gap). One paragraph.

#### Structural Gaps — most valuable section

Look for the *compounding structural reasons* the market exists today. This is the heart of the brief. Ask:

- What does the incumbent ecosystem (consultants, agencies, manual workflows, spreadsheets) do that software doesn't?
- Why does that ecosystem exist? What rule, regulation, skill gap, or coordination failure prevents the obvious software solution from already existing?
- Are there *two or more* structural conditions that compound? (One alone is rarely enough to sustain an ecosystem.)
- What does software that respects these conditions actually look like?

State each gap (number them — Gap 1, Gap 2, Gap 3), then write a "how the gaps compound" paragraph that shows them interacting. Close with a "strategic implication" that names what the product's defensibility actually is (rarely the technology; usually a curated content / coaching / translation layer that depends on the gaps).

#### Competition Set

##### Industry Forces (Porter's Five Forces)

One paragraph per force, specific to this market. Each paragraph should end with an implication, not just an observation.

##### Suppliers

Who supplies inputs to this market and what's their leverage? (Cloud infra, content licensors, trainers, distributors, data providers.)

##### Substitutes

The biggest substitute is almost always *the status quo* (binders, spreadsheets, phone calls) or a *human service* (consultant, agency). Name both.

##### Buyers

Their leverage today, their leverage at scale, what reduces buyer power over time (switching cost, embedded data).

##### Perceptual Mapping

Pick two attribute axes that matter to the customer (avoid generic axes like "easy / hard"). Plot known players in a small table. Identify the unoccupied corner. Note explicitly that the table needs primary validation.

##### Competitor profiles (Porter's Competitor Analysis framework)

For each serious competitor (1-2 fully, others stubbed): Future Goals, Current Strategy, Assumptions held (about themselves and the industry), Capabilities, Vulnerability, What Provokes Retaliation. Consider whether some "competitors" are actually partner candidates — that's a real strategic move (consultants in regulated industries, OEMs, agencies, system integrators).

#### Customers

##### Personas

Cover every actor named in source material. Each persona: name, role, age, plausible circumstance, the structural reason they're stuck, the specific reason they would buy. Make the description concrete enough that a stranger could pick this persona out of a lineup.

##### Empathy Template

Fill in for *every* persona named above. Use this exact format:

> {Who is impacted, plural} really feel {Empathy Adjective} at the {Place of the experience} during {process name}. All too often, {what happens in a time during the experience} leads to {a bad outcome}, of course, {Someone responsible for the process} {Empathy Action} {something a person can do to fix a problem} to {a bad outcome}, but it still leaves {who is impacted} with a sense of {empathy noun}.
>
> Making things even more challenging, leaders focused on {relevant outcome} have to keep in mind {an external factor or internal factor} which also exacerbates this situation because of {what links to the situation}.

The compound paragraph is what surfaces second-order pain. Don't skip it.

**Empathy Adjective vocabulary** (pick one per persona, or substitute a close synonym):
Frustrated, Angry, Stressed, Impatient, Anxious, Disappointed, Trapped, Empty, Abandoned, Lost, Confused, Cheated, Misled.

**Empathy Noun vocabulary** (matching the adjective in the second clause):
Frustration, Anger, Stress, Impatience, Anxiety, Disappointment, Emptiness, Abandonment, Loss, Confusion, Unfairness, Annoyance.

##### JTBD / Pains / Gains

Per persona, three short lists:

- **Jobs to be Done** — the functional, emotional, and social jobs they're hiring a product to do.
- **Pains** — what's hard, slow, embarrassing, or risky in the current solution.
- **Gains** — what success looks like, beyond just "less pain."

##### Technology Adoption Life Cycle placement

Place each persona on the TALC curve: Innovators / Tech Enthusiasts, Early Adopters / Visionaries, Early Majority / Pragmatists, Late Majority / Conservatives, Laggards / Skeptics. Name "the chasm" explicitly (between Visionaries and Pragmatists). State which segment v1 must serve and what would make Pragmatists comfortable in v2.

#### Hypothesis Tracking

A numbered list of every claim in this Situational Analysis that is *hypothesis*, not *evidence*. Each entry: short statement of the hypothesis, what would falsify it, what the next discovery action is. The brief is not allowed to advance past Strategic Alternatives without listing its hypotheses honestly.

---

### Strategic Alternatives

Generate **three substantively different strategies**, not three variations of one. The point is to consider the second-best option you're rejecting. Common kinds of forks:

- Direct-to-customer vs. channel-partner-led.
- Vertical specialist vs. horizontal generalist.
- Self-serve SaaS vs. high-touch services first.
- License existing content vs. build proprietary content.
- Bootstrap vs. raise vs. grant-funded.

For each Strategy (1, 2, 3): one paragraph on the bet, one paragraph on why it could win, one paragraph on what makes it hard or wrong.

---

### Selected Strategy: {Name}

Lead with one paragraph: which alternative you picked and why, in plain language. Then walk the operational implications.

#### Segmentation

Decompose the addressable market into segments. Don't just split by industry — split by buying motion, urgency level, regulatory posture, technical maturity, or whatever axis actually matters to the decision to buy.

#### Targeting

Pick the beachhead segment. Name one specific beachhead pin (narrow enough that word-of-mouth works), justify in 2-3 bullets, then list 2-5 adjacent pins in order with a one-line rationale each (the bowling-pin sequence). State the rule: do not jump pins until prior ones are repeatable, profitable, and referenceable. Connect to the TALC placement above: v1 serves Visionaries; v2 must serve Pragmatists.

#### Positioning

Start with a one-sentence positioning statement using the classic template:

> For {target customer} who {has need / problem}, the {product name} is a {product category} that {key benefit}, unlike {primary alternative}, which {key drawback}.

Then place the position on the **Competitive-Positioning Compass**: Specialist↔Generalist × Technology↔Market, with Supporters at top and Skeptics at bottom. State the starting quadrant and the 18-month strategic move (typically "crossing the chasm" diagonally from Specialist/Technology to Specialist/Market). Name what pulls toward Supporters and what risks pulling toward Skeptics.

#### Marketing Mix (4 P's + Proof)

##### Product / Services

Apply the **Whole Product Model** (Crossing the Chasm), four layers:

- **Generic product** — the raw SaaS / hardware / service.
- **Expected product** — what the customer assumes is already included.
- **Augmented product** — what makes it actually adoptable. **Tag each item to which Structural Gap from the Situational Analysis it attacks.** This forces consistency between strategy and product.
- **Potential product** — where it eventually goes.

Name the core differentiator explicitly — the one item that no incumbent has.

##### Price

Pricing model, list price hypothesis, basis (per-user, per-establishment, per-transaction, flat). Mark as hypothesis until validated by 20+ conversations.

##### Place

Distribution channels. Direct sales, self-serve, channel-partner, marketplace listing, retail. State which channels are v1 vs. later.

##### Promotion

###### Value Props and Messaging

Three message pillars and the audience each is aimed at. Use plain language; if a sentence requires industry jargon, that's a signal it isn't sharp yet.

##### Proof

###### Programs & Tactics & Demos

What earns trust before purchase. Case studies, pilots, free trials, certifications, demos, references, public-sector partnerships, security disclosures. Each item is a specific *thing to produce*, not an aspiration.

#### Wheel of Competitive Strategy — consistency check

Per Porter, a Goal in the center with functional spokes around it. State the goal first (revenue, growth, secondary objectives — be specific). Then write 1-3 sentences per spoke and confirm each is consistent with the goal:

- Product Line
- Target Markets
- Marketing
- Sales
- Distribution
- Manufacturing / Engineering
- Labor / Hiring
- Purchasing
- R&D
- Finance & Control

If any spoke contradicts the goal, the strategy is broken and one of them must change. This section is a consistency check, not new content.

---

### Appendix

#### Financial Analysis

##### Market Sizing (TAM / SAM / SOM)

Order-of-magnitude estimates only. Each number needs a "validate against [source]" caveat. Never present unsourced numbers as fact.

##### Budgets

Twelve-month operating budget. Headcount, infrastructure, content licensing, marketing, sales tooling. Each line a working assumption.

##### Pro Forma Statements

Year 1-3 simplified P&L (revenue, gross margin, operating expense, EBITDA-ish). Mark every line as hypothesis.

#### Monitors and Controls

What you will measure monthly to know if the strategy is working. Three categories:

- **Leading indicators** — conversations, trials, pipeline.
- **Trailing indicators** — paying customers, retention, gross margin.
- **Strategic tripwires** — conditions that would force a strategy review (e.g., "if by month 6 the consultant channel hasn't produced 5 introductions, the channel hypothesis is wrong").

#### Contingency Plans and Other Docs

For each Strategic Tripwire above, a one-paragraph contingency: what we would do instead.

#### Lean Canvas

The nine-block Lean Canvas (Ash Maurya), as a markdown table:

| **Problem** (top 3) | **Customer Segments** (target + early adopters) |
| **Unique Value Proposition** (one compelling sentence) |
| **Solution** (top 3 features) |
| **Channels** | **Revenue Streams** |
| **Cost Structure** | **Key Metrics** | **Unfair Advantage** |

Each block one to three lines. Cross-check that the Lean Canvas is consistent with the longer Situational Analysis and Selected Strategy — if they disagree, the canvas wins as the compressed truth, and the long sections need to be updated.

#### Business Model Canvas

The nine-block Business Model Canvas (Osterwalder), as a markdown table:

| **Key Partners** | **Key Activities** | **Value Propositions** | **Customer Relationships** | **Customer Segments** |
| (same row, continued) | **Key Resources** |  | **Channels** | (same row, continued) |
| **Cost Structure** | (continued) | **Revenue Streams** | (continued) | (continued) |

Use the Business Model Canvas for partnership / enterprise conversations where Key Partners and Key Activities matter more than the Lean Canvas's emphasis on Unfair Advantage and Key Metrics.

#### Market Requirements

External-facing requirements: what the market expects from a credible entrant in this category. (E.g., "SOC 2 Type I within 12 months," "HIPAA-aligned data handling," "USDA-acknowledged content library.")

#### Product / Services Requirements

Internal-facing requirements: what we must build / source / partner for to meet the Market Requirements.

#### Marketing Strategy

How the messaging from the Promotion section translates into a 6-12 month plan: content production cadence, channel investments, event presence, partnerships.

#### Sales Plans

##### Sales Guide

How a salesperson should run a first conversation: discovery questions, qualification criteria, sequence of asks.

##### Objection Handling

The five most likely objections and the prepared response to each. Include the objection we don't yet have a good answer for — that's another open question.

##### Sales Aids

Decks, demos, one-pagers, ROI calculators, case studies — list what exists vs. what needs to be produced.

#### Production Plans

How the product is built, delivered, and supported. Engineering roadmap (v1 → v1.5 → v2), supply chain (if physical), service-delivery operations (if services), customer-success motion.

#### Glossary

Domain-specific terms that aren't widely known.

#### Template-to-Section map

A small table mapping each playbook checklist item (Empathy Template, Porter's 5F, Whole Product Model, etc.) to the section in the brief where it appears. Forces completeness.

---

## Verification pass

After drafting, run a self-verification pass *before* showing the brief to the user:

1. Cross-check every claim about the domain against any user-provided source material. Flag drift in the response — don't silently smooth it over.
2. Confirm every section in the template has been written (not just headed).
3. Look for numbers presented as fact when they are hypotheses. Add validation caveats.
4. Confirm every Augmented Product item tags to a Structural Gap.
5. Confirm every actor named in the source material has both a Persona and an Empathy Template.
6. Confirm the Lean Canvas and Business Model Canvas are consistent with the long-form Situational Analysis and Selected Strategy.
7. Confirm at least three Hypothesis Tracking entries exist, each with a falsification condition.

Report verification findings to the user separately from the brief itself.

## Sharing-safe extract

If the user plans to share the brief with engineering collaborators, contractors, or external advisors who don't need (or shouldn't see) the full strategy, offer to produce a short companion doc, typically `STRATEGY.md`, 1-2 pages. It should include:

- Who we're building for (beachhead in one paragraph)
- The Structural Gaps (compressed)
- The personas (one line each, role + use of product)
- The augmented-product priorities (top 5-7, in priority order)
- The liability / regulatory rails (if applicable) as inviolable constraints

Strip: Financial Analysis, Competitor profiles, Porter Five Forces, the bowling-pin sequence, Hypothesis Tracking, Sales Plans, Production Plans.

Close the extract with a line pointing back to the full brief: "Additional context lives in the full business plan."

## Anti-patterns to avoid

- **Polished, confident-sounding content where no real information exists.** If you don't know, say so. Mark hypotheses as hypotheses.
- **Personas as bullet lists.** The Empathy Template is where empathy actually happens. A bulleted persona is a persona you can't act on.
- **Skipping Structural Gaps to get to product features faster.** That insight is the whole game.
- **Three Strategic Alternatives that are really three variations of one.** Make them genuinely different bets.
- **Smoothing over open questions in Hypothesis Tracking.** That list is what makes the working-draft posture honest.
- **Polishing prematurely.** v0.1 is the right label.
- **Generic Marketing Mix.** Each P (and Proof) should make a specific commitment, not a category description.
- **Lean Canvas that disagrees with the long form.** They must reconcile.

## Stylistic conventions

- Markdown output.
- H1 for the document title, H2 for top-level sections, H3 and H4 for nested subsections.
- Avoid emojis.
- Prefer prose for argumentative content; use bullets for lists of distinct items (personas, augmented-product items, open questions, alternative strategies).
- Mark hypotheses with phrases like "needs validation," "working assumption," "to be confirmed by…", or "*Open question.*"
- Start the document with the Title block: Status (Working draft), Audience, Method, Date.
- End with a "Next steps for v0.2" line that names concrete validation actions (e.g., "20 customer-discovery interviews split across X / Y / Z").
