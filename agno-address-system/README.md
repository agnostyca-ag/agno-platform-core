# AGNO Address System

Native address format for multi-jurisdictional compliance and AI automation.

## 🎯 Format

```
AGNO_[ISSUER]_[LAYER]_[NETWORK]_[DOMAIN]_[JURISDICTION]_[COMPLIANCE]_[HASH]
```

## 📋 Implementation

- `parser/` - Address parsing and validation
- `generator/` - Address generation utilities  
- `validator/` - Compliance checking
- `examples/` - Integration examples

## 📚 Documentation

See [AGNO-ADDRESS-GUIDE.md](AGNO-ADDRESS-GUIDE.md) for complete specification.

## 🔧 Usage

```go
import "github.com/agnostyca-ag/agno-platform-core/agno-address-system"

// Parse AGNO address
addr, err := agnoaddr.Parse("AGNO_UZH001_2_002_4_756_1620_a1b2c3d4...")
if err != nil {
    log.Fatal(err)
}

// Validate compliance
if addr.IsCompliant(agnoaddr.FINMA_SWITZERLAND) {
    // Process transaction
}
```