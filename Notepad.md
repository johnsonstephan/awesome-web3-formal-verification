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

add: Solidity Summit
