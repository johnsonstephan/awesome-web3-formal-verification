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
  - [📝 Articles](#-articles)
  - [🍿 Videos](#-videos)
  - [🚀 Contributing](#-contributing)
  - [Share with The Community](#share-with-the-community)

## 🤔 Introduction to Formal Verification

### Definition

Formal verification is a method of mathematically proving that a computer program (for example, a smart contract) functions as intended. It involves translating the code of the contract into a formal representation (such as mathematical models and logic) and then using automated tools (like theorem provers or model checkers) to verify that the specifications and properties of the contract hold true. In Web3, formal verification detects flaws in code and logic, ensuring the contract's correctness, reducing vulnerabilities, and preventing potential financial losses.

<p align="center">
  <img width="55%" height="auto" src="https://www.azquotes.com/picture-quotes/quote-the-job-of-formal-methods-is-to-elucidate-the-assumptions-upon-which-formal-correctness-tony-hoare-72-10-09.jpg">
</p>

### Comparison to Other Methods

- **Symbolic Execution**: Symbolic execution is a technique used within formal verification. It involves running a program with symbolic values instead of concrete inputs. It explores as many program paths as possible, checking for errors. Compared to formal verification, it does not provide a mathematical proof of correctness. Its focus is on finding bugs rather than proving their absence. It is a less comprehensive method in comparison to formal verification (but more practical in exploring complex code paths).
- **Fuzz Testing**: Fuzz testing involves inputting random, unexpected, or invalid data (fuzz) into the system to test its robustness. It's an excellent method for finding bugs, but it's less structured and can't guarantee comprehensive coverage or correctness like formal verification. Fuzz testing is most beneficial when you want to test the resilience of a system against malformed or malicious inputs.
- **Unit Testing**: Unit testing involves testing individual components (units) of a program to ensure they work as expected. This method is less comprehensive than formal verification but more practical and easier to implement. It's excellent for catching specific, localized bugs but doesn't address system-wide correctness. Unit testing is especially useful early in the development process to ensure each component functions correctly.

### Challenges of Formal Verification

Formal verification, despite its robust approach to ensuring the correctness of programs like smart contracts, presents challenges and constraints including:

- **Limited Scope**: While formal verification is powerful in proving the correctness of code against its specifications, it's only as good as the specifications themselves. If the specifications are incomplete, incorrect, or ambiguous, the verification process might not identify all potential issues. Moreover, it doesn't typically account for real-world scenarios or user interactions that lie outside the specified parameters.
- **Difficulty in Handling External Interactions**: Smart contracts often interact with external systems (like external smart contracts) and data sources. Formal verification can struggle to account for the unpredictable nature of these external interactions, potentially overlooking vulnerabilities that arise from such dynamics.
- **Handling State Space Explosion**: Handling state space growth can be difficult as the number of states grows when exploring contracts with features like loops and recursive calls. When the state space becomes too large, exploring all possible states and transitions can become infeasible.
- **Constraint Solving Complexities**: Particularly in Decentralized Finance (DeFi), contracts involve complex mathematical expressions, such as non-linear arithmetic, which are difficult for common solvers to handle. These complexities can impede the ability to fully verify correctness.

Despite these challenges, the ability to mathematically prove the correctness of smart contracts can significantly reduce the risk of bugs and vulnerabilities, leading to safer and more reliable protocols. It is important to note that while formal verification can greatly enhance the security of Web3 protocols, it is not a silver bullet. Formal verification should be used in conjunction with other testing methods, such as unit testing, fuzz testing, and manual code reviews, to ensure more comprehensive security.

## 🔧 Tools: Program Verifiers, Symbolic Execution Tools, and Others

_Utilize these tools to continue building your security toolkit._

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

_Understand these languages to take your understanding to the next level with creating specs._

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

_Continue moving along the learning curve with these insightful materials for hands-on practice._

- **Examples for Certora, Halmos, and Kontrol from Cyfrin**: This GitHub repository provides examples demonstrating how to use three different tools for formal verification of smart contracts. It's a great resource for understanding how to apply these tools in practice.
  - [Repository with Example Test Suites](https://github.com/Cyfrin/sc-exploits-minimized/tree/main/test/invariant-break/formal-verification)
- **Symbolic Execution Tutorial with Manticore, Mythril, hevm, and EthBMC**: This document provides a comprehensive overview of how to use four different symbolic execution tools. It covers how these tools can be used to verify properties of smart contracts.
  - [Symbolic Execution Tutorial](https://hackmd.io/@SaferMaker/EVM-Sym-Exec#What-can-they-do)
- **Halmos Demo, Formal verification of ERC721A**: This article shows how to use Halmos to symbolically test and formally verify ERC721A, a highly gas-optimized implementation of the ERC721 standard. It's a practical demonstration of how to use Halmos for formal verification.
  - [Halmos Formal Verification Demo](https://a16zcrypto.com/posts/article/symbolic-testing-with-halmos-leveraging-existing-tests-for-formal-verification/#section--6)
- **SMTChecker Tutorial, from Solidity Documentation**: This tutorial shares examples of using SMTChecker for overflow, assert, state properties, external calls, and reentrancy.
  - [SMTChecker Tutorial](https://docs.soliditylang.org/en/latest/smtchecker.html#tutorial)
- **Symbolic execution for hevm, from Ethereum**: This tutorial demonstrates how to use hevm, a symbolic execution engine for EVM bytecode.
  - [hevm Symbolic Execution Tutorial](https://fv.ethereum.org/2020/07/28/symbolic-hevm-release/)
- **Symbolic Execution With ds-test, from Ethereum**: This tutorial shows how to use the symbolic execution features of hevm in its unit testing framework.
  - [hevm Tutorial with ds-test](https://fv.ethereum.org/2020/12/11/symbolic-execution-with-ds-test/)
- **Z3 Tutorial from Philip Zucker**: This tutorial provides a comprehensive introduction to Z3, a powerful SMT solver developed by Microsoft.
  - [Z3 Comprehensive Tutorial](https://colab.research.google.com/github/philzook58/z3_tutorial/blob/master/Z3%20Tutorial.ipynb)
- **Developing Symbolic Execution Tools for EVM Using Z3**: This exercise aims to familiarize you with the details of symbolic execution techniques by building an EVM-level symbolic execution engine using Z3 as a constraint solver.
  - [Z3 Exercise in Symbolic Execution Tooling Development](https://github.com/WilfredTA/formal-methods-curriculum/blob/master/courses/2_Approaches_Modeling_Verification/exercises/1_Symbolic_Execution/exercise_2.md)
- **EVM Symbolic Execution from Will Berman**: This is a project which demonstrates how to add symbolic execution to a rust-based implementation of the EVM.
  - [EVM Symbolic Execution](https://github.com/williamberman/evm-symbolic-execution/blob/master/EVM%20Symbolic%20Execution.ipynb)
- **How to use Manticore to Find Bugs in Smart Contract, from Ethereum**: This tutorial shows how to use Manticore, a symbolic execution tool, to automatically find bugs in smart contracts.
  - [Manticore Tutorial](https://ethereum.org/en/developers/tutorials/how-to-use-manticore-to-find-smart-contract-bugs/)
- **Practical Symbolic Execution using Manticore**: This exercise equips you with hands-on experience of applying existing symbolic execution tools to analyze smart contracts with Manticore.
  - [Manticore Exercise](https://github.com/WilfredTA/formal-methods-curriculum/blob/master/courses/2_Approaches_Modeling_Verification/exercises/1_Symbolic_Execution/exercise_1.ipynb)
- **Course: Formal Methods for DeFi Developers**: This is a formal methods training program with an emphasis on blockchain and DeFi. It is designed to be a comprehensive resource to onboard blockchain developers to formal methods research and development.
  - [Formal Methods Training Course](https://github.com/WilfredTA/formal-methods-curriculum/)
- **Runtime Verification Brings Formal Verification to Algorand**: This tutorial examines an Algorand smart contract, which implements a Vault for K Coins. Users can interact with the Vault to mint K Coins in exchange for their Algos and to burn their K Coins to redeem the Algos. KAVM is used to formally verify that the mint and burn methods of the KCoint Vault work as expected.
  - [Algorand Formal Verification Tutorial with KAVM](https://runtimeverification.com/blog/runtime-verification-brings-formal-verification-to-algorand)

## 📝 Articles

_Read these articles to gain a deeper understanding of formal verification._

- **Formal Verification of Smart Contracts**: This Ethereum documentation provides a comprehensive overview of formal verification of smart contracts. It covers topics like formal models, specifications, techniques and why use formal verification for smart contracts.
  - [Formal Verification Documentation from Ethereum](https://ethereum.org/en/developers/docs/smart-contracts/formal-verification)
- **What Is Formal Verification of Smart Contracts?**: This article discusses what formal verification is, including how it works, its importance, and the manual auditing versus formal verification process.
  - [What Is Formal Verification? from Binance](https://academy.binance.com/en/articles/what-is-formal-verification-of-smart-contracts)
- **Formal Verification 101 for Blockchain Systems and Smart Contracts**: This article provides a gentle introduction to formal verification and its relevance to blockchain systems and smart contracts.
  - [Introduction to Formal Verification from Runtime Verification](https://runtimeverification.com/blog/formal-verification-101-for-blockchain-systems-and-smart-contracts)
- **Formal Verification & Symbolic Execution | The Security Silver Bullet?**: This article explores the role of formal verification and symbolic execution in securing Web3 applications. It provides insights into the benefits these techniques bring and compares them to other tools.
  - [Security Silver Bullet Article](https://patrickalphac.medium.com/formal-verification-symbolic-execution-the-security-silver-bullet-38e0ac9072eb)
- **A Guide to Formal Verification of Smart Contracts from Halborn**: This guide provides an overview of formal verification of smart contracts from the process to considerations.
  - [Guide to Formal Verification](https://www.halborn.com/blog/post/a-guide-to-formal-verification-of-smart-contracts)
- **Understanding Formal Verification**: This blog post provides highlights regarding the concept of formal verification, explaining how it uses mathematical methods to determine whether a smart contract adheres to its specified requirements.
  - [A Summary of Formal Verification](https://www.unvest.io/blog/smart-contract-formal-verification-a-deep-dive-into-tools-and-methodologies-ensuring-contract-correctness)
- **Formal Verification in Web3 Security Testing**: This section of a larger Web3 Security handbook discusses the role of formal verification in security testing.
  - [Formal Verification in Web3 Security Testing](https://df3ndr.com/Book/2/11/8-formal_verification.html#formal-verification-in-web3-security-testing)
- **Testing and Formal Verification for Web3 Smart Contract Security**: This article discusses the process of evaluating the correctness of a contract based on formal specifications. It highlights the importance of formal verification in assessing if the code does what is intended, and how formal verification uses formal methods for specifying, designing, and verifying programs.
  - [Testing and Formal Verification](https://blog.quillaudits.com/trending/testing-and-formal-verification/)
- **What is Formal Verification in Smart Contract Auditing?**: This article discusses what formal verification is and showcases brief sample code.
  - [What is Formal Verification in Smart Contract Auditing?](https://www.certik.com/resources/blog/3UDUMVAMia8ZibM7EmPf9f-what-is-formal-verification)
- **How Formal Verification of Smart Contracts Works**: This blog post provides a detailed description of the process of verifying a smart contract with several useful diagrams.
  - [Comprehensive Process of Smart Contract Verification](https://runtimeverification.com/blog/how-formal-verification-of-smart-contracts-works)
- **End-to-End Formal Verification of Ethereum 2.0 Deposit Smart Contract**: This article provides a walkthrough of the formal verification process for the Ethereum 2.0 deposit smart contract.
  - [Securing Transactions with Ethereum 2.0 Deposit Smart Contract](https://runtimeverification.com/blog/end-to-end-formal-verification-of-ethereum-2-0-deposit-smart-contract)
- **Formal Verification helps finding insolvency bugs — Balancer V2 Bug Report**: This article discusses how formal verification was utilized to identify bugs in the Balancer V2 smart contract.
  - [Utilizing Formal Verification for Bug Identification](https://medium.com/certora/formal-verification-helps-finding-insolvency-bugs-balancer-v2-bug-report-1f53ee7dd4d0)
- **Formally Verifying the World's Most Popular Smart Contract**: This blog post demonstrates how formal verification can be used to prove safety guarantees and invariants within the WETH contract.
  - [Proving WETH with Z3](https://www.zellic.io/blog/formal-verification-weth/)
- **DeepSEA: Advanced Web3 Formal Verification of a Smart Contract Compiler**: This article discusses the advanced formal verification of a smart contract compiler using the DeepSEA methodology.
  - [Advanced Formal Verification of a Smart Contract Compiler](https://www.certik.com/resources/blog/54rMfDcB9KAF5PS4G9kiy0-deepsea-advanced-web3-formal-verification-of-a-smart-contract-compiler)
- **SMTChecker, Remix & Dapptools**: This resource provides a deeper understanding of the use of SMTChecker, Remix, and Dapptools in Ethereum for formal verification.
  - [Ethereum Formal Verification Tools: SMTChecker, Remix, and Dapptools](https://fv.ethereum.org/2021/12/01/smtchecker-dapptools/)
- **SMTChecker and Formal Verification**: This section of the Solidity documentation provides a detailed understanding of SMTChecker, a formal verification tool embedded in the Solidity compiler.
  - [Solidity Documentation: SMTChecker and Formal Verification](https://docs.soliditylang.org/en/latest/smtchecker.html)
- **Automated Synthesis of External Unknown Functions**: This article discusses the process of synthesizing external unknown functions from Ethereum using SMTChecker, providing a practical approach to handling such functions.
  - [Synthesizing External Unknown Functions with SMTChecker](https://fv.ethereum.org/2021/01/18/smtchecker-and-synthesis-of-external-functions/)
- **Everything You Wanted to Know About Symbolic Execution for Ethereum Smart Contracts (But Were Afraid to Ask)**: This first part of a two-part article serves as a comprehensive guide to understanding symbolic execution. This section is focused on analysis, with the next focused on testing.
  - [Symbolic Execution: An Overview](https://hackmd.io/@SaferMaker/EVM-Sym-Exec)
- **The Easy Way To Quit (Concrete) Testing**: This second part of a two-part article serves as a comprehensive guide to understanding symbolic execution. This section is focused on testing, with the previous focused on analysis.
  - [A Simplified Approach to Symbolic Execution](https://hackmd.io/@SaferMaker/EVM-Sym-Test)
- **When Invariants Aren’t: DAI’s Certora Surprise**: This piece highlights the unexpected results obtained from Certora's formal verification of the DAI stablecoin, providing valuable insights into invariant analysis.
  - [Unexpected Findings in DAI's Invariant Analysis](https://hackmd.io/@SaferMaker/DAICertoraSurprise)
- **Formal Verification of ERC-20 Tokens**: This piece delves into the formal verification process for ERC-20 tokens, a widely adopted standard for tokens on the Ethereum blockchain.
  - [ERC-20 Token Formal Verification](https://www.certik.com/resources/blog/6nL1ogDyekFC7nfCt9n0LR-formal-verification-of-erc-20-tokens-part-one)
- **A Introduction to Z3 and Solving Satisfiability Problems**: This resource gives a beginner-friendly introduction to Z3, a powerful theorem prover, and demonstrates its utility in resolving satisfiability problems.
  - [Z3 Theorem Prover: Introduction and Satisfiability Problems](https://infosecadalid.com/2021/08/27/my-introduction-to-z3-and-solving-satisfiability-problems/)
- **Symbolic testing with Halmos: Leveraging existing tests for formal verification**: This article explores how existing tests can be utilized for formal verification using Halmos.
  - [Formal Verification Testing with Halmos](https://a16zcrypto.com/posts/article/symbolic-testing-with-halmos-leveraging-existing-tests-for-formal-verification/)
- **Enhancing Smart Contract Security with Certora’s Formal Verification**: This article explores the use of Certora's formal verification techniques to boost the security of smart contracts.
  - [Certora’s Formal Verification: Enhancing Smart Contract Security](https://medium.com/@JohnnyTime/enhancing-smart-contract-security-with-certoras-formal-verification-34d2f15ccc83)
- **A Guide to Formal Verification of Smart Contracts**: This guide provides a thorough overview of the principles and practices involved in formal verification of Solidity smart contracts.
  - [Guiding Principles for Formal Verification of Smart Contracts](https://www.halborn.com/blog/post/a-guide-to-formal-verification-of-smart-contracts)

## 🍿 Videos

_Watch these videos to learn more about formal verification in Web3._

## 🚀 Contributing

We welcome all contributions and are excited to welcome you aboard.

> #### Have a look at the contributing docs for how to contribute.

- Add new resources
- Suggest changes to existing resources
- Start and join a conversation in discussions
- Give feedback
- Spread the word

## Share with The Community

Please consider sharing a post about "Awesome Web3 Formal Verification" and the value it provides with others.

[![Twitter Share](https://img.shields.io/badge/share%20on-twitter-03A9F4?logo=twitter)](https://twitter.com/share?url=https://github.com/johnsonstephan/Awesome-Web3-Formal-Verification&text=Check%20out%20this%20awesome%20list%20of%20formal%20verification%20resources%20for%20web3!)
[![Reddit Share](https://img.shields.io/badge/share%20on-reddit-red?logo=reddit)](https://reddit.com/submit?url=https://github.com/johnsonstephan/Awesome-Web3-Formal-Verification&title=Awesome%20Web3%20Formal%20Verification%20resources%20for%20security%20researchers)
[![Hacker News](https://img.shields.io/badge/share%20on-hacker%20news-orange?logo=ycombinator)](https://news.ycombinator.com/submitlink?u=https://github.com/johnsonstephan/Awesome-Web3-Formal-Verification)
