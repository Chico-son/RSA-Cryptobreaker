# Phase 0 — Number Theory Study Roadmap

This folder will contain math reference documents as Phase 0 progresses.
Do not write any project code until all Phase 0 checkpoints are cleared.

## Topics to Cover (Weeks 1–4)

### Week 1
- Divisibility and prime numbers
- Modular arithmetic — definition, clock analogy, examples by hand
- Congruence notation: a ≡ b (mod n)

### Week 2
- Greatest Common Divisor (GCD)
- Euclidean Algorithm — trace by hand for gcd(48, 18)
- Extended Euclidean Algorithm — Bezout's Identity
- Modular inverse — what it means and when it exists

### Week 3
- Euler's Totient Function phi(n)
- Fermat's Little Theorem — verify 3^6 mod 7 = 1 by hand
- Euler's Theorem — why RSA decryption is correct
- Chinese Remainder Theorem — solve the three-congruence example by hand

### Week 4
- Miller-Rabin Primality Test — what a witness is, why 40 rounds
- RSA key generation — trace through full example with small numbers
- Why textbook RSA without padding is broken
- Environment setup: Java, Python, GitHub

## Phase 0 Exit Checklist

Before writing any project code, verify you can do all of the following
without looking at notes:

- [ ] Explain what a prime number is and why RSA uses two of them
- [ ] Solve a modular arithmetic problem by hand: 7^3 mod 11
- [ ] Trace the Euclidean Algorithm for gcd(56, 98)
- [ ] Compute phi(35) by hand
- [ ] State Fermat's Little Theorem with a numerical example
- [ ] Explain in plain English why RSA decryption recovers the original message
- [ ] Explain Miller-Rabin and why 40 rounds is sufficient
- [ ] Explain modPow vs pow().mod() and why it matters
- [ ] Write a basic tkinter window with a button
- [ ] Run a Java program from the command line
- [ ] Make 3 commits to this GitHub repository with descriptive messages

## Resources

- Aumasson, J. *Serious Cryptography* — Chapter 9 (RSA)
- Khan Academy — Modular Arithmetic (free, clear)
- MIT 6.875 Lectures 2–3 on YouTube
- Hoffstein, Pipher, Silverman. *An Introduction to Mathematical Cryptography* — Chapters 1–3
