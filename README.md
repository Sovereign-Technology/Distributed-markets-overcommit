
# CGK — Provably Non-Overcommitting Distributed Capacity Layer

**Constraint Geometry Kernel**  
A distributed primitive that **mathematically prevents capacity overcommitment** — even during network partitions and under adversarial pressure.

[![Open in Browser](https://img.shields.io/badge/Open%20Demo-Click%20Here-brightgreen?style=for-the-badge&logo=html5&logoColor=white)](https://distributed-markets-overcommit.github.io/Distributed-markets-overcommit/)

> **Live demo (single HTML file — no build required)**  
> https://distributed-markets-overcommit.github.io/Distributed-markets-overcommit/

## What CGK solves

Every major failure in distributed capacity systems follows the same pattern:

- State diverges during partition  
- Reconnection uses **additive** reconciliation  
- → Invisible overcommitment becomes catastrophic

Examples:

- FTX — customer deposits double-counted across internal ledgers  
- Celsius — same collateral committed to multiple yield promises  
- Cloud providers — cascading quota violations after regional reconnects

**CGK makes overcommitment topologically impossible** by combining:

1. **Contractive dynamics** → Banach fixed-point convergence  
2. **Lattice-semantic merge** (join ⊔ = max, never sum)  
3. **Hard budget-token gating** + **local/global capacity checks**

## Core Invariants (always hold)

- **Conservation**  
  ∀t: Σ allocations ≤ CAP  
- **Partition tolerance**  
  Isolated shard ≤ CAP / n  
- **Merge safety**  
  E(merge) ≤ c · (E(before)) with c < 1  
- **Contractivity**  
  Transition map T is a strict contraction → unique equilibrium

## Try the Guided Demo (5 steps)

1. **The Problem** — see why additive merges fail  
2. **Normal Operation** — watch contraction stabilize the system  
3. **Stress Test** — push to the hard cap (rejections appear)  
4. **Partition Attack** — isolate Shard C + adversarial injections  
5. **Convergence** — reconnect & observe safe merge (no double-spend)

**Controls you will use:**

- Start / Pause / Reset  
- Injection Rate slider (0–20)  
- Decay δ slider (controls contraction strength)  
- Partition C / Reconnect + Merge  
- Adversarial Inject (only active when partitioned)

All invariants are displayed live. Violations are impossible by construction.

## How to run locally

```bash
# Option 1: just open the file
open index.html    # macOS
xdg-open index.html   # Linux
start index.html      # Windows

# Option 2: simple local server (recommended — avoids CORS/font issues)
npx serve .            # or python -m http.server 8000
```

Then visit http://localhost:3000 (or :8000)

## Technical Highlights

- **Single-file HTML/JS** (~zero dependencies except Chart.js CDN)  
- **Banach fixed-point** applied to distributed resource allocation  
- **Tarski-style lattice join** for merge semantics  
- **Token regeneration bounded by decay rate** → no runaway excitation  
- **Local capacity bound during partitions** (CAP/n)  
- **Post-merge scaling + extra contraction margin**

## Current Status (Feb 2026)

| Component               | Status              | Notes                                      |
|-------------------------|---------------------|--------------------------------------------|
| Browser demo            | ✅ Complete         | Guided 5-step narrative + moment overlay   |
| Mathematical proofs     | ✅ In technical report | arXiv-style document available             |
| Multi-node simulator    | 🚧 Planned          | Rust + libp2p next milestone               |
| On-chain prototype      | 🚧 Planned          | Solidity / Move on L2                      |
| Formal verification     | 🗓 Future           | Coq / Lean target                          |

## Roadmap

1. Publish short paper with full proofs  
2. Multi-agent Rust simulator (Byzantine model)  
3. Reference smart-contract implementation  
4. Integrations: DePIN, AI inference markets, microgrids  
5. Open governance / tokenomics layer (if productized)

## Applications

- Decentralized GPU / AI inference slot markets  
- DePIN resource clearing (bandwidth, storage, compute)  
- Microgrid & decentralized energy balancing  
- Restaking / shared sequencing capacity caps  
- Any protocol that cannot afford double-spend of scarce resources

## Related Concepts

- CRDT merge semantics  
- Distributed rate limiters  
- Banach fixed-point in dynamical systems  
- Lattice-theoretic monitoring  
- Tarski fixed-point theorems in order theory

## License

see LICENSE.md

## Questions? Ideas? Collaboration?

Open an issue or reach out on X / Discord (links coming soon).

> Safety should not be a policy.  
> Safety should be geometry.

