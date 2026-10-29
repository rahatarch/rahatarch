<h1 align="center">Rahat Hasan</h1>

<p align="center">
  <b>Systems engineer & founder · Bogura, Bangladesh</b><br/>
  I build execution engines for AI, protocols for agents, and a computer architecture in my native language — from the instruction set up.<br/>
  <sub>9th-grade student and self-taught engineer. Everything below was designed and built at age 15. I'm 16 now, and still building.</sub>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/rahatarch/"><img src="https://img.shields.io/badge/LinkedIn-rahatarch-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="https://x.com/rahatarch"><img src="https://img.shields.io/badge/X-@rahatarch-000000?style=flat-square&logo=x&logoColor=white" alt="X"/></a>
  <a href="mailto:rahatarch@akkharlabs.com"><img src="https://img.shields.io/badge/Email-rahatarch@akkharlabs.com-EA4335?style=flat-square&logo=gmail&logoColor=white" alt="Email"/></a>
</p>

**Now:** Co-founder, Lead Engineer & CTO at [Truck Pai](https://truckpai.com) · Founder & Engineer at [Brud Code](https://github.com/rahatarch/brud) · Founder & Systems Researcher at [Akkhar-Labs](https://github.com/Akkhar-Labs)

**Open to:** research collaborations, fellowships, and ambitious projects in systems engineering, AI infrastructure, and agent protocols.

---

### Proof, not adjectives

- 🚚 **~1,500 active users & drivers** on Truck Pai, a production logistics platform I built and run.
- ⚙️ **Brud Code**: ![VS Code installs](https://vsmarketplacebadges.dev/installs-short/akkhar-labs.brud.svg?style=flat-square&color=FF6F00&label=installs) on the VS Code Marketplace, ![GitHub stars](https://img.shields.io/github/stars/rahatarch/brud?style=flat-square&logo=github&label=stars&color=FF6F00) on GitHub; patched 467 files with 0 failures on Truck Pai's production codebase.
- 📄 **Published research**: [HashedContext](https://doi.org/10.5281/zenodo.23668957) (up to 88.7% less GPU KV-cache per agent and 3.6× more agent turns per hour in simulation) and [ZRCP](https://doi.org/10.5281/zenodo.21955969), both archived on Zenodo with permanent DOIs.
- 🧾 **Co-author of an accepted protocol extension**: ASM Trust Delta Receipt v0.1. My design additions were merged and are cited in the ASM paper.
- 🧠 **Endorsed by a Google DeepMind researcher** (founding team, Gemini Deep Research) for Aura-Arc ([source](https://lablab.ai/ai-hackathons/nano-payments-arc/akkhar-labs/aura-arc-the-economic-os-for-the-agentic-frontier)).
- 🔣 **Designed a 16-bit CPU instruction set in Bengali**, with my own assembler and simulator that run it end to end.

---

## Featured work

### ⚙️ Brud Code: deterministic execution engine for AI code edits · ⭐ Flagship
[Repo](https://github.com/rahatarch/brud) · [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=akkhar-labs.brud) · [Website](https://brudcode.com) · MIT

![Installs](https://vsmarketplacebadges.dev/installs-short/akkhar-labs.brud.svg?style=flat-square&color=FF6F00&label=installs) ![Stars](https://img.shields.io/github/stars/rahatarch/brud?style=flat-square&color=FF6F00)

> Brud Code lets any AI chatbot safely edit real codebases. Every change is reviewed, logged, and reversible.

My most actively developed project: live on the VS Code Marketplace and proven on a real production codebase. It is architected as a layered, out-of-process system:

- **Out-of-process daemon:** the VS Code extension now runs execution and history through a standalone daemon over a typed **JSON-RPC** protocol (wire contracts, methods, error definitions), with a lifecycle supervisor, a client harness, a daemon staging/packaging pipeline, and end-to-end tests.
- **Microkernel with a plugin system:** `@brud/kernel` has a Level-1 PluginManager with permission contexts, topological dependency ordering, fail-fast rollback, dynamic lifecycle, and unforgeable official-plugin branding with namespace protection.
- **Layered services on the kernel:** a `SettingsService` (atomic storage, safety lattice), a `WorkspaceService` (boundary containment) and a `BrudFileSystem` (Level-0 storage drivers, hardened `PathValidator`, durability hardening), all bootstrapped through `createStandardKernel` with injectable storage drivers.
- **Universal History:** a SQLite-backed session ledger with a reversibility model and a state machine, replacing the earlier snapshot-only approach.
- **Reliability:** a read-pipeline governor with a single-materialization envelope, single-flight execution lifecycle, hardened terminal streaming, and a repo-wide zero-`any`, zero-lint-error baseline.
- Monorepo (core · protocol · UI · daemon · VS Code adapter), CI on GitHub Actions, provider parity tests.
- **Benchmarked on Truck Pai's production codebase (384K LOC at the time):** 1,000 files created in under 1 s · 467 files patched with 0 failures · 1,000 files reverted and restored in milliseconds

**Brud Prime**, an autonomous multi-agent engineering system, is *in active development and coming soon* ([announcement](https://brudcode.com/announcements)).
<sub>Lineage: Akkhar Code Patcher → Sover → Brud Code.</sub>

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
