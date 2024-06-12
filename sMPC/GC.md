# Introduction
This is project is about Garbled Circuits, and their integration with the UPMEM PIM

# Garbled Circuit
A cryptographic protocol that enable two mistrusting parties to evaluate a function without revealing their private input without presence of third trusted party.
Implementation of the protocols are in the following libraries.
- [TinyGarble](https://github.com/IntelLabs/TinyGarble2.0)

## Protocol
Before starting the protocol both parties (Alice and Bob) need to know the function to be evaluated, represented as boolean circuit.
1. Alice garbles (encrypt) the circuit
2. Alice sends the garbled circuit to Bob along with her encrypted input
3. To calculate the circuit Bob needs to garble his own input as well, so he needs the help of the Garbler (Alice). Bob encrypts with the help of oblivious transfer in which he is the receiver of the transfer.
4. Bob then decrypt and evaluates the circuit.
5. Alice and Bob communicates to learn the output.
	
## Garbling Process
1.Alice (the Garbler) assigns two random k-bit labels (usually 128 bits) to each wire in the circuit, representing the Boolean values 0 and 1.
2.A truth table is created with the randomly chosen labels, and the output is encrypted using double key encryption, with the keys being the corresponding input labels.

## Oblivious Transfer
## Evaluation and Revealing the outputs
## Security Settings
- Semi-honest
- Malicious

# Related Work
- [MAGE](https://www.usenix.org/conference/osdi21/presentation/kumar)