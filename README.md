### Keaton Taliaferro

**Field service engineer who builds the tools.**

Four years keeping production critical semiconductor equipment running in a live fab, now building the
tools I wanted on the floor and checking them against the published literature instead of against a
good feeling. Almost nobody in power service writes software, and almost nobody who writes software
has racked a breaker. I work in that overlap.

#### Power Service Toolbox

**[Repo](https://github.com/Skeeter-spec/power-service-toolbox)** · **[Live demo, no sign in](https://skeeter-spec.github.io/power-service-toolbox/projects/01-power-chain/build/index.html)**

Open tools for data center power service: switchgear, protective relays, ATS, metering, commissioning.

**The rule: nothing ships until it reproduces a published worked example and the number matches the book.**

| Live | What it proves |
|---|---|
| **[Power chain one line explorer](https://skeeter-spec.github.io/power-service-toolbox/projects/01-power-chain/build/index.html)** | Five published UPS configurations, utility to rack. Click any component to take it out of service and watch what goes dark. Every assertion quotes the source paper's own words. It refuses to print a tier, on purpose: a tier is awarded against a standard I have not read, and a confident wrong answer is exactly what this repo exists to avoid. |

Nine more in the same discipline: coordination curves, ATS sequence, relay bench, Modbus metering,
ladder logic, switching orders and LOTO planning, NETA test plans, commissioning scripts.

That gate is not decoration, and it cost me things. Mutation testing my own test suite (breaking the
code on purpose to prove the tests could actually fail) showed one of my features was dead code, so I
cut it. The same pass caught a real bug: a bus tie wired one way, so one side could never back feed the
other. `./tools/gate.sh` re-proves all of it in one command.

#### Background

Four years of field service on production critical semiconductor equipment at Applied Materials.
Better than 95% uptime, 15 to 25% downtime reduction, average service response under two hours.
PVD, CVD, CMP and FSS certified. Trained junior techs.

- **Safety.** LOTO certified and recertified every six months across those four years, in a live
  production fab. NFPA 70E training, ongoing, through a U.S. DOL registered electrical apprenticeship.
- **Power gear.** Hands on across the chain: 480V+ switchgear, MV gear and protective relays, ATS,
  UPS, generators, and NETA style acceptance testing. Acquired one install at a time.
- **Controls and comms.** Proprietary PLC configuration on tool specific control software. Install
  level networking: bringing every new tool online with remote engineering and IT.
- **The method that actually travels.** On equipment nobody memorizes, you derive it from the
  documentation, you engage the experts who know it, and you verify before you trust it. That is what
  I was paid for, and it is what the toolbox above is made of.

A fab runs 24/7 and production critical, on the same discipline a data center floor runs on.

#### I also ship software, which is the rare half

**[Edge AI Portfolio](https://github.com/Skeeter-spec/edge-ai-portfolio)** · **[Live demos, no sign in](https://skeeter-spec.github.io/edge-ai-portfolio/)**

Verifiable AI tools for nonprofits, on the same instinct as the toolbox: the model observes, and
deterministic code you can audit makes the decision.

| Project | What it proves |
|---|---|
| **[GrantMatch](https://skeeter-spec.github.io/edge-ai-portfolio/grantmatch/build/)** | Reads a funder's RFP into a checklist of every requirement, then refuses to mark a draft compliant unless it can quote your own words back. Catches the model fabricating coverage, live. |
| **[ColdWatch](https://skeeter-spec.github.io/edge-ai-portfolio/coldwatch/build/)** | A roughly $21 edge sensor that predicts a food bank fridge failure hours early, ignores door openings so the alarm stays trusted, and alerts fully offline. Zero AI at runtime. |
| **[ReClaim Vision](https://skeeter-spec.github.io/edge-ai-portfolio/reclaim-vision/build/)** | Grades donated computers against a real refurbishment standard. The model observes, a rubric decides. Currently in QA. |

**[Keystone](https://github.com/Skeeter-spec/keystone)** · a living atlas of the world's industrial
value chains, built to find the chokepoints. Educational, not investment advice.

Python, JavaScript, MATLAB, C, Java, Verilog, VHDL. Everything above runs in a browser or fully
offline, at zero cost per month.

#### Currently

Registered electrical apprentice on the Master Electrician track, 2029.
B.S. Business Administration, 2027. A.S. Engineering Transfer. A.S. Mathematics.

**[LinkedIn](https://www.linkedin.com/in/keaton-taliaferro-59109a126/)**
