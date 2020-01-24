# test-vectors for crypto-related algorithms used in nem project

* 0.test-keccak-256 - Keccak 256 test vectors
* 0.test-sha3-256 - SHA3 256 test vectors

sufixes:
 - `nis1` == NIS1 / catapult pub
 - `catapult` == CATAPULT priv

* 1.test-keys-[SUFFIX] - deriviation of public key from private key
  * `KeyPair("privateKey").publicKey` == "publicKey"
* 1.test-address-[SUFFIX] - deriviation of addresses in all networks from public key - CATAPULT priv
  * `AddressToString(PublicKeyToAddress("publicKey", Public))` == "address\_public"
  * `AddressToString(PublicKeyToAddress("publicKey", Public_Test))` == "address\_public\_test"
  * `AddressToString(PublicKeyToAddress("publicKey", Mijin))` == "address\_mijin"
  * `AddressToString(PublicKeyToAddress("publicKey", Mijin_Test))` == "address\_mijin\_test"
* 2.test-sign-[SUFFIX].dat - ed25519 ECDSA signing
  * `KeyPair("privateKey").publicKey` == "publicKey"
  * `Sign(keyPair, "data", "length")` == "signature"
* 3.test-derive-[SUFFIX].dat - shared key deriviation
  * `keyPair := KeyPair("privateKey")`
  * `DeriveSharedKey(keyPair, "otherPublicKey", "salt")` == "sharedKey"
  * scalarMulResult is an intermediate scalar multiplication result, prior to salting, can be ignored in most tests
* 4.test-cipher.dat - AEC-CBC encryption with IV
  * `keyPair := KeyPair("privateKey")`
  * `sharedKey` := `DeriveSharedKey(keyPair, "otherPublicKey", "salt")`
  * "clearText" == `AesCbcDecrypt(sharedKey, "iv" || "cipherText")`

