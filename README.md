# 🛰️ js8core-rs

[![License: AGPL v3](https://img.shields.io/badge/license-AGPLv3-blue)](./LICENSE)
![Status](https://img.shields.io/badge/status-active-brightgreen)
![Rust](https://img.shields.io/badge/rust-🦀-orange)
![Built for Off-Grid](https://img.shields.io/badge/mission-off--grid%20comms-red)

> Rebuilding the JS8Call protocol core in Rust — Make open source transmissible — over the air, across the world.

---

## 🌐 What is `js8core-rs`?

`js8core-rs` is a Rust reimplementation of the **JS8Call protocol**, designed for weak-signal, low-power, and off-grid communication over HF (shortwave) radio.  
It focuses on environments where bandwidth is scarce, latency is high, and infrastructure is nonexistent — such as:

- Emergency communications after disasters  
- Off-grid expeditions and field kits  
- Embedded devices in harsh environments  
- Simulated interplanetary networks (e.g., MarsNet)

---

## 📦 Project Origin

This project is a cleanroom reimplementation of the original [JS8Call C++ codebase](https://bitbucket.org/widefido/js8call/src/js8call/) maintained by KN4CRD.  
That legacy implementation is:

- Built with Qt GUI bindings  
- Intertwined with desktop components  
- Challenging to modularize or embed

Our goal is to **extract and modernize the protocol core** into a standalone, testable, embeddable Rust library — fully open-source and suitable for headless operation.

---

## 🧭 Why Rust?

Rust provides:

- ✅ Memory safety with zero-cost abstractions  
- ✅ `no_std` support for embedded and bare-metal  
- ✅ Strong type system for protocol correctness  
- ✅ First-class async + concurrency tooling  
- ✅ Cross-compilation to WASM, CLI, Linux, and RTOS

With `js8core-rs`, we aim to produce a library that can run:

- In a browser tab  
- On a microcontroller  
- Inside a planetary rover  
- Or inside your terminal

---

## 🛰️ Use Case: MarsNet

**MarsNet** is a conceptual example of how this protocol could be deployed in the future:

- JS8-like messaging across isolated relay nodes  
- TTL-aware frames, timestamped packets, store-and-forward logic  
- Operable in solar-powered, delay-tolerant, disconnected mesh environments

Whether on Earth or elsewhere, `js8core-rs` supports signal-based messaging even when nothing else works.

---

## 🧱 Module Structure

```text
js8core-rs
├── audio        # I/O abstraction (WAV/PCM)
├── modem        # Frame sync, symbol demod, SNR estimation
├── protocol     # JS8 message logic and framing
├── codec        # Huffman codec for compression
├── relay        # Store-and-forward with TTL logic
└── examples     # CLI usage, test vectors, integration
```


Each module is self-contained and exposed as a Rust crate. Future support includes:

- WebAssembly bindings  
- `no_std` compatibility  
- CLI tooling + relay daemon (`js8d`)

---

## 📊 Protocol Layer Role

| Layer             | Purpose                                |
|------------------|----------------------------------------|
| Application       | CLI, web frontend, headless services   |
| Protocol          | Framing, routing, relay logic          |
| Modem             | Baseband symbol-level decoding         |
| Audio             | Platform I/O bridge                    |
| Relay Engine      | Offline store/forward messaging        |

---

## 🤝 Contributing

We're building a community of radio hackers, protocol engineers, and Rustaceans.

We welcome:
- 🔧 Rust devs interested in protocol-layer work  
- 📡 JS8Call operators who can test real-world interactions  
- 🔬 DSP/audio engineers with a passion for signal decoding  
- 🛰️ Open source dreamers building the fallback internet

Pull requests and discussions are welcome. See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

---

## 🧩 License & Sharing

This project is licensed under **GNU AGPL v3**.

That means:
- You can use, modify, and deploy freely  
- If you run a modified version over a network, you must share the source  
- All forks and adaptations remain part of the commons

> We believe signal infrastructure should belong to everyone — especially in times of collapse.

📄 Read the [LICENSE](./LICENSE) for full details.

---

## 📡 Project Links

- Source: [github.com/rectinajh/js8core-rs](https://github.com/your-org/js8core-rs)
- Original: [bitbucket.org/widefido/js8call](https://bitbucket.org/widefido/js8call/src/js8call/)
- Contributors: See [`CONTRIBUTORS.md`](./CONTRIBUTORS.md)

---

Turn on the radio and receive the signal:
> `CQ CQ CQ DE JS8CORE-RS PSE QSY 14.078 RUSTCORE DE MARS`  
> _This isn’t just code. It’s how civilizations keep talking._
