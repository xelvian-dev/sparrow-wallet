<div align="center">

<img src="src/main/resources/image/sparrow.png" alt="Sparrow Wallet" width="128" />

# Sparrow Wallet

### Your keys. Your Bitcoin. Your control.

An open-source desktop Bitcoin wallet for transparent transaction management, hardware wallet integration, and connecting to your own node.

![Java](https://img.shields.io/badge/Java-25%2B-ed8b00?style=flat-square&logo=openjdk&logoColor=white)
![JavaFX](https://img.shields.io/badge/UI-JavaFX-2563eb?style=flat-square)
![Platforms](https://img.shields.io/badge/Windows%20%C2%B7%20macOS%20%C2%B7%20Linux-334155?style=flat-square)
[![License](https://img.shields.io/badge/License-Apache%202.0-22c55e?style=flat-square)](LICENSE)

[Features](#features) · [Quick Start](#quick-start) · [Build](#build) · [Project Structure](#project-structure) · [Documentation](#documentation)

</div>

---

## About

Sparrow lets you manage Bitcoin wallets and inspect each transaction, including selected UTXOs, recipients, change, and fees. It supports single-signature and multisignature wallets, cold storage, and hardware wallets.

This project is based on [sparrowwallet/sparrow](https://github.com/sparrowwallet/sparrow). It includes a custom README while preserving the original license and author credits.

## Features

| Feature | Capabilities |
| :--- | :--- |
| **Transaction control** | Select UTXOs, customize fees, and review transaction details before sending |
| **Flexible wallets** | Single-signature and multisignature wallets with standard Bitcoin scripts |
| **Hardware wallets** | Hardware wallet integration through the `lark` module |
| **Offline signing** | PSBT support with QR code and file exchange |
| **Network connections** | Bitcoin Core and Electrum server support |
| **Development networks** | Mainnet, testnet, testnet4, signet, and regtest |

## Quick Start

Running from source requires **JDK 25 or later**. The Gradle Wrapper is included; the first run requires internet access to download Gradle and dependencies. The `drongo` and `lark` modules are Git submodules. Initialize them after cloning:

```bash
git submodule update --init --recursive
```

Check your Java installation:

```bash
java -version
```

Run the application from the project root:

```bash
# Linux / macOS
./sparrow
```

```powershell
# Windows PowerShell
.\sparrow.bat
```

For development, specify a separate data directory and network:

```bash
./sparrow --network signet --dir ./dev-wallet
```

Show all available options: `./sparrow --help`.

## Build

| Task | Linux / macOS |
| :--- | :--- |
| Run the application | `./gradlew run` |
| Run tests | `./gradlew test` |
| Build the application package | `./gradlew jpackage` |
| Build without installers | `./gradlew jpackage -PskipInstallers=true` |

On Windows, use `.\gradlew.bat` instead of `./gradlew`.

Packaging on Debian / Ubuntu requires additional tools:

```bash
sudo apt install rpm fakeroot binutils
```

Building the Windows installer requires WiX. See [docs/reproducible.md](docs/reproducible.md) for reproducible build instructions.

## Project Structure

```text
.
├── src/main/          # Application, JavaFX interface, and resources
├── src/test/          # Application tests
├── drongo/            # Bitcoin primitives and wallet logic
├── lark/              # Hardware wallet integration
├── docs/              # Technical documentation
├── gradle/            # Gradle Wrapper and dependency configuration
├── build.gradle       # Dependencies, execution, and packaging
└── settings.gradle    # Module configuration
```

## Documentation

- [Sparrow guides](https://sparrowwallet.com/docs/)
- [Reproducible builds](docs/reproducible.md)
- [Upstream security policy](SECURITY.md)
- [Upstream repository](https://github.com/sparrowwallet/sparrow)

## License

The code is distributed under the [Apache License 2.0](LICENSE). Original author credits and license notices are preserved. Included modules retain their licenses in their respective directories.
