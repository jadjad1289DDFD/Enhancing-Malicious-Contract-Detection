
# Enhancing-Malicious-Contract-Detection : Combating Bytecode Manipulation and Address-based Evasion


# Overview : 

In the example below, we observe that the Inferno Drainer deploys contracts to bypass address-based detection. This proposal aims to counter such manipulations by flagging contracts based on high bytecode similarity, funder/entity relationships, and transaction patterns.

https://etherscan.io/address/0x000002e5a6b6949752a693d3dc6a3314c6150000#code : reported that this address was used in a Phishing scam.

https://etherscan.io/address/0x9744afd8ab8825eae9b6ee7c76a8e135253a13f0#code  :  not reported .

both contracts share the same bytecode ,funder and same transaction patterns making contract 2 is highly likely to be malicious  malicious, even if it hasn't been reported yet.

# Bytecode Similarity:
If two contracts (A and B) share either identical or highly similar bytecode, it is likely that they are the same or related contracts. While perfect bytecode matching minimizes the risk of collisions, recognizing high similarity (e.g., small changes or obfuscation ) can help identify potentially malicious contracts attempting to bypass detection.

# Funder/Entity Check: 
Along with bytecode matching, verify whether the funder or any associated address of contract B is linked to a known malicious actor (e.g., contract A). If the funders or related addresses match,linked contract B should be flagged as potentially malicious.

# Risk Minimization:  
This approach reduces false positives, as bytecode collisions are rare. Even if slight variations in bytecode exist, the combination with funder/entity tracking and transaction patterns offers a reliable flagging method.

# Heuristic Enhancements:  
To further validate, transaction patterns or known malicious functions can be incorporated, enhancing detection accuracy.



This approach can be integrated into address-based detection systems or explorer labeling to more effectively counter tactics where actors deploy similar bytecode contracts, with funders or related addresses matching or being linked, to evade address-based detection

