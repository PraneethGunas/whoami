# What's in my Masters?

&nbsp;  
&nbsp;  
&nbsp;  

## Network Security
> We focus on key protocols like TLS, DNSSEC, Routing, and Email Security, while exploring vulnerabilities and countermeasures. Recent study areas include certificate pinning in mobile apps, QUIC adoption, and its scalability, Destination-Side Source Address Validation (DSAV), Adoption of Route Origin Validation across autonomous systems etc. I’m currently trying to alayse reply attacks in TLS 1.3 during the data trasfer in 0-RTT handshake at the time of session resumption
&nbsp;

## Systems and Security

> We built the [Interprocedural Cryptographic API Misuse Dataset](https://github.com/PraneethGunas/CryptoFlowSafety) (TypeScript) to provide practical examples of secure and insecure cryptographic API usage within cryptocurrency applications. My focus was on demonstrating how security properties can propagate across different functions and modules, uncovering vulnerabilities that could lead to significant financial losses.
&nbsp;

## Blockchain Technologies
> Developed a robust, Rust-based [command-line tool](https://github.com/PraneethGunas/bitcoin-multisig-wallet) for key recovery in m-of-n Bitcoin multisig schemes. This addresses the
critical vulnerability of standard multisig wallets, where the loss of even a single original public key can prevent recovery, even if all private keys are retained. My tool enables recovery with only 'm' keys, significantly improving operational resilience using OP_RETURN.
&nbsp;

## Thesis — The Cost of Custody
> First empirical comparison of four active Bitcoin covenant proposals — [CTV (BIP-119)](https://bips.dev/119/), [CCV (BIP-443)](https://bips.dev/443/), [OP_VAULT (BIP-345)](https://bips.dev/345/), and [CAT+CSFS (BIP-347+348)](https://bips.dev/348/) — across 15 on-chain experiments on regtest. Built a [four-axis security framework](https://research.praneethg.xyz) mapping design choices (fee model, amount flexibility, recovery gating, recovery binding) to their structural attack surfaces. Discovered a critical covenant-bypass in CCV where undefined mode bytes trigger OP_SUCCESS and silently disable all vault protections, and a batched-defender ordering flip where CCV and OP_VAULT swap safety rankings depending on the watchtower's recovery strategy. Also implemented a [Simplicity vault on Elements](https://github.com/PraneethGunas/simple-simplicity-vault) as a cross-substrate reference point.
&nbsp;
