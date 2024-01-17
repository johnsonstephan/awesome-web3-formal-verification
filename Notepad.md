### Tools: Program Verifiers, Symbolic Execution Tools, and Others

### (Symbolic Execution Based Tools

- **ERCx**: ERCx is a property testing tool for ERC tokens developed by Runtime Verification. It generates detailed reports about its analysis of the token, providing insights into the token's operation. [ERCx](https://ercx.runtimeverification.com/)
- **Manticore**: Manticore is a symbolic execution tool developed by Trail of Bits. Though it's no longer maintained by Trail of Bits, it continues to serve as a valuable tool for vulnerability detection and automatic generation of test cases. [Manticore GitHub](https://github.com/trailofbits/manticore)
- **Z3**: Z3 is an efficient SMT solver developed by Microsoft. It's used in various fields, including formal verification of software and hardware. [Z3 GitHub](https://github.com/Z3Prover/z3)
- **Isabelle**: Isabelle/HOL is a proof assistant developed by Microsoft Research. It allows mathematical formulas to be expressed in a formal language and provides tools for proving those formulas. [Isabelle GitHub](https://github.com/isabelle-prover)
- **Coq**: Coq is an interactive theorem prover developed by INRIA. It allows you to define programs using theorems and interactively generate machine-checked proofs of correctness. [Coq GitHub](https://github.com/coq/coq)

- [Halmos (a16z's symbolic testing tool for EVM smart contracts)](https://github.com/a16z/halmos)
- [Kontrol (Runtime Verification's tool)](https://docs.runtimeverification.com/kontrol/overview/readme)​ combines KEVM and to grant developers the ability to perform without learning a new language or tool. This is especially useful for those who are not verification engineers. Additionally, developers can leverage Foundry test suites they have already developed and use symbolic execution to increase the level of confidence.
  the newer Ethereum Foundation fork for our experiments. hevm is implemented in Haskell and supports Z3 and cvc5 as solvers.
- [ERCx (Runtime Verification's Property testing tool for ERC tokens)](https://ercx.runtimeverification.com/) ERCx generates structured and detailed reports about its analysis of the token
- [Manticore (Trail of Bits' Symbolic execution tool)](https://github.com/trailofbits/manticore). This project is no longer internally developed and maintained as of Jul 11, 2023. A symbolic execution tool that is developed by Trail of Bits. Manticore is implemented in Python and supports several SMT solvers (Z3, Yices2, Boolector, cvc4). Manticore has several interfaces: it can be used as a CLI tool, through its Python API, or using manticore-verifier—a property-based symbolic execution tool. Besides vulnerability detection, Manticore automatically generates test cases corresponding to the execution paths identified through symbolic execution

### Other Tools

- [Z3 (Microsoft's efficient SMT solver)](https://github.com/Z3Prover/z3)
- [Isabelle](https://github.com/isabelle-prover) Isabelle/HOL is a proof assistant that allows mathematical formulas to be expressed in a formal language and provides tools for proving those formulas. The main application is the formalization of mathematical proofs and in particular formal verification, which includes proving the correctness of computer hardware or software and proving properties of computer languages and protocols.
- [Coq](https://github.com/coq/coq) Coq is an interactive theorem prover that lets you define programs using theorems and interactively generate machine-checked proofs of correctness

### Specification Languages for Creating Formal Specifications

- [Act](https://github.com/ethereum/act): Act allows specification of storage updates, pre/post conditions and contract invariants. Its tool suite also has proof backends able to prove many properties via Coq, SMT solvers, or hevm
- [Certora Verification Language (CVL)](https://docs.certora.com/en/latest/docs/cvl/index.html) Used by the Certora verification tool to write properties about analyzed contracts.
- [Scribble](https://github.com/ConsenSys/Scribble): Scribble transforms code annotations in the Scribble specification language into concrete assertions that check the specification
- [Dafny](https://github.com/dafny-lang/dafny): Dafny is a verification-ready programming language that relies on high-level annotations to reason about and prove correctness of code

### Real-World Case Studies

**Cetora**

- [MakerDao](https://github.com/Certora/Examples/tree/master/RealBugsFound/MakerDao) The contract Vat represents an intermediate product during preparation for deployment of Multi Collateral DAI on other domains. The invariant fundamental_equation_of_dai fails because the function Vat.init(ilk) is called when Vat.ils[ilk].Rate is zero as required , yet Vat.ilks[ilk].Art is non-zero
- [Balancer V2](https://github.com/verified-network/balancer-v2-verified/tree/master/audits/certora)

**K-framework, Runtime Verification**

- [Formal Verification of Casper Smart Contract](https://github.com/runtimeverification/verified-smart-contracts/blob/master/casper/README.md) We present the formal verification of the Casper FFG smart contract. This work was supported by the security grant from the Ethereum Foundation
- [GnosisSafe contract](https://github.com/runtimeverification/verified-smart-contracts/blob/master/gnosis/GnosisSafe_RuntimeVerification.pdf)
- [Uniswap contract](https://github.com/runtimeverification/verified-smart-contracts/blob/master/uniswap/README.md) We present a lightweight formal verification of the Uniswap smart contract, a decentralized token exchange contract, specifically uniswap_exchange.vy. Our lightweight verification consists of two parts: Formalization of the "x\*y=k" market maker model and its smart contract implementation. Symbolic execution of the compiled bytecode of four important functions
- [DappSys DSToken ERC20 token contract](https://github.com/runtimeverification/verified-smart-contracts/blob/master/erc20/ds-token/README.md) The DSToken ERC20 token is a high-profile ERC20 token contract written in Solidity by DappHub. We found that the DSToken ERC20 token deviates from the ERC20-K (and thus ERC20-EVM) specification
- [Bihu KEY token operation contracts](https://github.com/runtimeverification/verified-smart-contracts/blob/master/bihu/README.md) Bihu is a blockchain-based ID system, and KEY is the utility token for the Bihu ID system and community. The smart contracts requested to be formally verified are the ones for operating the KEY token
- [MyKidsEducationToken ERC20 token contract](https://github.com/runtimeverification/verified-smart-contracts/blob/master/erc20/hobby/README.md)
- [OpenZeppelin ERC20 token contract](https://github.com/runtimeverification/verified-smart-contracts/blob/master/erc20/zeppelin/README.md). The OpenZeppelin ERC20 token is a high-profile ERC20 token contract written in Solidity by Zeppelin, a consulting firm for smart contracts that provides security audits. We found that the OpenZeppelin token deviates from the ERC20-K (and thus ERC20-EVM) specification
- [HackerGold (HKG) ERC20 token contract](https://github.com/runtimeverification/verified-smart-contracts/blob/master/erc20/hkg/README.md). The HackerGold (HKG) token is an ERC20 token written in Solidity, which became well-known when a serious security vulnerability was discovered that even survived a security audit performed by Zeppelin. Specifically, the bug was due to a typographical error in the source code, using =+ instead of += for updating a receiver’s balance during a transfer, which would allow an attacker to reset an account balance. This security issue was resolved by deploying a new, fixed contract and reissuing the tokens.

### Exercises, Tutorials, and Examples

**Certora**

- [Certora Prover and CVL Examples](https://github.com/Certora/Examples)
- [Certora Prover Tutorials](https://docs.certora.com/projects/tutorials/en/latest/)
  - [ERC20 Example with Certora](https://github.com/Certora/Examples/tree/master/DEFI/ERC20) Example Certora verification for ERC20 contracts
  - [Liquidity Pool Example with Certora](https://github.com/Certora/Examples/tree/master/DEFI/LiquidityPool) Example Certora Prover verification for a simple multi-contract system
  - [Constant Product Pool with Certora](https://github.com/Certora/Examples/tree/master/DEFI/ConstantProductPool)
  - [Examples for CVL Commands](https://github.com/Certora/Examples/tree/master/CVLByExample)

**Others**

- [Examples for Certora, Halmos, and Kontrol from Cyfrin](https://github.com/Cyfrin/sc-exploits-minimized/tree/main/test/invariant-break/formal-verification)
- [Symbolic Execution with Manticore, Mythril, hevm, and EthBMC](https://hackmd.io/@SaferMaker/EVM-Sym-Exec#What-can-they-do) This repository contains a collection of examples illustrating CVL usage. The specifications are compatible with CVL2.

[Demo: Formal verification of ERC721A with Halmos](https://a16zcrypto.com/posts/article/symbolic-testing-with-halmos-leveraging-existing-tests-for-formal-verification/#section--6) To demonstrate the capabilities of Halmos, we used it to symbolically test and formally verify ERC721A, a highly gas-optimized implementation of the ERC721 standard that allows for batch minting at almost the same cost as single minting.
[SMTChecker Tutorial, from Solidity Documentation](https://docs.soliditylang.org/en/latest/smtchecker.html#tutorial) Covers examples for Overflow, Assert, State Properties, and External Calls + Reentrancy.
[Symbolic Execution With ds-test, from Ethereum](https://fv.ethereum.org/2020/12/11/symbolic-execution-with-ds-test/) The latest release of hevm incorporates the recently introduced symbolic execution features into its unit testing framework. This lets smart contract developers formulate and prove properties in Solidity using the dapp development framework. Formally verifying properties should now be no harder than writing a property based test. In fact, it uses almost the exact same syntax. In this tutorial we will show how to use these new features to prove properties of your smart contracts.
[Exercise 2. Developing Symbolic Execution Tools for EVM Using Z3](https://github.com/WilfredTA/formal-methods-curriculum/blob/master/courses/2_Approaches_Modeling_Verification/exercises/1_Symbolic_Execution/exercise_2.md) The goal of this exercise is to familiarize yourself with the details of symbolic execution techniques. In contrast to Exercise 1 where we have utilized the API of an existing symbolic execution tool, this exercise is focused on building our our EVM-level symbolic execution engine using Z3 as a constraint solver
[Z3 Tutorial from Philip Zucker](https://colab.research.google.com/github/philzook58/z3_tutorial/blob/master/Z3%20Tutorial.ipynb)

[Symbolic execution for hevm from Ethereum](https://fv.ethereum.org/2020/07/28/symbolic-hevm-release/) In this tutorial we will show how to use the new capabilities of hevm, and discuss some of its unique features as a symbolic execution engine. The latest release of hevm introduces symbolic execution features which can be used for checking smart contracts for correctness, step through the execution space of live contracts, or prove equivalence between them.

[EVM Symbolic Execution from Will Berman](https://github.com/williamberman/evm-symbolic-execution/blob/master/EVM%20Symbolic%20Execution.ipynb) Our goal is to add symbolic execution to a rust based implementation of the EVM
[Runtime Verification Brings Formal Verification to Algorand](https://runtimeverification.com/blog/runtime-verification-brings-formal-verification-to-algorand) We are happy to announce the public beta of KAVM — the formal semantics of the Algorand Virtual Machine built with the K framework! By building KAVM, we want to make it easier for Algorand developers to formally specify and verify smart contracts. In this tutorial, we will look at an Algorand smart contract implemented in PyTeal, which implements a Vault for K Coins. Users can interact with the Vault to mint K Coins in exchange for their Algos and to burn their K Coins to redeem the Algos. We will use KAVM to formally verify that the mint and burn methods of the KCoint Vault work as expected.
[How to use Manticore to Find Bugs in Smart Contracts](https://ethereum.org/en/developers/tutorials/how-to-use-manticore-to-find-smart-contract-bugs/) The aim of this tutorial is to show how to use Manticore to automatically find bugs in smart contracts.
[Exercise 1. Practical Symbolic Execution using Manticore](https://github.com/WilfredTA/formal-methods-curriculum/blob/master/courses/2_Approaches_Modeling_Verification/exercises/1_Symbolic_Execution/exercise_1.md) The purpose of this exercise is to equip you with hands-on experience of applying existing symbolic execution tools to analyze smart contracts. The exercise is based on Manticore—a symbolic execution engine developed in Python by Trail of Bits. It is also inspired by the Manticore's own tutorial
[Formal Methods for DeFi Developers](https://github.com/WilfredTA/formal-methods-curriculum/) Formal methods training program with an emphasis on software in the blockchain & decentralized financed (DeFi) industry

### Articles

[How Formal Verification of Smart Contracts Works](https://runtimeverification.com/blog/how-formal-verification-of-smart-contracts-works) In this post, we'll describe – in general terms – the process of verifying a smart contract.
[Formal Verification of Smart Contracts](https://ethereum.org/en/developers/docs/smart-contracts/formal-verification/)
[Formal Verification 101 for Blockchain Systems and Smart Contracts](https://runtimeverification.com/blog/formal-verification-101-for-blockchain-systems-and-smart-contracts) In this first article, we hope to provide a generalized and gentle introduction to formal verification (without specific reference to the blockchain or smart contracts) and why we need it
[Formal Verification & Symbolic Execution | The Security Silver Bullet?](https://patrickalphac.medium.com/formal-verification-symbolic-execution-the-security-silver-bullet-38e0ac9072eb) We look at formal verification & symbolic execution with two Trail of Bits Web3 security team members. Additionally, we review the value these techniques bring and compare them to other tools
[What Is Formal Verification of Smart Contracts?](https://academy.binance.com/en/articles/what-is-formal-verification-of-smart-contracts)
[Formal Verification in Web3 Security Testing](https://df3ndr.com/Book/2/11/8-formal_verification.html#formal-verification-in-web3-security-testing)
[Testing and Formal Verification for Web3 Smart Contract Security](https://blog.quillaudits.com/trending/testing-and-formal-verification/)
[A Guide to Formal Verification of Smart Contracts, Halborn](https://www.halborn.com/blog/post/a-guide-to-formal-verification-of-smart-contracts)
[What is Formal Verification in Smart Contract Auditing?](https://www.certik.com/resources/blog/3UDUMVAMia8ZibM7EmPf9f-what-is-formal-verification?ref=nodereal.ghost.io)
[End-to-End Formal Verification of Ethereum 2.0 Deposit Smart Contract](https://runtimeverification.com/blog/ end-to-end-formal-verification-of-ethereum-2-0-deposit-smart-contract)
[Formal Verification helps finding insolvency bugs — Balancer V2 Bug Report](https://medium.com/certora/formal-verification-helps-finding-insolvency-bugs-balancer-v2-bug-report-1f53ee7dd4d0)
[Formally Verifying the World's Most Popular Smart Contract](https://www.zellic.io/blog/formal-verification-weth/) In this blog post, we prove critical safety guarantees and invariants within the WETH contract. We do so by leveraging Z3, a battle-tested SMT solver
[SMTChecker and Formal Verification, from Solidity Documentation](https://docs.soliditylang.org/en/latest/smtchecker.html)
[Part I, Symbolic Execution: Everything You Wanted to Know About Symbolic Execution for Ethereum Smart Contracts (But Were Afraid to Ask)](https://hackmd.io/@SaferMaker/EVM-Sym-Exec)
[Part II, Symbolic Execution: The Easy Way To Quit (Concrete) Testing](https://hackmd.io/@SaferMaker/EVM-Sym-Test)
[When Invariants Aren’t: DAI’s Certora Surprise](https://hackmd.io/@SaferMaker/DAICertoraSurprise)
[My introduction to Z3 and solving satisfiability problems](https://infosecadalid.com/2021/08/27/my-introduction-to-z3-and-solving-satisfiability-problems/)
[Formal Verification of ERC-20 Tokens](https://www.certik.com/resources/blog/6nL1ogDyekFC7nfCt9n0LR-formal-verification-of-erc-20-tokens-part-one)
[DeepSEA: Advanced Web3 Formal Verification of a Smart Contract Compiler](https://www.certik.com/resources/blog/54rMfDcB9KAF5PS4G9kiy0-deepsea-advanced-web3-formal-verification-of-a-smart-contract-compiler)
[Symbolic testing with Halmos: Leveraging existing tests for formal verification](https://a16zcrypto.com/posts/article/symbolic-testing-with-halmos-leveraging-existing-tests-for-formal-verification/)
[SMTChecker, Remix & Dapptools from Ethereum](https://fv.ethereum.org/2021/12/01/smtchecker-dapptools/)
[Automated Synthesis of External Unknown Functions from Ethereum](https://fv.ethereum.org/2021/01/18/smtchecker-and-synthesis-of-external-functions/) The SMTChecker, a formal verification module built-in the Solidity compiler, received a lot of improvements in 2020. Many improvements are related to Solidity’s language features, such as structs, ABI, hash and math functions, and other important features that were unsupported. When running the tool, the user now has more control and is able to set a timeout per query and choose engines separately between BMC and CHC. The CHC engine encodes Solidity code as Constrained Horn Clauses and is often able to handle loops and contract invariants. The internals of the CHC engine will be detailed in an upcoming series of posts. CHC has been extended to analyze external calls to unknown code and report counterexamples including transaction traces, which are the focus of this post.

### YouTube Videos

**Certora**

[What is Certora and Formal Verification - Simply Explained](https://www.youtube.com/watch?v=8ON0Vpo7zls)
[Smart Contract Security Using Certora Prover with Chandrakana Nandi](https://www.youtube.com/watch?v=62tCJGBcvOY) Join us live as Patrick Collins interviews Chandrakana Nandi from Certora, a pioneer in smart contract security. Dive into the world of advanced smart contract auditing with insights from Certora's cutting-edge technologies. Discover how Certora is revolutionizing blockchain security with its innovative tools and methodologies. Don't miss this exclusive session for an in-depth look at the future of smart contract verification and security
[Ethereum Malaysia 2023: Scaling Formal Verification to Find Bugs in Complex Smart Contract Systems](https://www.youtube.com/watch?v=bae9U-PuTS8) Formal verification is a technique for detecting bugs and mathematically proving their absence. By comparing the existing behavior of the program to its desired behavior, code security is drastically increased. However, most tools do not scale to handle realistic programs. Mooly will explain how the Certora Prover successfully verifies programs with 10,000 lines of Solidity code.
[Formal Verification for Fun and Profit (Playlist)](https://www.youtube.com/playlist?list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj) Formal Verification for Fun and Profit teaches participants how to use the Certora Prover to find bugs in smart contracts without any prior knowledge. The workshop was held at Paris during EthCC, 21-23 July, 2022
[Understanding the Workflow of the Certora Prover](https://www.youtube.com/watch?v=c5ViO3Dpfqs) This talk will give a high-level overview of the Certora Prover. We will look at examples of contracts and their specifications and understand what the different steps of the Certora Prover do in order to verify smart contracts.
[Certora Workshop: Aave Community Day 1 4/27/22](https://www.youtube.com/watch?v=c8ZwKAvaiR0) Michael George reviews the CVL Language - writing basic rules and understanding verification results
[Certora Workshop: Aave Community Day 2 4/28/22](https://www.youtube.com/watch?v=QukwpzHhPL0) Michael George reviews thinking through properties - thinking about high-level properties while working on a generic liquidity pool
[Certora Workshop: Aave Community Day 3 4/29/22](https://www.youtube.com/watch?v=Per7Ylb1TJA) Nurit shows us how to find real bugs. - practice your newly acquired skills on examples based on bugs found in the real-world
[Bad Proofs in Formal Verification](https://archive.devcon.org/archive/watch/6/bad-proofs-in-formal-verification/?tab=YouTube) Formal verification can be a huge boon to smart contract security as it checks all possible execution paths. Unfortunately, even verified code can be faulty if the formal specification contains mistakes. "Bad" proofs can lead to false confidence in the code and premature deployment. This talk will discuss different types of "bad" proofs and how to avoid them.

[Formal Verification of Smart Contracts and Protocols: What, Why, How (Devcon5)](https://www.youtube.com/watch?v=xggtkB7w3es) This talk will explain what formal verification is in the context of blockchain smart contracts, tokens and protocols, why it is becoming increasingly critical, how it is done, and what tools are available. Several approaches are covered, from automated and light-weight that find bugs to interactive and comprehensive that analyze all the behaviors, from high-level source-code that developers write and understand to low-level bytecode that is executed by node clients

[Formal Verification of Smart Contracts Made Easy (Devcon5)](https://www.youtube.com/watch?v=tq5XH3JedqM) In this hands-on workshop, we will go through the process of formally verifying smart contracts. The attendees will learn (1) how to formally specify relevant functional requirements of Ethereum contracts, such as "the sum of deposits never exceeds the contract’s balance", and (2) how to verify these using existing analysis tools for Ethereum.

[Formal Verification of Smart Contracts: Dr. Christian Reitwiessner - IC3-Ethereum Crypto Boot Camp](https://www.youtube.com/watch?v=rx0NPckEWGI)

[EthCC : Fully Automated Formal Verification: How far can we go?](https://www.youtube.com/watch?v=RunMhlTtdKw) Fully automated formal verification of smart contracts is undecidable. Different contracts present different challenges for verification tools, in the form of loops, math, heavy data structures, complex control flow, or a mix of it all. In this talk we will discuss an experiment with real world contracts and several automated security tools; advantages and disadvantages of different approaches; and dive deeper into hevm, a symbolic execution, fuzzing and debugging tool for EVM bytecode, and the SMTChecker, a model checker built in the Solidity compiler

[Formal verification: the road to complete security of smart contracts - Martin Lundfall](https://www.youtube.com/watch?v=UT7c-fg8hbg)

[Formally verifying Morpho - Quentin Garchery, DeFi Security Summit 2023](https://www.youtube.com/watch?v=tOnqf7_rATE) Morpho is a peer-to-peer layer atop lending protocols that boasts identical risk parameters and liquidity yet offers enhanced rates.
Formal Verification ensures that the code matches a specification mathematically. DeFi projects, characterized by compact codebases, high-stakes systems, and permanent code, align well with Formal Verification. Quentin shows how Morpho uses three formal verification tools: Certora, Halmos, and Why3. This video details the pros and cons of each and which tasks they are best suited for.

[Formal Verification @ ETHDenver, 2023](https://www.youtube.com/watch?v=Eoaf6xB5G7w) Official video of Blockswap’s Multichain ERC20 event at ETHDenver 2023. In this video, Andreas Lynge (Formal Verification Engineer at Blockswap) and Armen Ter-Avetisyan (Security Engineer at Certora) explain how Formal Verification works and is implemented in Blockchain development
[Runtime Verification - Security Techniques & Formal Verification for Developers @ Multichain ETH](https://www.youtube.com/watch?v=lDVOe0eunt0)
[Symbolic Execution & Formal Verification | Trail Of Bits Head of Blockchain Engineering](https://youtu.be/3pWYvtx_sjA?si=3M7Stw9MssVfOG7T)
[Secereum - Audit Techniques and Tools 101, Formal Verification](https://www.youtube.com/watch?v=8IbkWnTLueU&t=555s)
[Guide To Formal Verification | Take Security To The Next Level](https://www.youtube.com/watch?v=imSy7Ll9ftg)
[Formal Verification Speedrun with Halmos, Kontrol, and Certora](https://www.youtube.com/watch?v=pjwYr97Q-Ok) We walk through how to do formal verification with Halmos, Kontrol, and Certora and show how easy it can be.
[Formal Verification & Symbolic Execution | W/ Trail Of Bits](https://www.youtube.com/watch?v=izpoxfTSaFs)
[The Symbolic Solidity Debugger, Secureum Trust X 2023](https://www.youtube.com/watch?v=irwV7c8cFRY)
[A Unified Framework for Formal Verification of Vyper Bytecode using Halmos, Secureum Trust X 2023](https://www.youtube.com/watch?v=ABdFd54VfwY)
[Formal Verification of Smart Contracts - Yoichi Hirai](https://www.youtube.com/watch?v=cCUGMAnCh7o&list=PLaM7G4Llrb7wPiT2G75tj2JQr8qg6P5hi&index=4)

[DeFi security Summit 2023 - Session 14: Formal Verification Panel](https://www.youtube.com/watch?v=vdMEGBllxLs) Panelists: Fraser Brown, CTO, Cubist and Assistant Professor, Carnegie Mellon University + Ghila Castelnuovo, R&D Director, Certora + Grigore Rosu, CEO, Runtime Verification + Jon Stephens, CTO, Veridise + JulianSutherland, Head of formal verification, Nethermind

[DefiSummer: Formal Verification of DeFi Projects](https://www.youtube.com/watch?v=Ck2WgIha6dQ) On this edition of the #DefiSummer hackathon workshop series, we are happy to have Everett Hildenbrandt, CTO of Runtime Verification is covering the formal verification of DeFi projects. In this video, Everett covers: a background on RunTime Verification, What formal verification is & its use cases, Mitigating blockchain vulnerabilities, Specification, Demo: ACT Specificiation, Q&A

[Yan Michalevsky on Ethereum Bugs Through the Lens of Formal Verification](https://www.youtube.com/watch?v=Ru6X043Q63U) Yan's abstract follows:"The DAO bug employed callbacks to steal $150M. Callbacks are essential in many programming environments, but drastically complicate program understanding and reasoning because they allow to mutate object’s local states by external objects in unexpected fashions, thus breaking modularity. We define the notion of Effectively Callback Free (ECF) objects in order to allow callbacks without preventing modular reasoning. We study the decidability of dynamically checking ECF in a given execution trace and statically checking if an object is ECF. We also show that dynamically checking ECF in Ethereum is feasible and can be done online. By running the history of all execution traces in Ethereum, we were able to verify that virtually all existing contract executions, excluding these of the DAO or of contracts with similar known vulnerabilities, are ECF. Finally, we show that ECF, whether it is verified dynamically or statically, enables modular reasoning about objects with encapsulated state."

[Formal Methods for the Informal Engineer: Tutorial #1 - The Z3 Theorem Prover](https://www.youtube.com/watch?v=56IIrBZy9Rc)
[Solc-verify, a source-level formal verification tool for Solidity smart contracts by Akos Hajdu](https://www.youtube.com/watch?v=1q2gSm3NuQA) Solc-verify is a source-level formal verification tool for Soldity smart contracts, developed in collaboration with SRI International. Solc-verify takes smart contracts written in Solidity and discharges verification conditions using modular program analysis and SMT solvers. Built on top of the Solidity compiler, solc-verify reasons at the level of the contract source code. This enables solc-verify to effectively reason about high-level functional properties while modeling low-level language semantics (e.g., the memory model) precisely. The contract properties, such as contract invariants, loop invariants, function pre- and post-conditions and fine grained access control can be provided as in-code annotations by the developer. This enables automated, yet user-friendly formal verification for smart contracts
[Episode 284 - Using Formal Verification on ZK Systems with Jon Stephens](https://www.youtube.com/watch?v=c-NqsK_f388) This week Anna Rose chats with Jon Stephens (Computer Science Ph.D. student in the UToPiA group at UT Austin and co-founder of Veridise. Veridise is a blockchain auditing firm that audits smart contracts and ZK systems. They discuss what led Jon to work on system security, what tools are available to test the security of ZK systems and the process of performing formal verification on ZK systems. They also cover general ZK security, why this topic matters and ways we can incentivise ethical disclosures when bugs and vulnerabilities are found.
[Concordium Smart Contracts and Formal Verification](https://www.youtube.com/watch?v=fTmKciK71Lc) Discover with Associate Professor Bas Spitters Concordium Smart Contracts and Formal Verification.
Professor Spitters heads the formal verification team at the Concordium Blockchain Research Center at Aarhus University, Denmark.
Formal verification is a technique to prove, with mathematical certainty, that software meets its formal specification, thus making sure it behaves as desired. It is the highest level of software quality.

### Research

[Formal Verification of Smart Contracts](https://dl.acm.org/doi/pdf/10.1145/2993600.2993611)In this paper, we outline a framework to analyze and formally verify Ethereum smart contracts using F functional programming language aimed at program verification
Formal Modeling and Verification of Smart Contracts
[Formally Verifying a Real World Smart Contract](https://arxiv.org/pdf/2307.02325.pdf) Nowadays, smart contracts have become increasingly popular and, as
with software development in general, testing is the standard method for
verifying their correctness. However, smart contracts require a higher level
of certainty regarding correctness because they are difficult to modify once
deployed and errors can result in significant financial losses. Therefore,
formal verification is essential. In this article, we present our search for a
tool capable of formally verifying a real-world smart contract written in
a recent version of Solidity
[A Survey of Smart Contract Formal Specification and Verification](https://arxiv.org/pdf/2008.02712.pdf) In this survey, we investigate formal models and specifications
of smart contracts presented in the literature and present a systematic overview in order to understand the common trends.
[Smart Contract Vulnerability Detection Technique: A Survey](https://arxiv.org/pdf/2209.05872.pdf) In this survey,
we first summarize the common types and typical cases of smart
contract vulnerabilities from three levels, i.e., Solidity code layer,
EVM execution layer, and Block dependency layer. Further, we
review the research progress of smart contract vulnerability
detection and classify existing counterparts into five categories,
i.e., formal verification, symbolic execution, fuzzing detection,
intermediate representation, and deep learning. Empirically, we
take 300 real-world smart contracts deployed on Ethereum as the
test samples and compare the representative methods in terms
of accuracy, F1-Score, and average detection time
[Finding smart contract vulnerabilities with ConCert’s property-based testing framework](https://arxiv.org/pdf/2208.00758.pdf) We provide three detailed case studies of vulnerabilities in smart contracts, and show how property
based testing would have found them: 1. the Dexter1 token exchange; 2. the iToken; 3. the ICO of
Brave’s BAT token. The last example is, in fact, new, and was missed in the auditing process.
We have implemented this testing in ConCert, a general executable model/specification of smart
contract execution in the Coq proof assistant. ConCert contracts can be used to generate verified
smart contracts in Tezos’ LIGO and Concordium’s rust language. We thus show the effectiveness of
combining formal verification and property-based testing of smart contracts.
[Fast and Reliable Formal Verification of Smart Contracts with the Move Prover](https://arxiv.org/pdf/2110.08362.pdf) The Move Prover (MVP) is a formal verifier for smart contracts
written in the Move programming language. MVP has an expressive specification language, and is fast and reliable enough that it can be run routinely by
developers and in integration testing. Besides the simplicity of smart contracts
and the Move language, three implementation approaches are responsible for
the practicality of MVP: (1) an alias-free memory model, (2) fine-grained invariant checking, and (3) monomorphization.
[Clockwork Finance: Automated Analysis of Economic Security in Smart Contracts](https://arxiv.org/pdf/2109.04347.pdf) We introduce the Clockwork Finance Framework (CFF), a general purpose, formal verification framework for mechanized reasoning about the economic security properties of composed
decentralized-finance (DeFi) smart contracts.
[Using Fault Injection to Assess Blockchain Systems in Presence of Faulty Smart Contracts](https://arxiv.org/pdf/2006.11597.pdf) In this paper, we use a software implemented fault
injection (SWIFI) technique to assess the behavior of permissioned blockchain systems in the presence of faulty smart contracts. We also study the effectiveness of formal verification (i.e., done by solc-verify) and runtime protections (e.g.,
using the assert statement) mechanisms in detection of injected faults. Results indicate that formal verification as well as additional
runtime protections have to complement built-in platform checks to guarantee the proper dependability of blockchain systems and
applications.
[Formal Verification of Solidity contracts in Event-B](https://arxiv.org/pdf/2005.01261.pdf) This paper proposes a method to meet such
requirements by translating Solidity contracts to Event-B models, supporting
certification.
[Formalising and verifying smart contracts with Solidifier: a bounded model checker for Solidity](https://arxiv.org/pdf/2002.02710.pdf) In this paper, we present a formalisation of Solidity
and the Ethereum blockchain using the Solid language and its blockchain; a Solid
program is obtained by explicating/desugaring a Solidity program. We make some
abstractions that over-approximate the way in which Solidity/Ethereum behave.
Based on this formalisation, we create Solidifier: a bounded model checker for
Solidity.
[User Experience with Language-Independent Formal Verification](https://arxiv.org/pdf/1912.02951.pdf) The goal of this paper is to help mainstream programmers routinely
use formal verification on their smart contracts by 1) proposing a
new YAML-format for writing general-purpose formal specifications, 2) demonstrating how a formal specification can be incrementally built up without needing advanced training, and 3) showing
how formal specifications can be tested by using program mutation
[solc-verify: A Modular Verifier for Solidity Smart Contracts](https://arxiv.org/pdf/1907.04262.pdf) We present solc-verify, a source-level verification tool for
Ethereum smart contracts. solc-verify takes smart contracts written
in Solidity and discharges verification conditions using modular program
analysis and SMT solvers
[VeriSolid: Correct-by-Design Smart Contracts for Ethereum](https://arxiv.org/pdf/1901.01292.pdf) To this end, we introduce the VeriSolid
framework for the formal verification of contracts that are specified using a transition-system based model with rigorous operational semantics.
Our model-based approach allows developers to reason about and verify contract behavior at a high level of abstraction. VeriSolid allows the
generation of Solidity code from the verified models, which enables the
correct-by-design development of smart contracts.
[Formal Modeling and Verification of Smart Contracts with Spin](https://www.mdpi.com/2079-9292/11/19/3091) This paper aims to verify the correctness of smart contracts in Ethereum transactions, and the model checker Spin is adopted for the formal verification of smart contracts in order to ensure their execution with respect to parties’ willingness, as well as their reliable interaction with clients. In this direction, we propose a formal method to construct the models for smart contracts
[Formal Verification of Smart Contracts Based on Users and Blockchain Behaviors Models](https://www.researchgate.net/publication/324175498_Formal_Verification_of_Smart_Contracts_Based_on_Users_and_Blockchain_Behaviors_Models) In this paper, wepropose a novel formal modeling approach to verify a smartcontract behavior in its execution environment. We apply thisformalism on a concrete smart contract example and analyze itsbreaches with a statistical model checking approach.

---

**Services**
[Certora](https://www.certora.com/audits)
[Runtime Verification](https://runtimeverification.com/smartcontract)
[Veridise](https://veridise.com/)
[CertiK](https://www.certik.com/products/formal-verification)
[Nethermind](https://www.nethermind.io/formal-verification)
[ShellBoxes](https://shellboxes.com/services/blockchain-security/formal-verification/)
[Beosin](https://beosin.com/product/vaas?lang=en-US)
[Sec3](https://www.sec3.dev/audit)
**Unsure**

Tools
[The K Framework (Runtime Verification's formal verification framework)](https://kframework.org/). is a powerful formal verification framework that enables deductive verification and interactive theorem proving. Its underlying theory and implementation provide a high level of expressiveness, making it suitable for verifying complex programs and algorithms. However, it should be noted that K is not designed with heavy emphasis on automated verification and lacks certain automation features which can require more manual effort during the verification process. To use the K framework, formal specifications are written in the K language, which must be learned prior to use. Its strength is particularly useful in verifying complex systems, which may be challenging to analyze using automated reasoning.

Case Study: PRBMath
https://twitter.com/zachobront/status/1679540903030013952

---

**Pending**

Section 11: Formal Verification & Symbolic Execution | the video is pending release

- https://github.com/Cyfrin/security-and-auditing-full-course-s23?tab=readme-ov-file#section-11-formal-verification--symbolic-execution
