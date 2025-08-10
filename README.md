# AGNO Platform Core

## 🏗️ Architecture Overview

AGNO (Agnostic Native Operations) is a multi-jurisdictional, compliance-first blockchain platform built on IOTA's DAG technology.

### 🎯 Core Components

```
agno-platform-core/
├── dag-engines/                    # DAG Layer Components
│   ├── hornet-l1/                 # L1 Hornet (secure, slow)
│   └── wasp-l2/                   # L2 Wasp (fast, smart contracts)
├── agno-address-system/           # AGNO Native Address Format
├── agno-ai-engine/               # AI Integration Layer
├── agno-contracts/               # Smart Contract Templates
└── documentation/                # Architecture & Compliance
```

### 🌍 AGNO Address Format

```
AGNO_[ISSUER]_[LAYER]_[NETWORK]_[DOMAIN]_[JURISDICTION]_[COMPLIANCE]_[HASH]
```

**Example:**
```
AGNO_UZH001_2_002_4_756_1620_a1b2c3d4e5f6789abc123def456789abc123def456789abc123def456789abc123d4e5
```

- **Multi-jurisdictional**: Supports EU, US, CH, DE compliance
- **AI-Readable**: Self-documenting compliance requirements
- **User Mobility**: Dynamic jurisdiction switching
- **Anti-Spam**: 100% effective against bot wallets

### 🚀 Quick Start

```bash
# Clone with submodules
git clone --recursive https://github.com/agnostyca-ag/agno-platform-core.git
cd agno-platform-core

# Initialize submodules
git submodule update --init --recursive

# Build L1 node
cd dag-engines/hornet-l1
make build

# Build L2 node  
cd ../wasp-l2
make build
```

### 📋 Repository Structure

- **dag-engines/**: Contains forks of IOTA Hornet (L1) and Wasp (L2)
- **agno-address-system/**: AGNO native address format implementation
- **agno-ai-engine/**: AI integration and automation layer
- **agno-contracts/**: Sector-specific smart contract templates
- **documentation/**: Complete architecture and compliance documentation

### 🏛️ Compliance Features

- **GDPR Compliant**: EU data protection by design
- **FINMA Ready**: Swiss financial market compliance
- **BaFin Compatible**: German financial supervision
- **Multi-KYC**: Flexible KYC levels (0-7)
- **Cross-Border**: Automated jurisdiction handling

### 🎓 Use Cases

- **Universities**: Student credentials and IQ tokens
- **Healthcare**: Secure medical record management  
- **Finance**: Cross-border payments and compliance
- **Luxury Brands**: Authentication and anti-counterfeiting
- **Government**: Digital identity and public services

### 📄 License

This project combines:
- **AGNO Platform**: Proprietary (Commercial License)
- **Hornet L1**: Apache 2.0 License (IOTA Foundation)
- **Wasp L2**: Apache 2.0 License (IOTA Foundation)

See individual LICENSE files in each component directory.

### 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for development guidelines.

### 🔗 Related Repositories

- [agno-wallet-frontend](https://github.com/agnostyca-ag/agno-wallet-frontend) - Web wallet interface
- [agno-mobile-wallet](https://github.com/agnostyca-ag/agno-mobile-wallet) - Mobile applications
- [agno-documentation](https://github.com/agnostyca-ag/agno-documentation) - Complete documentation

---

**Agnostyca AG** | Building compliant blockchain infrastructure for the real world.