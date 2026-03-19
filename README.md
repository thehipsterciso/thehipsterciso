# Thomas Jones

There is something about starting as an electrician that never leaves you. You
learn early that systems have physics — that the gap between how something is
supposed to work and how it actually behaves is always measurable, always honest,
and never negotiable. That lesson followed me through electrical engineering,
into digital systems, into the first management role I was not ready for, through
director and VP positions at global manufacturers, and eventually into the C-suite
accountable for the data, AI, and security functions of enterprises operating at
scale across multiple continents.

The path matters because it shaped what I build and why. Every project here
starts from the same place: what is actually true about this system, this
organization, this decision — and what would you need to know to be confident
you were right?

---

## Active

### Reasoning Graph Platform

Something I kept encountering in executive roles was a specific kind of
organizational fragility. A decision gets made based on a finding. The finding
came from an analysis. The analysis rested on assumptions that were reasonable
at the time, or maybe were never examined at all. Nobody knows, because the
system that stored the finding did not store any of that — it just stored the
conclusion. So the conclusion gets treated as fact, other decisions get built on
top of it, and somewhere downstream something fails in a way that is genuinely
hard to trace back.

I do not think this is a data quality problem. I think it is an architecture
problem. Knowledge systems are built to store what is known. They are not built
to store how confidently it was known, or what the evidence half-life is, or
what should change when the evidence ages out.

That is what this platform is trying to become. A reasoning system that persists
not just its results but the reasoning behind them — provenance on every claim,
traceable inference chains, confidence that decays as the evidence supporting it
ages. The system is designed to know what it does not know, which turns out to
matter quite a lot when the people using it are making decisions with real
consequences.

The build process is worth looking at separately if you are interested in how
AI-enabled systems can be governed without constant human supervision. Nine
repositories, forty components, autonomous build on GitHub Actions with a
seven-stage quality gate and two independent reviewers per component. Human
involvement when the system escalates something it cannot resolve on its own.
That boundary — where the system stops and the human starts — is a design
decision, not a default.

