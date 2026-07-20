### Keaton Taliaferro

**Field service engineer who builds the tools.**

Four years keeping production critical semiconductor equipment running in a live fab. I build the
custom systems that turn analog signal into digital record, with a receipt for every fault. That is
the overlap I work in: now building the tools I wanted on the floor, and checking them against the
published literature instead of against a good feeling.

#### Power Service Toolbox

**[Repo](https://github.com/Skeeter-spec/power-service-toolbox)** · **[Live demo, no sign in](https://skeeter-spec.github.io/power-service-toolbox/projects/01-power-chain/build/index.html)**

Open tools for data center power service: switchgear, protective relays, ATS, metering, commissioning.

**The rule: nothing ships until it reproduces a published worked example and the number matches the book.**

**Eight of the ten tools are live and clickable**, each checked against a published worked example
before it shipped. Here is the one that shows the method in full:

| Live | What it proves |
|---|---|
| **[Power chain one line explorer](https://skeeter-spec.github.io/power-service-toolbox/projects/01-power-chain/build/index.html)** | Five published UPS configurations, utility to rack. Click any component to take it out of service and watch what goes dark. Every assertion quotes the source paper's own words. It refuses to print a tier, on purpose: a tier is awarded against a standard I have not read, and a confident wrong answer is exactly what this repo exists to avoid. |

The other seven, same rule:

- **[TCC coordination studio](https://skeeter-spec.github.io/power-service-toolbox/projects/02-tcc-coordination/build/index.html)** reproduces all 210 trip times a relay manual publishes, and prints no coordination verdict because its source says "usually".
- **[ATS sequence simulator](https://skeeter-spec.github.io/power-service-toolbox/projects/03-ats-sequence/build/index.html)** runs a named vendor's own transfer timers, and has no vendor neutral mode because ASCO and Russelectric disagree on the numbers by 6x.
- **[Relay bench](https://skeeter-spec.github.io/power-service-toolbox/projects/04-relay-bench/build/index.html)** puts seven ANSI protective elements on the bench, with the overcurrent element running live on the coordination studio's own verified engine rather than a copy of it.
- **[Modbus frame codec](https://skeeter-spec.github.io/power-service-toolbox/projects/05-modbus-meter/build/index.html)** reproduces the specification's published hex frames byte for byte, and refuses to decode a value wider than one register because the spec defines no such type.
- **[Ladder logic interpreter](https://skeeter-spec.github.io/power-service-toolbox/projects/06-ladder-logic/build/index.html)** reproduces a GE latch truth table row for row and evaluates a close permissive over all 32 inputs.
- **[Clearance limits planner](https://skeeter-spec.github.io/power-service-toolbox/projects/07-switching-order/build/index.html)** reproduces three clearance answers the Bonneville Power Administration publishes for its own worked examples, from figures traced by hand.
- **[Three phase sandbox](https://skeeter-spec.github.io/power-service-toolbox/projects/10-three-phase/build/index.html)** works line against phase, per unit, and symmetrical fault current, each reproduced from a published example to the book's own precision.

Two remain unbuilt, a NETA acceptance checklist generator and a commissioning script runner, both
waiting on a free reproducible example rather than shipped on a guess.

That gate is not decoration, and it cost me things. Mutation testing my own test suite (breaking the
code on purpose to prove the tests could actually fail) showed one of my features was dead code, so I
cut it. The same pass caught a real bug: a bus tie wired one way, so one side could never back feed the
other. `./tools/gate.sh` re-proves all of it in one command.

#### Background

Four years of field service on production critical semiconductor equipment in a live fab.
Better than 95% uptime, 15 to 25% downtime reduction, average service response under two hours.
PVD, CVD, CMP and FSS certified. Trained junior techs.

- **Safety.** LOTO trained and recertified every six months across those four years, in a live
  production fab. NFPA 70E training, ongoing, through a U.S. DOL registered electrical apprenticeship.
- **Power gear.** Hands on across the chain, acquired one install at a time: breaker populated power
  distribution cabinets feeding an entire tool, plasma process and peripheral sensors both, with the
  plasma supplies run as master and slave pairs into a single chamber for 40 kW to the plasma. The
  high power supplies, RF generators, and UPS banks downstream of them. Protective
  relays I set, tested, replaced, and chased nuisance trips on. Ran the power and signal cable that
  ties all of it together, with the interference discipline that goes with it: power kept away from
  signal, and loop area kept small. Verified components against their published norm values, worked
  out why they failed, and recommended the fix.
- **Controls and comms.** Migrated tool host communications off legacy SECS-I serial onto HSMS over
  TCP/IP, across many tools, each one bringing its own legacy quirks. Chased SECS/GEM failures that
  were corrupting tool behavior analytics down to the board. RS-232 and Modbus TCP across tool and
  facilities systems: vacuum, thermal, gas, RF, and plant equipment. Worked the fab's facility
  supervisory layer, the monitoring PC that manages the tool computers, the peripheral sensors and
  the control valves. The vendor shipped that box closed, so I got it to log sensor voltage and
  current and hand the readings to a server over Ethernet, which is how the experiment underneath
  got its data. Install level networking: bringing every new tool online with remote engineering
  and IT.
- **Before the fab, two years in microelectronics prototype development.** Debugged and characterized
  custom electronics at board and component level: probes, scope, function generator, LCR meter,
  microscope. Built custom data acquisition fixtures to pull current, voltage, RF and accelerometer
  data off a board, and turned the results into fingerprints that tell a hardware fault apart from a
  software configuration fault. I brought that lens into the fab, which is why a tool that would not
  talk got its comm board characterized instead of swapped.
- **The method that actually travels.** A problem is a story of the device's state, and every
  deviation from norm has a hard reason backed up by data. On equipment nobody memorizes, you derive
  it from the documentation, you engage the experts who know it, and you verify before you trust it.
  That is what I was paid for, and it is what the toolbox above is made of.

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
| **[BenefitsBridge](https://skeeter-spec.github.io/edge-ai-portfolio/benefitsbridge/build/)** | Answers SNAP and energy assistance questions only from official rule text it retrieved, quoting the rule every time. Ask about a program it has not loaded and it refuses and routes you to a caseworker. English and Spanish. |

**[Keystone](https://github.com/Skeeter-spec/keystone)** · a living atlas of the world's industrial
value chains, built to find the chokepoints. Educational, not investment advice.

Python, JavaScript, MATLAB, C, Java, Verilog, VHDL. Everything above runs in a browser or fully
offline, at zero cost per month.

#### Currently

Registered electrical apprentice on the Master Electrician track, 2029.
B.S. Business Administration, 2027. A.S. Engineering Transfer. A.S. Mathematics.

**[LinkedIn](https://www.linkedin.com/in/keaton-taliaferro-59109a126/)**
