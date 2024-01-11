Definition

- Symbolic execution is a program analysis technique which explores multiple execution paths at the same time. If a program is run concretely, i.e., on a specific concrete input, a single control flow path of this program is explored. In contrast, symbolic execution assigns symbolic—rather than concrete—values to input variables that determine which paths should be be executed. A symbolic value represents an arbitrary value that can be assigned to a variable. Symbolic execution can therefore be viewed as a way to generalize testing.
- For each explored control flow path of a program, a symbolic execution engine maintains (1) a path condition—a first-order logic [1] formula over variable values that captures the conditions satisfied by the branches taken along that path, and (2) a symbolic memory store that maps variables to symbolic expressions or values computed along that paths. An execution of a branch statement updates the path condition, while an assignment updates the store.
- Symbolic execution is commonly used to check whether a certain property can be violated by any program execution, i.e., if a certain vulnerable state is reachable. To determine state reachability, symbolic execution engines typically rely on an off-the-shelf satisfiability modulo theories (SMT) solver, such as Z3. Since reachability of a state corresponds to the feasibility of a path leading to it, the path condition is given to an SMT solver to check its satisfiability. An SMT solver either finds a satisfying concrete assignment to symbolic variables, thus demonstrating path feasibility, or proves that a formula is unsatisfiable, indicating that no satisfying assignment exists and the path is infeasible. An SMT-solver can also be used to generate concrete program inputs that will cause a specific paths to execute, which can be used to automatically generate test cases.

Challenges
Although useful for various analyses, exhaustive exploration of all possible execution paths performed by symbolic execution comes with certain performance and scalability constraints.

The challenges include:

- Handling state space explosion (the number of states grows exponentially in the number of system components, and exploring smart contracts with, e.g., loops and recursive calls might be infeasible within reasonable resource constraints)
- Constraint solving (certain types of constraints pose a difficulty to SMT solvers—these include non-linear arithmetic expressions which are common in DeFi smart contracts, e.g., the Uniswap invariant)=
- Modeling memory (which can be fully symbolic, partially symbolic, or concretized)
- Interaction with the environment (e.g., calling other smart contracts and accounting for possible side effects)

