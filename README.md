<h1 align="center">Rahat Hasan</h1>

<p align="center">
  <b>Systems engineer & founder · Bogura, Bangladesh</b><br/>
  I build runtimes and execution engines for AI agents, protocols for agents, and a computer architecture in my native language — from the instruction set up.<br/>
  <sub>9th-grade student and self-taught engineer, building since 15. I'm 16 now.</sub>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/rahatarch/"><img src="https://img.shields.io/badge/LinkedIn-rahatarch-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="https://x.com/rahatarch"><img src="https://img.shields.io/badge/X-@rahatarch-000000?style=flat-square&logo=x&logoColor=white" alt="X"/></a>
  <a href="mailto:rahatarch@akkharlabs.com"><img src="https://img.shields.io/badge/Email-rahatarch@akkharlabs.com-EA4335?style=flat-square&logo=gmail&logoColor=white" alt="Email"/></a>
</p>

**Now:** Co-founder, Lead Engineer & CTO at [Truck Pai](https://truckpai.com) · Founder & Engineer at Brud ([Brud OS](https://github.com/rahatarch/brud) · [Brud Code](https://brudcode.com)) · Founder & Systems Researcher at [Akkhar-Labs](https://github.com/Akkhar-Labs)

**Open to:** research collaborations, fellowships, and ambitious projects in systems engineering, AI infrastructure, and agent protocols.

---

### Proof, not adjectives

- 🚚 **~1,500 active users & drivers** on Truck Pai, a production logistics platform I built and run.
- 🧩 **Brud OS**: an open-source, embeddable runtime for AI agents. All six of its core services are working. ![GitHub stars](https://img.shields.io/github/stars/rahatarch/brud?style=flat-square&logo=github&label=stars&color=FF6F00) on GitHub.
- ⚙️ **Brud Code**: ![VS Code installs](https://vsmarketplacebadges.dev/installs-short/akkhar-labs.brud.svg?style=flat-square&color=FF6F00&label=installs) on the VS Code Marketplace, free; patched 467 files with 0 failures on Truck Pai's production codebase.
- 📄 **Published research**: [HashedContext](https://doi.org/10.5281/zenodo.23668957) (up to 88.7% less GPU KV-cache per agent and 3.6× more agent turns per hour in simulation) and [ZRCP](https://doi.org/10.5281/zenodo.21955969), both archived on Zenodo with permanent DOIs.
- 🧾 **Co-author of an accepted protocol extension**: ASM Trust Delta Receipt v0.1. My design additions were merged and are cited in the ASM paper.
- 🧠 **Endorsed by a Google DeepMind researcher** (founding team, Gemini Deep Research) for Aura-Arc ([source](https://lablab.ai/ai-hackathons/nano-payments-arc/akkhar-labs/aura-arc-the-economic-os-for-the-agentic-frontier)).
- 🔣 **Designed a 16-bit CPU instruction set in Bengali**, with my own assembler and simulator that run it end to end.

---

## Featured work

### 🧩 Brud: a runtime for AI agents, and the coding tool built on it · ⭐ Flagship

#### Brud OS
[Repo](https://github.com/rahatarch/brud) · Apache 2.0 · Developer Preview, in active development

![Stars](https://img.shields.io/github/stars/rahatarch/brud?style=flat-square&color=FF6F00)

> An embeddable, zero-trust runtime that lets apps give AI agents real power (files, terminal, network) without handing them the keys to the machine.

Most agent frameworks either give the model free rein over the host machine or wrap it in a heavy virtual machine that can't be embedded in a real product. Brud OS takes a different path: its core holds no power of its own. It only checks who each component is, decides what it may do, and routes each request to the right place.

Every app gets the same **fixed floor of six core services**. They can't be removed or swapped out, and Brud OS refuses to start if any of them is missing or fails verification. Everything else (file access, terminal, storage, integrations) is an optional service the app chooses for itself.

**What it saves the people building on it:** making an agent product safe usually means months of work before the product itself even starts: sandboxing, permission systems, identity checks, secure process communication. Brud OS ships all of that as the starting point, so you get security by default instead of building it yourself, and you can spend your time on what makes your app different. Eleven official services are already built, and the plan is to offer **25+ official, ready-made services and plugins** once Brud OS is published, so an agent-powered app can come together in days instead of months.

**Working today: the six core services**
- **Identity:** every component gets an ID that the runtime issues from a hash of its code. A modified plugin can't pass itself off as a trusted one by reusing its name, and a component without a verified identity doesn't run.
- **Capability registry:** a single list of everything that can be called. It is sealed once the system is running, so nothing new can slip in afterwards.
- **Parser and router:** every request is turned into one standard shape and sent to the component that owns that kind of operation. Anything without an owner is rejected.
- **Sandbox:** unofficial and unverified components run only inside a WebAssembly sandbox, and no configuration can switch it off. Whether a component is sandboxed depends on what the app trusts, not on who wrote it.
- **Events:** components can publish signals without knowing who is listening. This is the "observe" counterpart to the "call" registry.

**Official services, built on top of the core**
- **Plugins, like VS Code extensions, for any app:** an app built on Brud OS can load and unload plugins while it runs, and each one extends what the app can do, just as extensions extend VS Code. The plugin system comes ready-made, so an app can offer its own in-app plugin marketplace within days instead of building one from scratch. Plugins load in a safe order, get only the permissions they're granted, and roll back cleanly if one fails. Official status is tied to verified code, so nobody can fake it by copying a name.
- **Files and workspace:** file access only within what's authorized, with durable writes, and a hard boundary that keeps everything inside the open project.
- **Terminal:** runs commands as a controlled service instead of giving raw access to the host machine.
- **AI tools:** the list of every tool an AI is allowed to call to do real work.
- **Human-only actions:** some operations can only be triggered by a person, never by the AI, and that split is enforced every time a request is dispatched.
- **History:** a persistent record of every session, with undo and redo across the whole runtime.
- **Settings, validation and utilities:** atomic settings changes with change notifications, schema-based data validation, and shared helpers.

These are the official versions, not the only ones. Any developer or open-source team can build their own services, including direct alternatives to the official ones, and they plug in under the same rules. The official set is the starting point, and the ecosystem grows as third parties start building on it.

**Designed, in progress**
- **Permissions that only narrow:** a sub-agent can never hold more access than the agent that created it. Read-write can become read-only, never the reverse.
- **Per-component storage** with transactional (ACID) guarantees.
- **An encrypted, mutually authenticated channel** between the app and the runtime when it runs as a separate process.

#### Brud Code
[VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=akkhar-labs.brud) · [Website](https://brudcode.com) · Free · Closed source

![Installs](https://vsmarketplacebadges.dev/installs-short/akkhar-labs.brud.svg?style=flat-square&color=FF6F00&label=installs)

> Brud Code lets any AI chatbot safely edit real codebases. Every change is reviewed, logged, and reversible.

**Free, and staying free.** Maintaining Brud OS, an open-source Brud Code, and a separate release build on my own wasn't sustainable, so Brud Code is now closed source and being rebuilt on Brud OS. The move is about focus, not about charging for it. The open-source work continues in Brud OS itself.

Brud Code was already built like a small operating system, and that core is what grew into Brud OS:

- **A separate background process** runs every edit and keeps the history. The editor talks to it through a typed protocol, and a supervisor manages its lifecycle.
- **A small plugin core** loads plugins in a safe dependency order, gives each one only the permissions it was granted, and rolls everything back cleanly if one fails to start.
- **Strict file safety:** every file operation is checked to stay inside the project, and writes are atomic and durable.
- **Full session history** in a local database, so every change can be traced and undone.
- **A strict quality bar:** no untyped code, zero lint errors, and CI across a multi-package monorepo.
- **Benchmarked on Truck Pai's production codebase (384K LOC at the time):** 1,000 files created in under 1 s · 467 files patched with 0 failures · 1,000 files reverted and restored in milliseconds

**Brud Prime**, an autonomous multi-agent engineering system, is *in active development and coming soon* ([announcement](https://brudcode.com/announcements)).
<sub>Lineage: Akkhar Code Patcher → Sover → Brud Code (age 15) → Brud OS (age 16, grown out of Brud Code's core) → Brud Code, now being rebuilt on Brud OS.</sub>

### 🔣 Akkhar-Labs: computing from first principles, in Bengali
[Org](https://github.com/Akkhar-Labs) · [Project Ekushey](https://github.com/Akkhar-Labs/project-ekushey)

Akkhar-Labs is my independent systems research lab. It isn't a product company. It's where I work at the lowest layers of computing.
Its long-term mission, **Project Ekushey** (named after the 1952 Language Movement), is a complete computing stack designed in Bengali, from the instruction set to the operating system.

The bottom of that stack already exists and runs:

```
 .বয়ন source  ──►  Boyon (assembler)  ──►  .ব machine code  ──►  Shimu (simulator)  ──►  execution report
                         └──────────── Nirdeshika SDK: one command, full pipeline ────────────┘
                                   all targeting the Nirdeshika-16 ISA
```

| Layer | What I built | Engineering it demonstrates |
|---|---|---|
| [**Nirdeshika-16**](https://github.com/Akkhar-Labs/Nirdeshika-16) | A 16-bit load/store CPU **instruction set architecture**, specified entirely in Bengali (32-page spec, v1.0). Hardware design, not software. | Instruction encoding, register file, addressing modes, cycle timing |
| [**Boyon**](https://github.com/Akkhar-Labs/Boyon) | Two-pass assembler in C for Bengali assembly language | Lexing Unicode in C, symbol tables, label resolution, binary emission |
| [**Shimu**](https://github.com/Akkhar-Labs/Shimu) | Instruction-level CPU simulator in C | Fetch–decode–execute loop, 64 KB memory model, flags, fault handling |
| [**Nirdeshika SDK**](https://github.com/Akkhar-Labs/nirdeshika-sdk) | Unified toolchain: `nirdeshika --compute program.বয়ন` | Toolchain design, CMake builds |

I also defined **Akkhar-Hex**, a Bengali hexadecimal notation (০–৯, ক–চ). Next on the roadmap: a Bengali character encoding, 32/64-bit ISAs, the **Kotha** programming language, the **BAPS** kernel, and **Matrika OS**.

### 🚚 Truck Pai: logistics platform, Bangladesh
[truckpai.com](https://truckpai.com) · Co-founder, Lead Engineer & CTO

I designed, built, and continuously develop the entire technical platform **solo**, as a single proprietary monorepo: **7 Flutter apps, 25+ Node.js modules, a Go microservice, and PostgreSQL**. It runs in production, is upgraded daily, and serves **~1,500 active users and drivers**. It's my largest project.

### 🧠 Aura-Arc: economic OS for AI agents (hackathon)
[Repo](https://github.com/Akkhar-Labs/aura-arc) · [Project page](https://lablab.ai/ai-hackathons/nano-payments-arc/akkhar-labs/aura-arc-the-economic-os-for-the-agentic-frontier) · lablab.ai *Agentic Economy on Arc*

A deterministic C++17 core compiled to WebAssembly, Circle USDC nanopayments on Arc, a 3-way escrow handshake, and Supabase-backed crash recovery, with a Next.js 15 front end.

> *"Wild execution from a solo 16-year-old: deterministic C++17 core compiled to WebAssembly for financial atomicity off the JS main thread, plus a 3-way ASE handshake for trust-gap escrow and a Wasm/Supabase rehydration story for crash recovery. The unit-economics framing ($0.005 task vs $0.15 gas) is exactly the Arc pitch. Impressive."*
> — **[Naman Goyal](https://namangoyal.com)**, Researcher at Google DeepMind · [source](https://lablab.ai/ai-hackathons/nano-payments-arc/akkhar-labs/aura-arc-the-economic-os-for-the-agentic-frontier)
>
> <sub>(I was actually 15 when I built it.)</sub>

---

## Client work

Professional freelancer since 2025, with ongoing client work for businesses in Bangladesh. Selected projects:

- **[iLab BD](https://ilabbd.com)**: training platform for mobile-repair and technology courses. I built the entire mobile app, shipped many new back-end features, and contributed across the web front end.
- **[My Pharma](https://mypharma.com.bd)**: Front-end developer (Next.js).

## 📄 Published research

Formal publications, archived on [Zenodo](https://zenodo.org) with permanent DOIs.

### Scaling GPU KV-Cache Efficiency and Inference Concurrency for Autonomous Agents with HashedContext: A Dual-Mode Architecture
[Paper (latest version)](https://doi.org/10.5281/zenodo.23668957) · [DOI: 10.5281/zenodo.23668957](https://doi.org/10.5281/zenodo.23668957) · [Code](https://github.com/rahatarch/hashedcontext)

Autonomous coding agents re-send unchanged source files to the LLM on every step, so prompts grow with every turn. That saturates GPU KV-cache memory and limits multi-tenant serving concurrency. **HashedContext** is a content-addressed context architecture that removes the redundancy: each file is tracked by its SHA-256 hash, past copies become compact `[HASH_STUB]` references, and every version stays in a local vault for lossless recovery.

It is a **dual-mode architecture**:

1. **Mode A (Authoritative Tail):** one complete copy of each current file at the end of the prompt, for the lowest memory use
2. **Mode B (Lazy Tail):** history is never rewritten and only changed lines are sent, so a prefix cache can reuse almost the entire prompt

Both modes run either edge-natively inside client editors or transparently at server-side inference gateways.

**Results:** in a simulated evaluation with 20,000 coding agents on real open-source repositories, **up to 88.7% less KV-cache per agent** and, on a 16-GPU cluster serving 512 agents, **up to 3.6× more agent turns per hour**. With a warm prefix cache, Mode B processes **88.1% fewer prompt tokens**.

### Zero-Redundancy Context Protocol (ZRCP)
[Paper (Zenodo)](https://zenodo.org/records/21955969) · [DOI: 10.5281/zenodo.21955969](https://doi.org/10.5281/zenodo.21955969) · [Spec & code](https://github.com/rahatarch/zrcp)

A protocol specification for removing redundant context between AI agents using content hashes.

### Protocol collaboration

| | |
|---|---|
| [**ASM Trust Delta Receipt v0.1**](https://github.com/YE-YI7/asm-spec/issues/7) | Co-authored with [Yi Guo](https://www.linkedin.com/in/yi-g-8842153a0/), creator of ASM (Product Manager, Tencent Ads). I contributed the first external reference integration, and my design additions (`public_key_fingerprint`, `supersedes`) were merged in [PR #8](https://github.com/YE-YI7/asm-spec/pull/8) and cited in the ASM paper. |

## Developer tools

| | |
|---|---|
| [**Akkhar Magic**](https://github.com/Akkhar-Labs/akkhar-magic) | OpenAI-compatible local API bridge for Google AI Studio (TypeScript, browser automation over CDP). |
| [**Braidwire**](https://github.com/rahatarch/Braidwire) | OpenAPI client generator with protected regions that survive regeneration, plus drift detection. |
| [**Export Code Context**](https://github.com/rahatarch/export-code-context) | VS Code extension that exports files or folders into one clean text file for LLMs. |

---

## Stack

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black)
![C++](https://img.shields.io/badge/C++17-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-0175C2?style=flat-square&logo=dart&logoColor=white)
![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![WebAssembly](https://img.shields.io/badge/WebAssembly-654FF0?style=flat-square&logo=webassembly&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![CMake](https://img.shields.io/badge/CMake-064F8C?style=flat-square&logo=cmake&logoColor=white)

## Ideas I'm developing

- 🎓 **[Just-In-Time Learning Educational Model](https://github.com/rahatarch/jit-learning-model)**: *proposal, draft v0.1.* An education model in which a learner's own goal decides what they learn next, with guidance when they need it and autonomy when they've earned it. It includes an admissions approach, an assessment framework, and a plan for testing whether it works. *"Who can't find their path, teach them. Whoever can, let them be free."*
- 📖 **Orchestrator of Reality**: book in progress. Its multi-model critique workflow parallels recent research on debate-based oversight (e.g., [arXiv:2605.27483](https://arxiv.org/abs/2605.27483)).

---

<p align="center">
  <b>Open to research collaborations, fellowships, and ambitious systems and AI-infrastructure projects.</b><br/>
  <a href="mailto:rahatarch@akkharlabs.com">rahatarch@akkharlabs.com</a>
</p>
