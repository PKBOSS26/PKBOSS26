# Pratik Kale

**Blockchain Infrastructure & Systems Engineer** — compilers, realtime SDKs, and observability tooling for Solana, Avalanche, and Monad.

I build the infrastructure developers build on. Right now that's [**Anvil**](https://github.com/Pratikkale26/Anvil): a transpiler that ports Anchor programs to leaner runtimes and then *proves* the port is byte-equal, instead of asking you to trust it.

[![Portfolio](https://img.shields.io/badge/Portfolio-kalehub.com-B45309?style=flat-square)](https://kalehub.com)
[![X](https://img.shields.io/badge/X-@PratikKale26-181717?style=flat-square&logo=x&logoColor=white)](https://x.com/PratikKale26)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-pratikkale26-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/pratikkale26/)
[![Superteam Earn](https://img.shields.io/badge/Superteam_Earn-%2412%2C130-14F195?style=flat-square)](https://superteam.fun/earn/t/Pratikkale26)

---

## Building

| Project | What it is | Proof |
|---|---|---|
| **[Anvil](https://github.com/Pratikkale26/Anvil)** | Anchor → Pinocchio transpiler with a byte-equal proof gate | [site](https://anvilsol.xyz) · [demo](https://anvil-rho.vercel.app/) · [npm](https://www.npmjs.com/package/anvil-sol) |
| **[SolSocket](https://github.com/Pratikkale26/solsocket)** | Socket.io for Solana — rooms, presence, state subscriptions on MagicBlock Ephemeral Rollups | [npm](https://www.npmjs.com/package/solsocket) |
| **[MonSocket](https://github.com/Pratikkale26/monsocket)** | The same realtime primitive, on Monad | [demo](https://escapemonsocket.vercel.app) · [npm](https://www.npmjs.com/package/monsocket) |
| **[ICM Trace](https://github.com/Pratikkale26/icm-trace)** | Cross-chain execution debugging for Avalanche ICM/Teleporter | [live](https://icm-trace.vercel.app) · [npm](https://www.npmjs.com/package/@avapulse/icm-core) |
| **[AvaPulse](https://github.com/Pratikkale26/AvaPulse)** | Alerting-first observability for self-hosted Avalanche L1s | [live](https://ava-pulse.vercel.app) |

<details>
<summary><b>Earlier work</b></summary>

<br>

| Project | What it is |
|---|---|
| [DecentralWatch](https://github.com/Pratikkale26/DecentralWatch) | DePIN uptime network — 50+ validators across 6 countries, sub-100ms validation. Grant-funded by Solana × CoinDCX |
| [Flowrge](https://github.com/Pratikkale26/Flowrge) | Event-driven Web3 automation — webhook and on-chain triggers to programmable Solana actions |
| [Sui Private Transfer](https://github.com/Pratikkale26/sui-private-transfer) | Privacy-preserving token transfers on Sui |
| [Sonpari](https://github.com/Pratikkale26/Sonpari) | Digital gold savings — accounts, purchases, groups, leaderboards |
| [DareMe](https://github.com/Pratikkale26/dareme) | On-chain dares with trustless escrow |
| [LayerSplit](https://github.com/Pratikkale26/LayerSplit) | Group expense splitting on Sui, as a Telegram Mini App |

</details>

---

## Why Anvil is the interesting one

Anchor gives you productivity. Lower-level runtimes give you compute budget. Nobody ports between them by hand because rewriting thousands of lines of Rust is a correctness risk you can't justify.

Anvil does the port — then builds **both** binaries, runs them against the same instruction sequence inside LiteSVM, and asserts every account's `data`, `lamports`, and `owner` match byte for byte.

```bash
npm install -g anvil-sol

anvil compile ./my-anchor-program --target pinocchio -o ./out
anvil verify  ./my-anchor-program
#  ✓ BYTE-EQUAL — all compared accounts match.
```

| | |
|---|---|
| **196** | byte-equal differential tests, plus 181 cargo-build regression gates |
| **14+** | externally-authored programs cloned verbatim and verified byte-equal |
| **30–48%** | compute-unit savings, measured side by side on a test validator |
| **klend** | 63 instructions, builds SBF-green — first top Solana lending protocol fully compilable to Pinocchio |

---

## Published packages

| Package | What it does | Version | Installs |
|---|---|:--|:--|
| [`anvil-sol`](https://www.npmjs.com/package/anvil-sol) | Anchor → Pinocchio/Native transpiler + byte-equivalence verifier | ![](https://img.shields.io/npm/v/anvil-sol?style=flat-square&label=&color=B45309) | ![](https://img.shields.io/npm/dm/anvil-sol?style=flat-square&label=&color=555) |
| [`solsocket`](https://www.npmjs.com/package/solsocket) | Realtime rooms, presence, and state subscriptions for Solana | ![](https://img.shields.io/npm/v/solsocket?style=flat-square&label=&color=B45309) | ![](https://img.shields.io/npm/dm/solsocket?style=flat-square&label=&color=555) |
| [`monsocket`](https://www.npmjs.com/package/monsocket) | The same realtime primitive, on Monad | ![](https://img.shields.io/npm/v/monsocket?style=flat-square&label=&color=B45309) | ![](https://img.shields.io/npm/dm/monsocket?style=flat-square&label=&color=555) |
| [`@avapulse/icm-core`](https://www.npmjs.com/package/@avapulse/icm-core) | Teleporter/ICM message lifecycle engine | ![](https://img.shields.io/npm/v/@avapulse/icm-core?style=flat-square&label=&color=B45309) | ![](https://img.shields.io/npm/dm/@avapulse/icm-core?style=flat-square&label=&color=555) |

<sub>Version and install badges are live from npm — they update themselves.</sub>

## Open source

Contributions to other people's codebases — open and merged labelled separately, because they're not the same thing.

| Repo | PR | State |
|---|---|:--|
| [block/buzz](https://github.com/block/buzz) `25.5k★` | [#4931](https://github.com/block/buzz/pull/4931) read social publish body from stdin for the `-` sentinel | open |
| [block/buzz](https://github.com/block/buzz) | [#4922](https://github.com/block/buzz/pull/4922) accept conventional boolean spellings for env-backed flags | open |
| [block/buzz](https://github.com/block/buzz) | [#4918](https://github.com/block/buzz/pull/4918) republish group metadata when a huddle auto-archives | open |
| [block/buzz](https://github.com/block/buzz) | [#4882](https://github.com/block/buzz/pull/4882) tombstone workflow definition events on NIP-09 deletion | open |
| [magicblock-labs/Solana.Unity-SDK](https://github.com/magicblock-labs/Solana.Unity-SDK) | [#264](https://github.com/magicblock-labs/Solana.Unity-SDK/pull/264) MWA API parity, auth cache, reconnect UX | open |
| [blueshift-gg/blueshift-dashboard](https://github.com/blueshift-gg/blueshift-dashboard) | [#311](https://github.com/blueshift-gg/blueshift-dashboard/pull/311) dynamic, localized course-card descriptions | **merged** |

---

## Stack

**Chains & programs** — Rust · Solana · SVM · Anchor · Pinocchio · LiteSVM · SBPF · Solidity · Foundry · Sui/Move

**Systems & backend** — TypeScript · Node.js · WebSockets · Kafka · Redis · PostgreSQL · Prisma

**Infrastructure** — Docker · AWS · CI/CD · Prometheus · Grafana · Turborepo · Linux

**Interfaces** — Next.js · React · React Native · Electron · Tailwind

*Going deeper into:* Solana runtime internals · native SBPF programs · compiler design · distributed systems

---

## Background

**B.S. Data Science and Applications**, IIT Madras · SuperDevs (top 1% selection) · Turbin3 graduate · Superteam India member · 2× Web3 ecosystem grant recipient

---

<sub>Looking for infrastructure and systems engineering roles and internships. Reach me at <a href="mailto:pratikkale7661@gmail.com">pratikkale7661@gmail.com</a>.</sub>
