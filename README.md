

AQUARIUM IMPLEMENTATION ROADMAP
The Aquarium Implementation Roadmap outlines a strategic plan to develop a post-quantum secure protocol that is optimized for the needs of the modern computing world. While a full implementation of the protocol would require significant time and resources, the team will focus on implementing the most significant features to meet current needs. The team is committed to maintaining a clear plan for the target specification of the full protocol, ensuring that it remains robust and secure.
To expedite the development process and minimize the risk of errors, the team has decided to leverage existing frameworks and applications rather than reinventing the wheel. By recombining the best parts of other projects, the Aquarium team can achieve a more stable and reliable solution. This approach also enhances the auditability of the source code, making it easier to identify and fix any potential security vulnerabilities.

PHASE 1.
THE FASTEST ANONYMOUS BLOCKCHAIN 
The proposed blockchain implementation is based on Tendermint and aims to be the fastest and most anonymous blockchain. It uses the account and contract off-chain data and on-chain state hash model as defined in the AQUARIUM paper, with a few modifications.
One significant modification is the use of Snarks instead of Starks, which provides better performance for verifying and validating transactions. The transactions use Scnorr signatures, which are more efficient than ECDSA signatures and provide better privacy features.
To save blockchain space and nodes computational power, aggregated transactions use BLS signatures. Accounts are identified by a 4-byte index to minimize transferred data, and a counter is used to record the transaction sequence, which increments its value at every finalized transaction.
The implementation allows transactions to form batches, where a random group of payers can form a common Merkle root state hash, with their individual state hashes as the Merkle tree leaves. These transaction batches carry only a 4-byte index per transaction, indicating the participating accounts.
BLS signatures aggregation with public keys registered once and verified with proofs of possession further enhances privacy and efficiency. Since Tendermint is asynchronous, this setting permits very high transaction throughput.
Finally, the implementation uses SnarkyJS based recursive SNARKS to provide succinct accounts and smart contracts with full data availability. This technology enables highly efficient and private transactions and can support a broad range of blockchain use cases.

PHASE 2.
DECENTRALIZATION 
The current implementation based solely on Tendermint lacks scalability, objectivity, and liveness under extreme conditions. To address these limitations, a Phase 2 upgrade is planned, which involves the introduction of group signing with FROST during attestation on blocks and delegation on these groups. This upgrade will transform staking pools into decentralized staking communities, without the need to modify the underlying Tendermint algorithm.
FROST (Flexible Round-Optimized Schnorr Threshold Signature) is a type of signature that enables secure group signing, which means that a group of validators can collectively sign a message with a single signature. This eliminates the need for each validator to sign individually, reducing the overhead and enabling faster consensus. 
The group signing mechanism will be used during block attestation, where validators will sign off on the validity of the transactions included in the block. By leveraging FROST, a group of validators can sign off on a block with a single signature, increasing efficiency and reducing the risk of failure in extreme conditions. 
Additionally, delegation on these groups will be implemented, which will allow stakers to delegate their voting power to a group of validators they trust. This feature will enable the creation of decentralized staking communities, where stakers can choose to delegate their voting power to a group of validators based on their preferences and criteria.

PHASE 3.
OUROBOROS
In order to combine the speed and safety of tendermint with the liveness and objectivity of Ouroboros, we will let Ouroboros define the Validator set on which tendermint runs. Although Ouroboros has a low finalization speed compared to tendermint, its objective and always-live properties make it an attractive choice for defining the Validator set. By using tendermint to validate transactions with high speed on the Validator set defined by Ouroboros, we can achieve a more secure and reliable blockchain while still maintaining high transaction throughput.

PHASE 4.
NETWORK ANONYMITY
The Aquaris network is designed to provide robust anonymity to its users through the use of Riffle, a privacy-enhancing protocol that ensures strong anonymity for group communication. 
In the current phase of our roadmap, we plan to implement the Aquaris network with a single layer of Riffle groups. 
Clients seeking to join the network will publish a join request and be assigned to a group through the VRF, resulting in a random assignment of clients that makes it virtually impossible for an adversary to compromise the anonymity set of a single group. The network will route user data anonymously by dividing it into fixed-sized packages, routing them across different tunnels.
We are confident that the implementation of the Aquaris network with one layer of Riffle groups will provide users with strong anonymity and security, while also ensuring the network remains efficient and scalable.

PHASE 5.
SSUCCINCTNES
Ouroboros Samasika allows for a succinct description of the whole blockchain, which is only a few kilobytes in size, similar to Mina. This description can inform light nodes about the current Validator set. In addition, a set of signatures can inform them about the last tendermint block in the tendermint chain, which is defined by the Validator set determined by Ouroboros Samasika. This can be done trustlessly, without requiring the light nodes to download the entire blockchain to synchronize and verify it. By leveraging these features of Ouroboros Samasika, we can improve the efficiency and speed of our blockchain while maintaining security and reliability.

PHASE 6.
SHARDING 
In this phase, we will migrate from the Tendermint consensus algorithm to Gasper, which is the current consensus algorithm used in Ethereum. Gasper will introduce improvements, including one slot finality and Rlmd ghost, to address vulnerabilities in the current algorithm. Additionally, Gasper will support sharding, which will be implemented through the introduction of Data Availability sharding.

PHASE 7.
POST-QUANTUM SECURITY
In order to ensure post-quantum security in our blockchain, we plan to upgrade all signature schemes from elliptic curve-based to hash-based. This will make our blockchain less vulnerable to attacks from quantum computers. Additionally, we plan to migrate from SNARK proofs to STARK proofs. STARKs are considered more robust and resistant to quantum computing attacks, making them a better choice for our blockchain’s security. By implementing these upgrades, we aim to provide our users with a highly secure blockchain that can withstand potential threats from quantum computing.

PHASE 8.
FULL DEPLOYMENT OF THE AQUARIUM PROTOCOL
During the full deployment of the Aquarium protocol, Aquaris will be upgraded to a two-layered network for enhanced anonymity. The first layer will consist of entry groups while the second layer will comprise exit groups. Both layers will be powered by the Riffle protocol, which provides strong anonymity for communication within groups.
In addition, the Aquarium protocol will gain all the design features of Aquaris, including decentralized governance through DAOs, the Payment Channel Network (PCN), and the self-protection mechanism against Sybil attacks. The PCN will allow for fast and secure transactions between users while the Sybil protection mechanism will prevent attackers from compromising the network's anonymity by operating multiple nodes.
With DAOs governing the development of the Aquarium protocol, the currency will be designed and maintained in a robust and decentralized manner, ensuring the longevity and sustainability of the network.


