# Temporal Hash Demo

A practical demonstration tool for the Temporal Hashing algorithm, which incorporates time-based elements into password hashing for enhanced security.

## Why Temporal Hashing?

Temporal Hashing provides several significant advantages over traditional hashing methods:

1. **Rainbow Table Protection**: 
   - Traditional hashes remain constant, making them vulnerable to pre-computed rainbow table attacks
   - Temporal hashes change over time, making rainbow tables impractical

2. **Database Breach Protection**:
   - Traditional hashed passwords remain valid indefinitely after a breach
   - Temporal hashes automatically expire, limiting the window of vulnerability

3. **Enhanced Collision Resistance**:
   - Traditional hashes have a fixed output space
   - Temporal hashing adds a time dimension, vastly expanding the output space

4. **Brute Force Resistance**:
   - Traditional hashes can be attacked indefinitely
   - Temporal hashing requires matching both the hash and timing window

## Features

- Interactive CLI tool for demonstrating temporal hashing
- Real-time visualization of hash changes over time
- Comprehensive comparison with traditional hashing methods
- Performance benchmarking tools
- Security analysis utilities

## Installation

```bash
pip install temporal-hash-demo
```

## Usage

### Basic Operations

```bash
# Hash a password
temporal-hash hash "mypassword"

# Verify a password
temporal-hash verify "mypassword" <hash>

# Show hash evolution over time
temporal-hash visualize "mypassword" --duration 24h

# Run security analysis
temporal-hash analyze --test-suite basic
```

### Comparison Features

```bash
# Compare protection against rainbow table attacks
temporal-hash compare rainbow-table "mypassword"

# Demonstrate database breach protection
temporal-hash compare breach-protection

# Compare performance with traditional methods
temporal-hash compare performance "mypassword" --iterations 1000

# Test collision resistance
temporal-hash compare collisions --samples 1000

# Compare brute force resistance
temporal-hash compare brute-force "mypassword"
```

## Example Outputs

1. Rainbow Table Protection:
```bash
$ temporal-hash compare rainbow-table "mypassword"
Traditional Hashes (same hash repeated over time):
MD5: 34819d7beeabb9260a5c854bc85b3e44
SHA256: 89e01536ac207279409d4de1e5253e01f4a1769e696db0d6062ca9b8f56767c8

Temporal Hashes (different hash values over time):
2024-01-10 12:00: th1$ABC...XYZ
2024-01-10 13:00: th1$DEF...UVW
2024-01-10 14:00: th1$GHI...RST
```

2. Database Breach Protection:
```bash
$ temporal-hash compare breach-protection
┌────────────┬─────────────────────┬──────────────────┐
│ Password   │ Traditional Valid   │ Temporal Valid   │
├────────────┼─────────────────────┼──────────────────┤
│ password123│         ✓           │        ✗         │
│ securepass │         ✓           │        ✗         │
└────────────┴─────────────────────┴──────────────────┘
```

3. Performance Comparison:
```bash
$ temporal-hash compare performance "mypassword"
┌──────────┬────────────────┐
│ Method   │ Time (ms)      │
├──────────┼────────────────┤
│ MD5      │     0.012      │
│ SHA256   │     0.015      │
│ Temporal │     0.018      │
└──────────┴────────────────┘
```

## Security Benefits

1. **Time-Based Invalidation**
   - Hashes automatically expire after a configurable time window
   - Compromised passwords become invalid automatically
   - Enforces regular password changes naturally

2. **Enhanced Entropy**
   - Incorporates temporal entropy in addition to password entropy
   - Increases effective password strength
   - Makes pre-computation attacks infeasible

3. **Breach Mitigation**
   - Limits the useful lifetime of stolen password hashes
   - Provides automatic protection without user action
   - Reduces the impact of database breaches

4. **Implementation Security**
   - Uses cryptographically secure primitives
   - Implements constant-time comparisons
   - Provides secure salt generation and management

## Documentation

For detailed documentation, visit [https://temporal-hash-demo.readthedocs.io](https://temporal-hash-demo.readthedocs.io)

## Contributing

Contributions are welcome! Please read our [Contributing Guidelines](CONTRIBUTING.md) for details.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. 