# 🔐 Awesome Web3 Formal Verification

A curated list of awesome formal verification resources for Web3.

## 📂 Table of Contents

- [🔐 Awesome Web3 Formal Verification](#-awesome-web3-formal-verification)
  - [📂 Table of Contents](#-table-of-contents)
  - [🤔 Introduction to Formal Verification](#-introduction-to-formal-verification)
    - [Definition](#definition)
    - [Comparison to Other Methods](#comparison-to-other-methods)
    - [Challenges of Formal Verification](#challenges-of-formal-verification)
  - [🔧 Tools: Program Verifiers, Symbolic Execution Tools, and Others](#-tools-program-verifiers-symbolic-execution-tools-and-others)
  - [🎤 Specification Languages for Creating Formal Specifications](#-specification-languages-for-creating-formal-specifications)
  - [👨🏾‍💻 Exercises, Tutorials, and Examples](#-exercises-tutorials-and-examples)

## 🤔 Introduction to Formal Verification

### Definition

Formal verification is a method of mathematically proving that a computer program - for example, a smart contract - functions as intended. It involves translating the code of the contract into a formal representation (such as mathematical models and logic) and then using automated tools (like theorem provers or model checkers) to verify that the specifications and properties of the contract hold true. Formal verification detects flaws in code and logic, ensuring the contract's correctness, reducing vulnerabilities, and preventing potential financial losses.

### Comparison to Other Methods

- **Symbolic Execution**: Symbolic execution is a technique used within formal verification. It involves running a program with symbolic values instead of concrete inputs. It explores as many program paths as possible, checking for errors. Compared to formal verification, it does not provide a mathematical proof of correctness. Its focus is on finding bugs rather than proving their absence. It is a less comprehensive method in comparison to formal verification (but more practical in exploring complex code paths).
- **Unit Testing**: Unit testing involves testing individual components (units) of a program to ensure they work as expected. This method is less comprehensive than formal verification but more practical and easier to implement. It's excellent for catching specific, localized bugs but doesn't address system-wide correctness. Unit testing is critical early in the development process to ensure each component functions correctly.
- **Fuzz Testing**: Fuzz testing involves inputting random, unexpected, or invalid data (fuzz) into the system to test its robustness. It's an excellent method for finding bugs, but it's less structured and can't guarantee comprehensive coverage or correctness like formal verification. Fuzz testing is most beneficial when you want to test the resilience of a system against malformed or malicious inputs.

### Challenges of Formal Verification

Formal verification, despite its robust approach to ensuring the correctness of computer programs like smart contracts, presents challenges and constraints including:

- **Limited Scope**: While formal verification is powerful in proving the correctness of code against its specifications, it's only as good as the specifications themselves. If the specifications are incomplete, incorrect, or ambiguous, the verification process might not identify all potential issues. Moreover, it doesn't typically account for real-world scenarios or user interactions that lie outside the specified parameters.
- **Difficulty in Handling External Interactions**: Smart contracts often interact with external systems (like external smart contracts) and data sources. Formal verification can struggle to account for the unpredictable nature of these external interactions, potentially overlooking vulnerabilities that arise from such dynamics.
- **Handling State Space Explosion**: Handling state space growth can be difficult as the number of states grows when exploring contracts with features like loops and recursive calls. When the state space becomes too large, exploring all possible states and transitions can become infeasible.
- **Constraint Solving Complexities**: Particularly in Decentralized Finance (DeFi), contracts involve complex mathematical expressions, such as non-linear arithmetic, which are difficult for common solvers to handle. These complexities can impede the ability to fully verify correctness.

Despite these challenges, the ability to mathematically prove the correctness of smart contracts can significantly reduce the risk of bugs and vulnerabilities, leading to safer and more reliable protocols. It is important to note that while formal verification can greatly enhance the security of Web3 solutions, it is not a silver bullet; it should be used in conjunction with other testing methods, such as unit testing, fuzz testing, and manual code reviews, to ensure more comprehensive security.

## 🔧 Tools: Program Verifiers, Symbolic Execution Tools, and Others

- **Certora**: Certora is a formal verification tool which utilizes automated verification and supports bounded model checking. It uses the CVL language for specifying contracts, allowing for detailed description of critical properties. Certora provides a reliable and robust toolset, continuously evolving with strong community support.
  - [GitHub](https://github.com/Certora)
  - [Documentation](https://docs.certora.com/en/latest/)
- **Solidity SMTChecker**: Solidity’s SMTChecker is a built-in model checker based on SMT (Satisfiability Modulo Theories) and Horn solving. It confirms if a contract’s source code matches specifications during compilation and statically checks for violations of safety properties.
  - [Solidity GitHub](https://github.com/ethereum/solidity)
  - [Documentation](https://docs.soliditylang.org/en/latest/smtchecker.html)
- **KEVM**: KEVM is a formal semantics of the Ethereum Virtual Machine (EVM) written in the K framework. It is executable and can prove property-related assertions using reachability logic.
  - [GitHub](https://github.com/runtimeverification/evm-semantics)
  - [Documentation](https://docs.runtimeverification.com/kevm/overview/kevm-semantics-of-evm-in-k#documentation-support)
- **EthBMC**: EthBMC is a bounded model checker for EVM bytecode based on symbolic execution. It is implemented in Rust and supports several SMT solvers (Z3, Yices2, Boolector).
  - [GitHub](https://github.com/RUB-SysSec/EthBMC)
  - [Academic Paper](https://www.usenix.org/system/files/sec20fall_frank_prepub_0.pdf)
- **hevm**: hevm is a symbolic evaluator for the Ethereum Virtual Machine (EVM). It uses symbolic execution to evaluate existing tests and detect assertion violations, offering users flexibility in choosing how to use it.
  - [GitHub](https://github.com/ethereum/hevm)
  - [Documentation](https://hevm.dev)
- **Mythril**: Mythril is a tool developed by ConsenSys for analyzing EVM bytecode. It uses symbolic execution to detect a wide range of security vulnerabilities in Solidity smart contracts.
  - [GitHub](https://github.com/ConsenSys/mythril)
  - [Documentation](https://mythril-classic.readthedocs.io/en/latest/)
- **Halmos**: Halmos is a symbolic testing tool for EVM smart contracts developed by a16z. It uses symbolic execution to identify assertion violations.
  - [GitHub](https://github.com/a16z/halmos)
  - [Getting Started](https://github.com/a16z/halmos/blob/main/docs/getting-started.md)
- **Kontrol**: Kontrol is a tool by Runtime Verification that combines KEVM and Foundry. It simplifies the verification process by eliminating the need to learn a new language or tool, making it accessible even for developers who aren't verification engineers.
  - [GitHub](https://github.com/runtimeverification/kontrol)
  - [Documentation](https://docs.runtimeverification.com/kontrol/overview/readme)
- **ERCx**: ERCx is a property testing tool for ERC tokens developed by Runtime Verification. It generates detailed reports about its analysis of the token, providing insights into the token's operation.
  - [Tool](https://ercx.runtimeverification.com/)
- **Manticore**: Manticore is a symbolic execution tool developed by Trail of Bits. Though it's no longer maintained by Trail of Bits, it continues to serve as a valuable tool for vulnerability detection and automatic generation of test cases.
  - [GitHub](https://github.com/trailofbits/manticore)
  - [Documentation](https://manticore.readthedocs.io/en/latest/index.html)
- **Z3**: Z3 is an efficient SMT solver developed by Microsoft. It's used in various fields, including formal verification of software.
  - [GitHub](https://github.com/Z3Prover/z3)
  - [Guide](https://microsoft.github.io/z3guide/)
- **Isabelle**: Isabelle/HOL is a proof assistant developed by Microsoft Research. It allows mathematical formulas to be expressed in a formal language and provides tools for proving those formulas.
  - [GitHub](https://github.com/isabelle-prover)
  - [Documentation](https://isabelle.in.tum.de/documentation.html)
- **Coq**: Coq is an interactive theorem prover developed by INRIA. It allows you to define programs using theorems and interactively generate machine-checked proofs of correctness.
  - [GitHub](https://github.com/coq/coq)
  - [Documentation](https://coq.inria.fr/doc/master/refman/)

## 🎤 Specification Languages for Creating Formal Specifications

- **Act**: Act is a tool that enables specification of storage updates, pre/post conditions, and contract invariants. It includes proof backends that can validate many properties using Coq, SMT solvers, or hevm.
  - [GitHub](https://github.com/ethereum/act)
  - [Documentation](https://ethereum.github.io/act/)
- **Certora Verification Language (CVL)**: CVL is a language used by Certora, a tool for verifying smart contracts. It provides a structured way to express the properties of smart contracts, enabling formal verification of their correctness.
  - [Documentation](https://docs.certora.com/en/latest/docs/cvl/index.html)
- **Scribble**: Scribble is a tool that transforms code annotations in the Scribble specification language into concrete assertions that check the specification.
  - [GitHub](https://github.com/ConsenSys/Scribble)
  - [Documentation](https://docs.scribble.codes)
- **Dafny**: Dafny is a programming language designed to facilitate the construction of correct and efficient software. It uses high-level annotations to reason about and prove the correctness of code.
  - [GitHub](https://github.com/dafny-lang/dafny)
  - [Documentation](http://dafny.org/dafny/)

## 👨🏾‍💻 Exercises, Tutorials, and Examples

- **Examples for Certora, Halmos, and Kontrol from Cyfrin**: This GitHub repository provides examples demonstrating how to use Certora, Halmos, and Kontrol for formal verification of smart contracts. It's a great resource for understanding how to apply these tools in practice.
  - [Repository with Example Test Suites](https://github.com/Cyfrin/sc-exploits-minimized/tree/main/test/invariant-break/formal-verification)
- **Symbolic Execution with Manticore, Mythril, hevm, and EthBMC**: This document provides a comprehensive overview of how to use symbolic execution tools. It covers how these tools can be used to verify properties of smart contracts.
  - [Symbolic Execution Tutorial](https://hackmd.io/@SaferMaker/EVM-Sym-Exec#What-can-they-do)
- **Demo: Formal verification of ERC721A with Halmos**: This article shows how to use Halmos to symbolically test and formally verify ERC721A, a highly gas-optimized implementation of the ERC721 standard. It's a practical demonstration of how to use Halmos for formal verification.
  - [Halmos Formal Verification Demo](https://a16zcrypto.com/posts/article/symbolic-testing-with-halmos-leveraging-existing-tests-for-formal-verification/#section--6)
- **SMTChecker Tutorial, from Solidity Documentation**: This tutorial covers examples of using SMTChecker - a built-in model checker in Solidity - for overflow, assert, state properties, and external calls + reentrancy.
  - [SMTChecker Tutorial](https://docs.soliditylang.org/en/latest/smtchecker.html#tutorial)
