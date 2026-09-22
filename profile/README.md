# Kyanite

Kyanite builds an open, from-scratch software stack for server management and
networking hardware — bare-metal firmware, a device microkernel, and the
management surfaces around them. Most of it is pure Go on
[TamaGo](https://github.com/usbarmory/tamago) and Rust on
[Embassy](https://github.com/embassy-rs/embassy): no OS, no libc, no CGo.

> **Status:** everything here is **experimental**. APIs, formats, and layouts
> change without notice while the stack matures.

## Repositories

| Repo | What it is | Language |
| ---- | ---------- | -------- |
| [cairn](https://github.com/kyanitecomputer/cairn) | Bare-metal BMC runtime for the ASPEED AST2700 | Go (TamaGo) |
| [vein](https://github.com/kyanitecomputer/vein) | Bare-metal L2 switch OS for the MilkV Vega (RISC-V) | Go (TamaGo) |
| [core](https://github.com/kyanitecomputer/core) | Shared device microkernel: supervision, NATS bus, telemetry, FSM, auth, config, web serving | Go |
| [scree](https://github.com/kyanitecomputer/scree) | Embedded block + journal store backing NATS JetStream persistence | Go |
| [schema](https://github.com/kyanitecomputer/schema) | Shared API and message schema for the stack | Protobuf |
| [facet](https://github.com/kyanitecomputer/facet) | Management web UI | TypeScript (SvelteKit + Tauri) |
| [embedded-go-hal](https://github.com/kyanitecomputer/embedded-go-hal) | Dependency-free Go HAL interface definitions (`src.kyanite.computer/embedded-go-hal`) | Go |
| [aspeed-go](https://github.com/kyanitecomputer/aspeed-go) | ASPEED SoC register package and HAL drivers, zero-dependency | Go (TamaGo) |
| [aspeed-data](https://github.com/kyanitecomputer/aspeed-data) | ASPEED register data and the generator feeding `aspeed-go` | Go |
| [aspeed-rs](https://github.com/kyanitecomputer/aspeed-rs) | ASPEED HAL crates (`embassy-aspeed`, `aspeed-mmio`) | Rust (Embassy) |
| [mcu-runtime](https://github.com/kyanitecomputer/mcu-runtime) | BootMCU / Root-of-Trust firmware for AST2700 auxiliary cores | Rust (Embassy) |
| [aspeed-cf-runtime](https://github.com/kyanitecomputer/aspeed-cf-runtime) | SDK/runtime for the ASPEED ColdFire (m68k) coprocessor | C |

## Conventions

- **Go modules** import under the vanity path `src.kyanite.computer/<repo>`.
- **Licensing:** everything is dual-licensed under **Apache-2.0 OR MIT**.
- **Contributing & security:** see [CONTRIBUTING](https://github.com/kyanitecomputer/.github/blob/main/CONTRIBUTING.md) and
  [SECURITY](https://github.com/kyanitecomputer/.github/blob/main/SECURITY.md). These org-wide defaults apply to every repository.