Documentation
[SMTChecker and Formal Verification](https://docs.soliditylang.org/en/latest/smtchecker.html)

(Symbolic Execution / Formal Verification) Tools

- [Halmos (a16z's symbolic testing tool for EVM smart contracts)](https://github.com/a16z/halmos)
- [Certora](https://docs.certora.com/en/latest/). is a formal verification tool for smart contracts that focuses on automated verification and supports bounded model checking, similar to Halmos. To use Certora, developers must learn their new language, CVL, in order to write specifications. This language allows for the concise description of many critical properties through contract invariants, a feature that Halmos currently does not support. Despite being a closed-source, proprietary tool, Certora provides robust formal verification tooling, with ongoing development and good user support.
- [Mythril (ConsenSys' security analysis tool for EVM bytecode)](https://github.com/ConsenSys/mythril) A security analysis tool for EVM bytecode that performs vulnerability detection using symbolic execution. Mythril is developed by ConsenSys. It’s implemented in Python and uses Z3 as an SMT solver through its Python API.
- [Kontrol (Runtime Verification's tool)](https://docs.runtimeverification.com/kontrol/overview/readme)​ combines KEVM and to grant developers the ability to perform without learning a new language or tool. This is especially useful for those who are not verification engineers. Additionally, developers can leverage Foundry test suites they have already developed and use symbolic execution to increase the level of confidence.
- [hevm (symbolic EVM evaluator)](https://github.com/ethereum/hevm) is another formal verification tool that is similar to Halmos. It was previously part of DappTools, which is a precursor of Foundry. Both HEVM and Halmos have the feature of not requiring a separate specification and can symbolically execute existing tests to identify assertion violations. This allows users to use both tools interchangeably or run them in parallel for the same tests, providing them with multiple options for symbolic testing. A symbolic execution engine and equivalence checker for EVM bytecode. Initially developed as part of the dapptools framework, hevm has been forked by Ethereum Foundation and is currently under active development—we are using the newer Ethereum Foundation fork for our experiments. hevm is implemented in Haskell and supports Z3 and cvc5 as solvers.
- [EthBMC (A Bounded Model Checker for Smart Contracts)](https://github.com/RUB-SysSec/EthBMC) A bounded model checker for EVM bytecode based on symbolic execution developed in Ruhr-University Bochum. The only academic tool that made it into our list, EthBMC has been proposed in an academic paper presented at Usenix Security, 2020. A distinctive feature of EthBMC is its support of concrete validation of the identified counterexamples using geth. EthBMC is implemented in Rust and supports several SMT solvers (Z3, Yices2, Boolector).
- [ERCx (Runtime Verification's Property testing tool for ERC tokens)](https://ercx.runtimeverification.com/) ERCx generates structured and detailed reports about its analysis of the token
- [Manticore (Trail of Bits' Symbolic execution tool)](https://github.com/trailofbits/manticore). This project is no longer internally developed and maintained as of Jul 11, 2023. A symbolic execution tool that is developed by Trail of Bits. Manticore is implemented in Python and supports several SMT solvers (Z3, Yices2, Boolector, cvc4). Manticore has several interfaces: it can be used as a CLI tool, through its Python API, or using manticore-verifier—a property-based symbolic execution tool. Besides vulnerability detection, Manticore automatically generates test cases corresponding to the execution paths identified through symbolic execution

Other Tools
[Z3 (Microsoft's efficient SMT solver)](https://github.com/Z3Prover/z3)

Exercises and Tutorials
[Symbolic Execution with Manticore, Mythril, hevm, and EthBMC](https://hackmd.io/@SaferMaker/EVM-Sym-Exec#What-can-they-do)
[Demo: Formal verification of ERC721A with Halmos](https://a16zcrypto.com/posts/article/symbolic-testing-with-halmos-leveraging-existing-tests-for-formal-verification/#section--6) To demonstrate the capabilities of Halmos, we used it to symbolically test and formally verify ERC721A, a highly gas-optimized implementation of the ERC721 standard that allows for batch minting at almost the same cost as single minting.
[SMTChecker Tutorial, from Solidity Documentation](https://docs.soliditylang.org/en/latest/smtchecker.html#tutorial) Covers examples for Overflow, Assert, State Properties, and External Calls + Reentrancy.
[Symbolic Execution With ds-test, from Ethereum](https://fv.ethereum.org/2020/12/11/symbolic-execution-with-ds-test/) The latest release of hevm incorporates the recently introduced symbolic execution features into its unit testing framework. This lets smart contract developers formulate and prove properties in Solidity using the dapp development framework. Formally verifying properties should now be no harder than writing a property based test. In fact, it uses almost the exact same syntax. In this tutorial we will show how to use these new features to prove properties of your smart contracts.
[Exercise 2. Developing Symbolic Execution Tools for EVM Using Z3](https://github.com/WilfredTA/formal-methods-curriculum/blob/master/courses/2_Approaches_Modeling_Verification/exercises/1_Symbolic_Execution/exercise_2.md) The goal of this exercise is to familiarize yourself with the details of symbolic execution techniques. In contrast to Exercise 1 where we have utilized the API of an existing symbolic execution tool, this exercise is focused on building our our EVM-level symbolic execution engine using Z3 as a constraint solver
[Symbolic execution for hevm from Ethereum](https://fv.ethereum.org/2020/07/28/symbolic-hevm-release/) In this tutorial we will show how to use the new capabilities of hevm, and discuss some of its unique features as a symbolic execution engine. The latest release of hevm introduces symbolic execution features which can be used for checking smart contracts for correctness, step through the execution space of live contracts, or prove equivalence between them.
[Z3 Tutorial from Philip Zucker](https://colab.research.google.com/github/philzook58/z3_tutorial/blob/master/Z3%20Tutorial.ipynb)
[EVM Symbolic Execution from Will Berman](https://github.com/williamberman/evm-symbolic-execution/blob/master/EVM%20Symbolic%20Execution.ipynb) Our goal is to add symbolic execution to a rust based implementation of the EVM
[Runtime Verification Brings Formal Verification to Algorand](https://runtimeverification.com/blog/runtime-verification-brings-formal-verification-to-algorand) We are happy to announce the public beta of KAVM — the formal semantics of the Algorand Virtual Machine built with the K framework! By building KAVM, we want to make it easier for Algorand developers to formally specify and verify smart contracts. In this tutorial, we will look at an Algorand smart contract implemented in PyTeal, which implements a Vault for K Coins. Users can interact with the Vault to mint K Coins in exchange for their Algos and to burn their K Coins to redeem the Algos. We will use KAVM to formally verify that the mint and burn methods of the KCoint Vault work as expected.
[How to use Manticore to Find Bugs in Smart Contracts](https://ethereum.org/en/developers/tutorials/how-to-use-manticore-to-find-smart-contract-bugs/) The aim of this tutorial is to show how to use Manticore to automatically find bugs in smart contracts.
[Exercise 1. Practical Symbolic Execution using Manticore](https://github.com/WilfredTA/formal-methods-curriculum/blob/master/courses/2_Approaches_Modeling_Verification/exercises/1_Symbolic_Execution/exercise_1.md) The purpose of this exercise is to equip you with hands-on experience of applying existing symbolic execution tools to analyze smart contracts. The exercise is based on Manticore—a symbolic execution engine developed in Python by Trail of Bits. It is also inspired by the Manticore's own tutorial

Articles
[SMTChecker and Formal Verification, from Solidity Documentation](https://docs.soliditylang.org/en/latest/smtchecker.html)
[Part I, Symbolic Execution: Everything You Wanted to Know About Symbolic Execution for Ethereum Smart Contracts (But Were Afraid to Ask)](https://hackmd.io/@SaferMaker/EVM-Sym-Exec)
[Part II, Symbolic Execution: The Easy Way To Quit (Concrete) Testing](https://hackmd.io/@SaferMaker/EVM-Sym-Test)
[When Invariants Aren’t: DAI’s Certora Surprise](https://hackmd.io/@SaferMaker/DAICertoraSurprise)
[My introduction to Z3 and solving satisfiability problems](https://infosecadalid.com/2021/08/27/my-introduction-to-z3-and-solving-satisfiability-problems/)
[Symbolic testing with Halmos: Leveraging existing tests for formal verification](https://a16zcrypto.com/posts/article/symbolic-testing-with-halmos-leveraging-existing-tests-for-formal-verification/)
[SMTChecker, Remix & Dapptools from Ethereum](https://fv.ethereum.org/2021/12/01/smtchecker-dapptools/)
[Automated Synthesis of External Unknown Functions from Ethereum](https://fv.ethereum.org/2021/01/18/smtchecker-and-synthesis-of-external-functions/) The SMTChecker, a formal verification module built-in the Solidity compiler, received a lot of improvements in 2020. Many improvements are related to Solidity’s language features, such as structs, ABI, hash and math functions, and other important features that were unsupported. When running the tool, the user now has more control and is able to set a timeout per query and choose engines separately between BMC and CHC. The CHC engine encodes Solidity code as Constrained Horn Clauses and is often able to handle loops and contract invariants. The internals of the CHC engine will be detailed in an upcoming series of posts. CHC has been extended to analyze external calls to unknown code and report counterexamples including transaction traces, which are the focus of this post.

YouTube Videos
[Formal Verification & Symbolic Execution | W/ Trail Of Bits](https://www.youtube.com/watch?v=izpoxfTSaFs)
[Formal Methods for the Informal Engineer: Tutorial #1 - The Z3 Theorem Prover](https://www.youtube.com/watch?v=56IIrBZy9Rc)

---

**Unsure**

Tools
[The K Framework (Runtime Verification's formal verification framework)](https://kframework.org/). is a powerful formal verification framework that enables deductive verification and interactive theorem proving. Its underlying theory and implementation provide a high level of expressiveness, making it suitable for verifying complex programs and algorithms. However, it should be noted that K is not designed with heavy emphasis on automated verification and lacks certain automation features which can require more manual effort during the verification process. To use the K framework, formal specifications are written in the K language, which must be learned prior to use. Its strength is particularly useful in verifying complex systems, which may be challenging to analyze using automated reasoning.

Case Study: PRBMath
https://twitter.com/zachobront/status/1679540903030013952

---

**Pending**

Section 11: Formal Verification & Symbolic Execution | the video is pending release

- https://github.com/Cyfrin/security-and-auditing-full-course-s23?tab=readme-ov-file#section-11-formal-verification--symbolic-execution
