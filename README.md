# 5G-ESAKA: An Efficient and Secure Authentication and Key Agreement Protocol for 5G without SQN

This is the repository for our paper "5G-ESAKA: An Efficient and Secure Authentication and Key Agreement Protocol for 5G without SQN". This instruction describes the organization of the source code and how to use it.

## File explanation

The **model** folder contains the formal models of 5G-ESAKA implemented with Tamarin, as well as screenshots of the formal analysis results.

- **model/5G_ESAKA.spthy** contains the model used to analyze the authentication and secrecy of 5G-ESAKA.
- **model/5G_ESAKA_passive.spthy** contains the model used to analyze the privacy of 5G-ESAKA under passive attackers.
- **model/5G_ESAKA_active.spthy** contains the model used to analyze the privacy of 5G-ESAKA under active attackers.

The **evaluation** folder contains the code for computational cost evaluation of 5G-ESAKA. This project references relevant code on cryptographic operations from the open-source project [Free5GC](https://github.com/free5gc/free5gc). To run the project, you can open "**evaluation/Evaluate**" as a new project in GoLand.

- **evaluation\Evaluate\src\main\main.go** contains the main function to evaluate the computational costs of 5G-AKA and 5G-ESAKA. You can obtain the evaluation result by running the main function.
- **evaluation\Evaluate\src\main\5G_AKA.go** contains cryptographic operations required for running 5G-AKA.
- **evaluation\Evaluate\src\main\5G_ESAKA.go** contains cryptographic operations required for running 5G-ESAKA.
- **evaluation\Evaluate\src\main\evaluation.go** contains code for 5G-AKA and 5G-ESAKA to perform related cryptographic operations on three entities, UE, SN and HN.
- **evaluation\Evaluate\src\main\global.go** includes some variables required for the protocol operation, and fixed values are provided here to simplify the evaluation.
- **evaluation\Evaluate\src\main\util.go** contains some utility functions used during the evaluation process.
- **evaluation\evaluation_results.png** is a screenshot of the results obtained after running **evaluation\Evaluate\src\main\main.go**, which illustrates the computational costs required for 5G-ESAKA and 5G-AKA on UE, SN, and HN sides.

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

### How to reproduce the results (computational costs)

For computational costs evaluation, open **evaluation/Evaluate** as a new project in GoLand and run **main.go**.










​	
