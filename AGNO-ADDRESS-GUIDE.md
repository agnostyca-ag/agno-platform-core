# AGNO Address Format - Complete Reference Guide

## 🎯 **Format Overview**

```
AGNO_[ISSUER]_[LAYER]_[NETWORK]_[DOMAIN]_[JURISDICTION]_[COMPLIANCE]_[HASH]
```

**Example Breakdown:**

```
AGNO_UZH001_2_002_4_756_1620_a1b2c3d4e5f6789abc123def456789abc123def456789abc123def456789abc123d4e5
│    │       │ │   │ │   │    │
│    │       │ │   │ │   │    └── 64-char hash (DAG address)
│    │       │ │   │ │   └───────── Compliance code
│    │       │ │   │ └───────────── Jurisdiction code
│    │       │ │   └─────────────── Domain type
│    │       │ └─────────────────── Network ID
│    │       └───────────────────── Layer (1=L1, 2=L2)
│    └───────────────────────────── Issuer ID
└────────────────────────────────── Protocol identifier
```

## 🔐 **CRITICAL: Hash Integrity System**

**⚠️ ENTIRE STRING IS THE HASH - NOT JUST THE LAST PART**

### **Correct Implementation:**
```
Full Hash = "AGNO_UZH001_2_002_4_756_1620_a1b2c3d4e5f6789abc123def456789abc123def456789abc123def456789abc123d4e5"
```
- **The complete 95-character string IS the cryptographic hash**
- **Classification fields are part of the hash, not metadata**
- **No node can change classification without changing the entire hash**

### **Development Default Format:**
```
AGNO_000000_0_000_0_000_0000_[64-char-cryptographic-hash]
```
- **All classification fields = 0 during development**
- **AI/Human classification API assigns real values later**
- **Hornet DAG treats entire string as immutable hash**

### **Classification API Requirements:**

**Input:** Transaction data + context
**Output:** Complete AGNO hash with proper classification
**Process:**
1. AI/Human analyzes: issuer, domain, jurisdiction, compliance
2. API generates: `AGNO_[CLASSIFIED_FIELDS]_[CRYPTO_HASH]`
3. DAG receives: Complete hash (no modifications allowed)

### **Why This Matters:**
- **Security:** Prevents hash tampering via classification changes
- **Integrity:** Entire address is cryptographically secured
- **Immutability:** Classification becomes part of permanent record
- **Compliance:** Classification cannot be retroactively altered

## 📋 **Field Breakdown**

### **1. ISSUER (6 chars)**

```
000000  = System issuer (genesis, governance)
USER01  = Regular user account
UZH001  = University of Zurich
UBS001  = UBS Bank
GUCCIX  = Gucci (€5M premium registration)
APPLEC  = Apple (€5M premium registration)
```

### **2. LAYER (1 digit)**

```
1 = L1 Hornet (slow, secure, expensive)
2 = L2 Wasp (fast, cheap, smart contracts)
```

### **3. NETWORK (3 digits)**

```
000 = Main network
001 = Primary L2 network
002 = Education network
003 = Financial network
004 = Healthcare network
```

### **4. DOMAIN (1 digit)**

```
1 = Technical (infrastructure, APIs)
2 = Financial (payments, banking)
3 = NFT (art, credentials, authentication)
4 = Token (stablecoins, utilities, rewards)
```

### **5. JURISDICTION (3 digits)**

```
000 = International/Mobile user
276 = Germany (BaFin regulated)
372 = Ireland (EU passport)
040 = Austria (FMA regulated)
756 = Switzerland (FINMA regulated)
840 = United States
```

### **6. COMPLIANCE (4 digits)**

#### **KYC Levels (0000-0099)**

```
0000 = No KYC
0001 = Basic verification
0002 = Enhanced verification
0003 = Professional verification
0007 = Maximum institutional KYC
```

#### **Transaction Types (1000-8999)**

```
1001 = Personal payment
1400 = Investment banking
1500 = Corporate treasury
1600 = Luxury authentication
1620 = Educational utility
2001 = Academic credential
2500 = Healthcare record
```

#### **Authority Sectors (9000-9999)**

