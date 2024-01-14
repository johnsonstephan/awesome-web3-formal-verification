# 🔐 Awesome Web3 Formal Verification

A curated list of awesome formal verification resources for Web3.

## 📂 Table of Contents

- [🔐 Awesome Web3 Formal Verification](#-awesome-web3-formal-verification)
  - [📂 Table of Contents](#-table-of-contents)
  - [🤔 Introduction](#-introduction)
    - [Comparison to Other Methods](#comparison-to-other-methods)

## 🤔 Introduction

Formal verification is a method of mathematically proving that a computer program -- for example, a smart contract -- functions as intended. It involves translating the code of the contract into a formal representation (such as mathematical models and logic) and then using automated tools (like theorem provers or model checkers) to verify that the specifications and properties of the contract hold true. Formal verification detects flaws in code and logic, ensuring the contract's correctness, reducing vulnerabilities, and preventing potential financial losses.

### Comparison to Other Methods

- **Symbolic Execution**: Symbolic execution is a technique used within formal verification. It involves running a program with symbolic values instead of concrete inputs. It explores as many program paths as possible, checking for errors. Compared to formal verification, it does not provide a mathematical proof of correctness. It's focus is on finding bugs rather than proving their absence. It is a less comprehensive method in comparison to formal verification (but more practical in exploring complex code paths).
- **Unit Testing**: Unit testing involves testing individual components (units) of a program to ensure they work as expected. This method is less comprehensive than formal verification but more practical and easier to implement. It's excellent for catching specific, localized bugs but doesn't address system-wide correctness. Unit testing is critical early in the development process to ensure each component functions correctly.
- **Fuzz Testing**: Fuzz testing involves inputting random, unexpected, or invalid data (fuzz) into the system to test its robustness. It's an excellent method for finding bugs, but it's less structured and can't guarantee comprehensive coverage or correctness like formal verification. Fuzz testing is most beneficial when you want to test the resilience of a system against malformed or malicious inputs.