[rg-platform-core](https://github.com/thehipsterciso/rg-platform-core) ·
[rg-graph-layer](https://github.com/thehipsterciso/rg-graph-layer) ·
[rg-integrity-layer](https://github.com/thehipsterciso/rg-integrity-layer) ·
[rg-value-layer](https://github.com/thehipsterciso/rg-value-layer) ·
[rg-agent-roster](https://github.com/thehipsterciso/rg-agent-roster) ·
[rg-domain-stores](https://github.com/thehipsterciso/rg-domain-stores) ·
[rg-unified-provenance](https://github.com/thehipsterciso/rg-unified-provenance) ·
[rg-build-orchestration](https://github.com/thehipsterciso/rg-build-orchestration) ·
[rg-governance-artifacts](https://github.com/thehipsterciso/rg-governance-artifacts)

---

### SCF Machine Learning

The question I never heard answered well in a board conversation about security
spending is also the most basic one: what did we actually get for that? Not a
maturity level. Not a compliance status. Something closer to — if we had not
made that investment, what would the financial exposure have looked like, and
how much of it did we actually move?

Most governance programs are not set up to answer that because they were built
for a different purpose. They map controls to frameworks. They track coverage.
They tell you where you are relative to a benchmark. That is useful work, but
it is not a business case, and at some point someone in that board conversation
is going to want a business case.

These models are built on the Secure Controls Framework, which spans 100+ laws,
regulations, and standards across 34 control domains, and they are trying to
close that gap — translating what organizations actually have in place into
financial terms that a CFO can engage with and a board can interrogate.

[securecontrolsframework](https://github.com/thehipsterciso/securecontrolsframework)

---

## Complete

### hc-cdaio-kg

There is something genuinely strange about the traditional due diligence model
if you sit with it long enough. An enormous amount of time, money, and expertise
goes into producing a document that is essentially static. You cannot query it.
You cannot ask it a follow-up question. You cannot extend it when circumstances
change or when a new question emerges after the deal closes. If you want any of
that, you start over.

I wanted to understand what it would look like to build the alternative — not
as a theoretical exercise but as an actual artifact. So I took a public
technology company and built a full knowledge graph on it from public sources
only. 2,900+ entities, 7,600+ relationships, 401 structured analysis documents
working through ten stages of due diligence — corporate structure, business
model, competitive position, operating model, financial reality, technology
platform, data maturity, organizational resilience, and several others. Every
claim in the analysis is tagged as FACT, INFERENCE, or HYPOTHESIS and carries
a source citation. Each stage was validated before the next one opened.

The specific company is not the interesting part. What I wanted to know was
whether this approach — structured analytical framework, AI-augmented collection,
honest evidentiary standards — could produce something genuinely useful at a
fraction of the traditional cost and timeline. The answer, at least in this
instance, is yes. Whether that generalizes is a more interesting question, and
one I am still working through.

[hc-cdaio-kg](https://github.com/thehipsterciso/hc-cdaio-kg)

---

### hc-enterprise-kg

One of the persistent frustrations I ran into at the executive level is how
rarely the structural picture of an organization is actually visible before
a major decision gets made. Not the org chart — that tells you the official
version. The real picture: where the actual dependencies are, which vendor
relationships the business could not survive losing, where knowledge or
decision-making authority is concentrated in ways that are not documented
anywhere. That picture usually takes months to develop, which means most
decisions get made without it.

This platform was built around that problem. It generates a connected graph
of an enterprise — people, departments, systems, vendors, data assets,
regulatory obligations, and the relationships between them — that can be
stood up quickly enough to be useful before a decision rather than after.
Scenario modeling, dependency tracing, blast radius analysis, centrality
scoring. Three industry profiles that scale realistically from a small firm
to a 20,000-person enterprise. Full API, GraphQL gateway, interactive
visualization, Kubernetes-ready infrastructure, MCP server for Claude Desktop.
1,200+ tests. The first version was built in 11 days, which taught me enough
to want to build the next one from scratch.

[hc-enterprise-kg](https://github.com/thehipsterciso/hc-enterprise-kg) ·
[hc-enterprise-kg-enrich](https://github.com/thehipsterciso/hc-enterprise-kg-enrich) ·
[hc-enterprise-kg-gateway](https://github.com/thehipsterciso/hc-enterprise-kg-gateway) ·
[hc-enterprise-kg-web](https://github.com/thehipsterciso/hc-enterprise-kg-web) ·
[hc-enterprise-kg-infra](https://github.com/thehipsterciso/hc-enterprise-kg-infra)

---

### hc-claude-osint

When you are about to acquire a company, enter into a significant partnership,
or make a major resource commitment against a competitive position, there is
a version of that decision that benefits enormously from knowing what is
actually true about the other organization — not their narrative, but what
the public record shows when you apply a structured framework to it
systematically. That gap between what an organization says about itself and
what the evidence supports is often where the most useful diligence work
happens, and it is usually the work that gets done last, if at all.

This is a 13-agent system built to do that work. Four execution phases —
planning, parallel specialist research, independent verification, synthesis.
The specialists cover corporate and ownership structure, funding and investor
history, executive and team composition, technology and vendor landscape,
competitive position, hiring signals as a proxy for strategic direction,
government contracts, M&A activity, and public sentiment. Everything sourced,
everything confidence-rated.

[hc-claude-osint](https://github.com/thehipsterciso/hc-claude-osint)

---

### Measurable Cybersecurity

At some point in most security budget conversations, someone asks a version of
the same question: what are we actually getting for this? It sounds simple. In
practice it is remarkably hard to answer, partly because the field has defaulted
to metrics that measure activity rather than outcomes — coverage percentages,
maturity levels, audit findings — and partly because connecting those metrics to
financial terms requires work that most programs were never designed to do.

This framework was built to make that connection. It generates indicators from
control catalogs — SCF, NIST, CMMC — and maps them to financial outcomes in
language that holds up when someone in a board meeting decides to push back on
the numbers. Whether that fully solves the problem is something I am honest
about — the translation from security posture to financial impact involves real
uncertainty, and the framework tries to represent that rather than paper over it.

[measurable-cybersecurity](https://github.com/thehipsterciso/measurable-cybersecurity)

---

### Conforme

OVAL is the language standards bodies use to formally define vulnerability and
configuration state — the mechanism through which organizations prove to
regulators, auditors, and certification bodies that their systems are actually
in the state they claim. It is strict, unforgiving, and most of the tooling
that exists for working with it was built for reading OVAL content rather than
producing it at the quality level that formal submission and review requires.

Conforme was written to fill that gap. A C++ library built specifically for
authorship — generating OVAL content that is correct, deterministic, and built
to survive the review process it is going into. This came out of direct
submission work to MITRE and CIS, which has a way of clarifying exactly what
the standard actually requires versus what you thought it required.

[conforme](https://github.com/thehipsterciso/conforme)

---

### Microsoft Defender for Identity — ML

Something that becomes visible when you look at identity environments with
ML tooling is how much drift accumulates over time between what licenses and
permissions were assigned and what people actually need. Roles change, teams
reorganize, projects end, and the identity estate does not keep pace — not
because anyone made a bad decision, but because nobody was looking at the
aggregate picture. The result is spend that does not map to value, and
sometimes coverage gaps in places that matter.

These models were built on the zerve.ai platform to surface that misalignment
specifically — which roles carry capabilities they no longer use, where
subscription tiers exceed what the work actually requires, where consolidation
or rightsizing recovers budget. The output is a financial case, not a security
assessment.

[defender-for-identity-ml](https://github.com/thehipsterciso/defender-for-identity-ml)

---

## Contact

[thehipsterciso.com](https://www.thehipsterciso.com) · [LinkedIn](https://www.linkedin.com/in/thehipsterciso/)

PGP: `a14544d8e04c62926e5887605973310129535708` · [public key](https://github.com/thehipsterciso/thehipsterciso/blob/main/assets/pgp-public-key.asc)
