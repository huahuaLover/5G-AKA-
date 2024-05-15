# 5G-AKA改进协议

 This instruction describes the organization of the source code and how to use it.

## File explanation

The folder contains the formal models of 5G-AKA改进协议 implemented with Tamarin, as well as screenshots of the formal analysis results.

- **5G_AKA_Enhanced_Autn.spthy** contains the model used to analyze the authentication and secrecy of 5G-AKA-Enhanced.
- **5G_AKA_Enhanced_Secret.spthy** contains the model used to analyze the secrecy of 5G-AKA-Enhanced.
-  **5G_AKA_Enhanced_Fix.spthy** contains the model used to analyze the fix of 5G-AKA-Enhanced.
- **5G_AKA_Enhanced_Passive.spthy** contains the model used to analyze the privacy of 5G-AKA-Enhanced under passive attackers.
- **5G_AKA_Enhanced_Active.spthy** contains the model used to analyze the privacy of 5G-AKA-Enhanced under active attackers.

## How to run

### How to reproduce the results (authentication and secrecy goals)

This analysis uses version 1.8.0 of the Tamarin-prover. Due to the complexity of the proofs, tactics that guide the proof search are required. Since the tactics have been embedded in the 5G_ESAKA.spthy, the file just needs to be run as shown below.

`tamarin-prover interactive .`

Once an interactive Tamarin session is launched, one can select and load the 5G_ESAKA.spthy and navigate through the model and the different lemmas.

Lemmas can be proven automatically using our tactics(clicking 'a').

### How to reproduce the results (privacy goals)

The  privacy goals are modeled as an observational equivalence property and therefore relies on the diff-equivalence mode of Tamarin.

The command that should be used is:

`tamarin-prover interactive . --diff`












​	
