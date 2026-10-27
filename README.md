# PathwayAI

A civic AI assistant that matches Chicago residents to technology career pathways. Built by [DJMP Institute](https://djmpinstitute.org), a Chicago 501(c)(3), and governed by TCAF™ (the Trustworthy Civic AI Framework).

**Status (October 2026):** v0 is live at [djmpinstitute.org/pathwayai](https://djmpinstitute.org/pathwayai) as one structured Claude call behind a Cloudflare Worker. This repository is where the next phases are built in the open. Code arrives here as each phase is built and tested; until then, this page describes the design.

\---

## What it does

A resident chooses a role, describes a goal in a sentence, and receives a pathway card: suggested training, resources and next steps toward a technology career.

## Architecture

**v0 (live):** web page → Cloudflare Worker → one structured Claude call. The Worker holds the API key, validates input, rate-limits requests, accepts calls only from djmpinstitute.org, and checks that the model returns valid JSON.

**Phase 1 (in progress):** a supervisor coordinating five agents, with a human-in-the-loop oversight layer:

|Agent|Job|
|-|-|
|Intake \& Profile Builder|Turns the resident's input into a structured profile|
|Labor Market Analyst|Identifies in-demand technology roles|
|Resource Matcher|Matches the profile to training and support resources|
|Barrier Detector|Flags obstacles (time, cost, transport, prerequisites)|
|Pathway Architect|Assembles the step-by-step pathway|

## Roadmap

|Phase|What|Status|
|-|-|-|
|0|v0 code moved into this repository and documented|Next|
|1|Supervisor + five agents, with tests|In progress|
|2|Public labor-market and training data sources|Planned|

## What is not built yet

* The five-agent system is designed, not yet running. v0 is a single model call.
* No federal or public data sources are connected yet.
* No evaluation results yet; they will be published here with Phase 1.

## Governance (TCAF™)

Every build is checked against TCAF's four pillars: Secure by Architecture · Ethical by Design · Equitable by Intent · Scalable by Design. TCAF is a methodology under empirical validation.

## Security

API keys and other secrets live in Cloudflare's encrypted settings, never in this repository. Found a security issue? Email djmpinstitute@gmail.com rather than opening a public issue.

## License

Apache License 2.0. Copyright 2026 DJMP Institute. See [LICENSE](LICENSE) and [NOTICE](NOTICE).

Maintainer: Martin O. Pieters ([@gtbannamartin](https://github.com/gtbannamartin)), Founder \& Executive Director, DJMP Institute.

