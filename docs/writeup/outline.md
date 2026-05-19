# Technical Writeup — Outline
## To be completed in Phase 5 (Weeks 16–17)

Do not write this document until the project is built.
Writing it before the project exists produces a plan, not a writeup.
The writeup should describe what you actually built, not what you intended to build.

---

## Structure (3 pages)

### Page 1 — Mathematical Background and Thesis
- Project thesis (1 paragraph)
- RSA mathematical foundation: primes, modular arithmetic, key generation
- Why OAEP padding is required
- Shor's Algorithm and the quantum threat
- NSA CNSA 2.0 timeline: 2027 and 2035 deadlines

### Page 2 — Implementation and Attack Suite
- RSA engine: Miller-Rabin, Extended Euclidean, OAEP, CRT speedup
- Wiener's Attack: condition, continued fractions, results table
- Hastad's Broadcast Attack: CRT combination, cube root recovery

### Page 3 — Kyber KEM and Conclusions
- Learning With Errors problem
- Polynomial ring arithmetic
- Full KEM cycle: keygen, encapsulate, decapsulate
- Bit-flip demonstration
- Why Kyber resists Shor's Algorithm
- Conclusions and references

---

*Write the final version in September after the project is complete.*
*Replace every outline point with specific results from your actual build.*