```
9001 = Financial intelligence unit
9002 = Tax authority
9003 = Central bank
9050 = Anti-money laundering
9099 = Law enforcement (covert)
```

### **7. HASH (64 chars)**

Standard blockchain address hash (SHA-256 derived)

## 🎓 **Real Examples Explained**

### **University Student Token**

```
AGNO_UZH001_2_002_4_756_1620_IQ_a1b2c3d4e5f6789abc123def456789abc123def456789abc123def456789abc123d4e5
```

- **UZH001**: University of Zurich issuer
- **2**: L2 (fast, cheap for students)
- **002**: Education network
- **4**: Token domain (IQ rewards)
- **756**: Switzerland jurisdiction
- **1620**: Educational utility token type
- **IQ**: Human-readable token identifier
- **Hash**: Unique address

### **Cross-Border Payment**

```
AGNO_USER01_1_000_2_000_9001_123abc456def789abc123def456789abc123def456789abc123def456789abc123def4
```

- **USER01**: Regular user
- **1**: L1 (secure for large amounts)
- **000**: Main network
- **2**: Financial domain
- **000**: International (mobile user)
- **9001**: Enhanced cross-border compliance
- **Hash**: Unique address

### **Premium Brand NFT**

```
AGNO_GUCCIX_2_001_3_372_1600_c3d4e5f6789abc123def456789abc123def456789abc123d4e5f678
```

- **GUCCIX**: Gucci premium issuer (€5M)
- **2**: L2 (smart contracts for NFTs)
- **001**: Primary L2 network
- **3**: NFT domain
- **372**: Ireland jurisdiction
- **1600**: Luxury authentication
- **Hash**: Unique NFT address

### **Banking Transaction**

```
AGNO_UBS001_1_000_2_756_1400_123abc456def789abc123def456789abc123def456789abc123def456789abc123def4
```

- **UBS001**: UBS Bank issuer
- **1**: L1 (maximum security)
- **000**: Main network
- **2**: Financial domain
- **756**: Switzerland (FINMA regulated)
- **1400**: Investment banking
- **Hash**: Bank account address

## 🤖 **AI Readability Benefits**

**Why this format works for AI:**

1. **Self-documenting**: Each field explains compliance requirements
2. **Structured parsing**: Easy to extract jurisdiction, domain, compliance level
3. **Regulatory automation**: AI can automatically apply correct rules
4. **Cross-border intelligence**: Instant jurisdiction recognition
5. **Compliance validation**: Automated KYC level checking

## 🛡️ **Anti-Spam Protection**

**Blocked formats:**

- `0x1234...` (Ethereum/MetaMask)
- `bc1q...` (Bitcoin)
- `addr1...` (Cardano)
- Any non-AGNO format

**Result**: 100% effective bot/spam blocking while maintaining regulatory compliance.

## 🔄 **User Mobility**

**Dynamic Jurisdiction System:**

- **Institutions**: Fixed where licensed (UZH001 always 756=Switzerland)
- **Users**: Follow current location (000=International allows movement)
- **No Lock-in**: Solve Apple ID jurisdiction problems

**Example Journey:**

```
Switzerland → Germany → Ireland
AGNO_USER01_1_000_2_756_1001_...  # Living in CH
AGNO_USER01_1_000_2_276_1001_...  # Moved to DE
AGNO_USER01_1_000_2_372_1001_...  # Relocated to IE
```

## 🎯 **Quick Reference Card**

| Field        | Length | Purpose     | Example     |
| ------------ | ------ | ----------- | ----------- |
| Protocol     | 4      | Identifier  | `AGNO`      |
| Issuer       | 6      | Who issued  | `UZH001`    |
| Layer        | 1      | L1 or L2    | `2`         |
| Network      | 3      | Sub-network | `002`       |
| Domain       | 1      | Use case    | `4`         |
| Jurisdiction | 3      | Legal zone  | `756`       |
| Compliance   | 4      | Rules/KYC   | `1620`      |
| Hash         | 64     | Address     | `a1b2c3...` |

**Total Length**: ~95 characters (self-documenting compliance)
