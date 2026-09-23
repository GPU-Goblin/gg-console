# gg-console

The operations console of [GPU Goblin](https://github.com/GPU-Goblin/gg-server): the interface the
people running a GPU Goblin deployment use to control and maintain it.

> **Status: planned. This repository contains no code yet.** Nothing here is advertised as working.

## What it is for

Today, a deployment is operated from the `gg admin` command line and the `/v1/admin` API of the
control plane (see [gg-server](https://github.com/GPU-Goblin/gg-server)). The console is meant to
put the same operations in front of an operator:

- admission of researchers and projects, credit grants;
- authorization of contributors' workers, registration of validators and validation operators;
- disputes between validation operators, settled by a human (never automatically);
- task and run supervision, the audit rate, Prometheus metrics;
- reward batches and their settlement state.

## Constraints it will inherit

- It is a client of the existing `/v1/admin` API: it adds no route and no privilege of its own.
- An admin token grants everything; the console never stores one in the browser beyond a session,
  and never logs one.
- Every decision that the platform leaves to a human (a dispute, a grant, an authorization) stays a
  deliberate human action with a recorded reason.
- The design principles and the threat model of the project apply:
  [gg-server/docs/SPEC.md](https://github.com/GPU-Goblin/gg-server/blob/main/docs/SPEC.md),
  [gg-server/docs/THREAT_MODEL.md](https://github.com/GPU-Goblin/gg-server/blob/main/docs/THREAT_MODEL.md).

## Contributing

Open an issue to discuss the design before writing code. The contribution rules are those of the
project: [gg-server/CONTRIBUTING.md](https://github.com/GPU-Goblin/gg-server/blob/main/CONTRIBUTING.md).

## License

[PolyForm Noncommercial 1.0.0](LICENSE): free for research and any noncommercial use,
source-available, not open source in the OSI sense. See [LICENSING.md](LICENSING.md).
