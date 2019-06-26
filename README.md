# test-vectors for crypto-related algorithms used in nem project

* 0.test-keccak-256 - Keccak 256 test vectors
* 0.test-sha3-256 - SHA3 256 test vectors

sufixes:
 - `nis1` == NIS1 / catapult pub
 - `catapult` == CATAPULT priv

* 1.test-keys-<suffix> - deriviation of public key from private key
* 1.test-address-<suffix> - deriviation of addresses in all networks from public key - CATAPULT priv
* 2.test-sign-<suffix>.dat - ed25519 ECDSA signing
* 3.test-derive-<suffix>.dat - shared key deriviation
* 4.test-cipher.dat - AEC-CBC encryption with IV

