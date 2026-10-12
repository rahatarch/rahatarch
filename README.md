<h1 align="center">Rahat Hasan</h1>

<p align="center">
  <b>Systems engineer & founder · Bogura, Bangladesh</b><br/>
  I build execution engines for AI, protocols for agents, and a computer architecture in my native language — from the instruction set up.<br/>
  <sub>9th-grade student and self-taught engineer. Everything below was designed and built at age 15. I'm 16 now, and still building.</sub>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/rahatarch/"><img src="https://img.shields.io/badge/LinkedIn-rahatarch-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="https://x.com/rahatarch"><img src="https://img.shields.io/badge/X-@rahatarch-000000?style=flat-square&logo=x&logoColor=white" alt="X"/></a>
  <a href="mailto:rahathasan5773@gmail.com"><img src="https://img.shields.io/badge/Email-rahathasan5773@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white" alt="Email"/></a>
</p>

**Now:** Co-founder, Lead Engineer & CTO at [Truck Pai](https://truckpai.com) · Founder & Engineer at [Brud Code](https://github.com/rahatarch/brud) · Founder & Systems Researcher at [Akkhar-Labs](https://github.com/Akkhar-Labs)

**Looking for:** internships, fellowships, and research collaborations in full-stack engineering, systems engineering, and research.

---

### Proof, not adjectives

- 🚚 **~1,000 active users & drivers** on Truck Pai, a production logistics platform I built and run.
- ⚙️ **Brud Code**: 780+ installs on the VS Code Marketplace and 29★ on GitHub; patched 467 files with 0 failures on a 384K-LOC codebase.
- 🧾 **Co-author of an accepted protocol extension**: ASM Trust Delta Receipt v0.1. My design additions were merged and are cited in the ASM paper.
- 🧠 **Endorsed by a Google DeepMind researcher** (founding team, Gemini Deep Research) for Aura-Arc ([source](https://lablab.ai/ai-hackathons/nano-payments-arc/akkhar-labs/aura-arc-the-economic-os-for-the-agentic-frontier)).
- 🔣 **Designed a 16-bit CPU instruction set in Bengali**, with my own assembler and simulator that run it end to end.

---

## Featured work

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

### ⚙️ Brud Code: deterministic execution engine for AI code edits
[Repo](https://github.com/rahatarch/brud) · [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=akkhar-labs.brud) · MIT

![Installs](https://img.shields.io/visual-studio-marketplace/i/akkhar-labs.brud?style=flat-square&label=installs&color=FF6F00) ![Stars](https://img.shields.io/github/stars/rahatarch/brud?style=flat-square&color=FF6F00)

> Brud Code lets any AI chatbot safely edit real codebases. Every change is reviewed, logged, and reversible.

- Standalone microkernel (`@brud/kernel`) with a capability pipeline and workspace sandboxing
- Snapshot history engine, session revert/restore, 7-day trash
- Terminal engine: sequential, parallel, and conditional runs; timeouts; dangerous-command blocking; live streaming
- Monorepo (core · protocol · UI · VS Code adapter), CI on GitHub Actions, provider parity tests
- **Benchmarks on a 384K-LOC codebase:** 1,000 files created in under 1 s · 467 files patched with 0 failures · 1,000 files reverted and restored in milliseconds

**Brud Prime**, an autonomous multi-agent engineering system, is *in active development and coming soon* ([announcement](https://brudcode.com/announcements)).
<sub>Lineage: Akkhar Code Patcher → Sover → Brud Code.</sub>

### 🚚 Truck Pai: logistics platform, Bangladesh
[truckpai.com](https://truckpai.com) · Co-founder, Lead Engineer & CTO

I designed, built, and maintain the entire technical platform: **7 Flutter apps, 25+ Node.js modules, a Go microservice, and PostgreSQL**. I shipped the first version in 20 days, and it now serves **~1,000 active users and drivers**.

### 🧠 Aura-Arc: economic OS for AI agents (hackathon)
[Repo](https://github.com/Akkhar-Labs/aura-arc) · [Project page](https://lablab.ai/ai-hackathons/nano-payments-arc/akkhar-labs/aura-arc-the-economic-os-for-the-agentic-frontier) · lablab.ai *Agentic Economy on Arc*

A deterministic C++17 core compiled to WebAssembly, Circle USDC nanopayments on Arc, a 3-way escrow handshake, and Supabase-backed crash recovery, with a Next.js 15 front end.

> *"Wild execution from a solo 16-year-old: deterministic C++17 core compiled to WebAssembly for financial atomicity off the JS main thread, plus a 3-way ASE handshake for trust-gap escrow and a Wasm/Supabase rehydration story for crash recovery. The unit-economics framing ($0.005 task vs $0.15 gas) is exactly the Arc pitch. Impressive."*
> — **[Naman Goyal](https://namangoyal.com)**, Researcher at Google DeepMind · [source](https://lablab.ai/ai-hackathons/nano-payments-arc/akkhar-labs/aura-arc-the-economic-os-for-the-agentic-frontier)
>
> <sub>(I was actually 15 when I built it.)</sub>

---

## Research & protocols

| | |
|---|---|
| [**HashedContext**](https://github.com/rahatarch/hashedcontext) | *Research paper, working draft.* Hash-referenced context for LLM agents. Early benchmarks show **57.7–67.2% fewer prompt tokens** on DeepSeek V4 production endpoints. |
| [**ZRCP**](https://github.com/rahatarch/zrcp) | Public protocol specification for removing redundant context between AI agents using content hashes. |
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
- 📖 **Orchestrator of Reality**: book in progress.

---

<p align="center">
  <b>Open to internships, fellowships, research collaborations, and serious projects.</b><br/>
  <a href="mailto:rahathasan5773@gmail.com">rahathasan5773@gmail.com</a>
</p>
