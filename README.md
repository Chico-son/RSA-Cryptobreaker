# CryptoBreaker

> **Build it. Break it. Replace it.**

A 17-week summer research project in applied cryptography.
**Start date: June 1, 2026 | End date: September 28, 2026**

---

## Project Thesis

RSA encryption — the algorithm that has secured the majority of the world's
digital communications for over four decades — is mathematically broken, not
by brute force but by structure. This project proves that claim by building
RSA-2048 from scratch, attacking it using documented cryptographic
vulnerabilities, and implementing its post-quantum replacement based on the
Kyber standard (NIST FIPS 203, August 2024).

The sequence — build, break, replace — mirrors at a student scale what NSA
is executing institutionally as it migrates national security systems away
from classical encryption before the advent of large-scale quantum computing.

---

## Why This Exists

NSA's CNSA 2.0 mandate requires:
- All new National Security System acquisitions to use quantum-resistant algorithms by **2027**
- All National Security Systems to be fully quantum-resistant by **2035**

NIST finalized **FIPS 203** (ML-KEM, derived from Kyber) in August 2024.
Understanding both what is being retired and why the replacement is
mathematically sound is not peripheral knowledge for someone pursuing a
career at NSA. It is the mission.

---

## What Will Be Built

### Component 1 — RSA-2048 Engine (Java)
A complete from-scratch implementation. No cryptographic libraries.
- 2048-bit prime generation using Miller-Rabin (40 rounds)
- Extended Euclidean Algorithm for key generation
- OAEP padding (PKCS#1 v2.2 / SHA-256)
- CRT-optimized decryption (mirrors real HSM implementations)
- Sub-100ms performance target

### Component 2 — Attack Suite (Python)
Two historically significant attacks against intentionally weakened keys.
- **Wiener's Attack**: recovers d when d < N^0.25 / 3 via continued fractions
- **Hastad's Broadcast Attack**: recovers plaintext from 3 ciphertexts (e=3) via CRT

### Component 3 — Kyber Toy KEM (Java + Python)
A simplified implementation of NIST FIPS 203 based on Module-LWE.
- Polynomial ring arithmetic over Z_q[x]/(x^n+1)
- Key generation, encapsulation, decapsulation
- Lattice visualization in GUI

---

## The Core Distinction

| Property       | RSA-2048                                      | Kyber (ML-KEM)                                     |
|----------------|-----------------------------------------------|----------------------------------------------------|
| Hard problem   | Integer factorization of N = p x q            | Finding short vectors in a high-dimensional lattice|
| Quantum-safe?  | No — Shor's Algorithm breaks it in poly-time  | Yes — no known quantum algorithm solves LWE        |
| NIST standard  | Legacy — being phased out                     | FIPS 203, finalized August 2024                    |
| NSA deadline   | Deprecated for NSS by 2030                    | Required for all new NSS acquisitions by 2027      |

---

## Development Timeline

| Phase | Weeks | Focus                                              | Status  |
|-------|-------|----------------------------------------------------|---------|
| 0     | 1–4   | Mathematical foundations — no code written         | Current |
| 1     | 5–8   | RSA-2048 engine in Java                            | Planned |
| 2     | 9–10  | Python GUI and Java-Python handshake               | Planned |
| 3     | 11–13 | Wiener's Attack and Hastad's Broadcast Attack      | Planned |
| 4     | 14–15 | Kyber toy KEM implementation                       | Planned |
| 5     | 16–17 | Documentation, demo video, GitHub polish           | Planned |

---

## Repository Structure

```
CryptoBreaker/
├── src/
│   ├── main/
│   │   ├── java/cryptobreaker/
│   │   │   ├── rsa/          # RSA engine (Phase 1)
│   │   │   ├── attacks/      # Weak key generation (Phase 3)
│   │   │   ├── kyber/        # Polynomial ring arithmetic (Phase 4)
│   │   │   └── util/         # JSON export (Phase 1)
│   │   └── python/
│   │       ├── gui/          # tkinter interface (Phase 2)
│   │       ├── attacks/      # Wiener + Hastad (Phase 3)
│   │       ├── kyber/        # Toy KEM (Phase 4)
│   │       └── util/         # JSON reader, timer
│   └── test/                 # Unit and integration tests
├── docs/
│   ├── math/                 # Number theory and Kyber math reference
│   └── writeup/              # 3-page technical writeup (Phase 5)
├── scripts/                  # Build and test automation
├── .github/workflows/        # CI — compile and test on push
├── output/                   # Runtime-generated files (gitignored)
├── bin/                      # Compiled Java classes (gitignored)
└── README.md
```

---

## How to Run (once implemented)

```bash
# Build Java backend
./scripts/build.sh

# Launch GUI
python3 src/main/python/gui/main_gui.py

# Run attack suite
python3 src/main/python/attacks/wiener.py
python3 src/main/python/attacks/hastad.py

# Run test harness
python3 rsa_test_harness.py
```

---

## References

- Rivest, Shamir, Adleman. "A Method for Obtaining Digital Signatures and Public-Key Cryptosystems." 1978.
- Boneh, D. "Twenty Years of Attacks on the RSA Cryptosystem." 1999.
- Wiener, M. "Cryptanalysis of Short RSA Secret Exponents." 1990.
- Hastad, J. "Solving Simultaneous Modular Equations of Low Degree." 1988.
- Bos et al. "CRYSTALS-Kyber: A CCA-Secure Module-Lattice-Based KEM." 2018.
- NIST FIPS 203: Module-Lattice-Based Key Encapsulation Mechanism Standard. August 2024.
- NSA CNSA 2.0: Commercial National Security Algorithm Suite. September 2022.
- Aumasson, J. *Serious Cryptography*. No Starch Press, 2017.

---

## Author

**[Your Full Name]**
The Heights School, Potomac, MD — Class of 2027
Intended: University of Maryland, Mathematics / ACES Program

*Developed June 1 – September 28, 2026.*
*NSA Stokes Educational Scholarship application project.*

---

## License

MIT License. See [LICENSE](LICENSE).

> The attacks implemented in this project target intentionally weakened
> keys generated by the project itself. For educational purposes only.
