# Kyanite

Kyanite Computer hosts a random selection of from-scratch software stack for server management and
networking hardware, bare-metal firmware, some Go libraries for it, and the management surfaces around them.
Most of it is pure Go on [TamaGo](https://github.com/usbarmory/tamago) and Rust on
[Embassy](https://github.com/embassy-rs/embassy). For now this is mainly experimental and leisure coding, who knows
if this turns into a serious project eventually.

> **Status:** everything here is **experimental**. APIs, formats, layouts, you name it,
> change without notice while the stack matures.

## Repositories

| Repo | What it is | Language |
| ---- | ---------- | -------- |
| [cairn](https://github.com/kyanitecomputer/cairn) | Bare-metal BMC runtime mostly in Go | Go (TamaGo) |
| [vein](https://github.com/kyanitecomputer/vein) | Bare-metal switch OS most in Go | Go (TamaGo) |
| [core](https://github.com/kyanitecomputer/core) | Shared device libs: supervision, NATS bus, telemetry, FSM, auth, config, web serving, bla bla bla | Go |
| [scree](https://github.com/kyanitecomputer/scree) | Embedded filesystem in Go cause fat32 doesn't cut it | Go |
| [schema](https://github.com/kyanitecomputer/schema) | Shared API and message schema for the stack | Protobuf |
| [facet](https://github.com/kyanitecomputer/facet) | Management web UI for both cairn and vein | TypeScript (SvelteKit + Tauri) |
| [embedded-go-hal](https://github.com/kyanitecomputer/embedded-go-hal) | Dependency-free Go HAL interface definitions (`src.kyanite.computer/embedded-go-hal`) | Go |
| [aspeed-go](https://github.com/kyanitecomputer/aspeed-go) | ASPEED HAL drivers in Go | Go (TamaGo) |
| [aspeed-data](https://github.com/kyanitecomputer/aspeed-data) | ASPEED register data and pac | Go |
| [aspeed-rs](https://github.com/kyanitecomputer/aspeed-rs) | ASPEED HAL crates in Rust | Rust (Embassy) |
| [mcu-runtime](https://github.com/kyanitecomputer/mcu-runtime) | BootMCU / Root-of-Trust firmware for smaller (auxiliary) cores | Rust (Embassy) |
| [aspeed-cf-runtime](https://github.com/kyanitecomputer/aspeed-cf-runtime) | SDK/runtime for the ASPEED ColdFireV1 coprocessor | C |

## Conventions

- **Go modules** import under the vanity path `src.kyanite.computer/<repo>`.
- **Licensing:** everything is dual-licensed under **Apache-2.0 OR MIT**.
- **Contributing & security:** see [CONTRIBUTING](https://github.com/kyanitecomputer/.github/blob/main/CONTRIBUTING.md) and
  [SECURITY](https://github.com/kyanitecomputer/.github/blob/main/SECURITY.md). These org-wide defaults apply to every repository cause I'm lazy.
