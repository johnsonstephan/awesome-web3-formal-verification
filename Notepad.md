YouTube Video
[Formal Verification & Symbolic Execution | W/ Trail Of Bits](https://www.youtube.com/watch?v=izpoxfTSaFs)

Documentation
[SMTChecker and Formal Verification](https://docs.soliditylang.org/en/latest/smtchecker.html)

(Symbolic Execution / Formal Verification) Tools
[Halmos (a16z's symbolic testing tool for EVM smart contracts)](https://github.com/a16z/halmos)
[Certora](https://docs.certora.com/en/latest/). is a formal verification tool for smart contracts that focuses on automated verification and supports bounded model checking, similar to Halmos. To use Certora, developers must learn their new language, CVL, in order to write specifications. This language allows for the concise description of many critical properties through contract invariants, a feature that Halmos currently does not support. Despite being a closed-source, proprietary tool, Certora provides robust formal verification tooling, with ongoing development and good user support.
[Mythril (ConsenSys' security analysis tool for EVM bytecode)](https://github.com/ConsenSys/mythril)
[Kontrol (Runtime Verification's tool)](https://docs.runtimeverification.com/kontrol/overview/readme)​ combines KEVM and to grant developers the ability to perform without learning a new language or tool. This is especially useful for those who are not verification engineers. Additionally, developers can leverage Foundry test suites they have already developed and use symbolic execution to increase the level of confidence.
[hevm (symbolic EVM evaluator)](https://github.com/ethereum/hevm) is another formal verification tool that is similar to Halmos. It was previously part of DappTools, which is a precursor of Foundry. Both HEVM and Halmos have the feature of not requiring a separate specification and can symbolically execute existing tests to identify assertion violations. This allows users to use both tools interchangeably or run them in parallel for the same tests, providing them with multiple options for symbolic testing.
[EthBMC (A Bounded Model Checker for Smart Contracts)](https://github.com/RUB-SysSec/EthBMC)
[ERCx (Runtime Verification's Property testing tool for ERC tokens)](https://ercx.runtimeverification.com/) ERCx generates structured and detailed reports about its analysis of the token
[Manticore (Trail of Bits' Symbolic execution tool)](https://github.com/trailofbits/manticore). This project is no longer internally developed and maintained as of Jul 11, 2023.

Other Tools
[Z3 (Microsoft's efficient SMT solver)](https://github.com/Z3Prover/z3)

Articles
[Part I, Symbolic Execution: Everything You Wanted to Know About Symbolic Execution for Ethereum Smart Contracts (But Were Afraid to Ask)](https://hackmd.io/@SaferMaker/EVM-Sym-Exec)
[Part II, Symbolic Execution: The Easy Way To Quit (Concrete) Testing](https://hackmd.io/@SaferMaker/EVM-Sym-Test)
[When Invariants Aren’t: DAI’s Certora Surprise](https://hackmd.io/@SaferMaker/DAICertoraSurprise)
[My introduction to Z3 and solving satisfiability problems](https://infosecadalid.com/2021/08/27/my-introduction-to-z3-and-solving-satisfiability-problems/)
[Symbolic testing with Halmos: Leveraging existing tests for formal verification](https://a16zcrypto.com/posts/article/symbolic-testing-with-halmos-leveraging-existing-tests-for-formal-verification/)

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
