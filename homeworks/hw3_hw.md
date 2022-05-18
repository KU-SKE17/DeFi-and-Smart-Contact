# Homework 3

##### 1. Why it is harder to perform frequency analysis on Vigenere cipher than on substitution cipher?

Because, `substitution cipher use mono-alphabetic encryption` with key for a plain text. It only use a little analysis to mapping a plain text with mono-alphabetic hash. On the other hand, `Vigenere cipher use equations`: Ci, Mi (like metric) to encrypt a plain text which more complicate to analyze.

##### 2. “This crypto system of ours is the most secretive and has never been revealed to anyone. It also uses 128-bit key, so you can be assured that it is 100% secured” Give your criticism on such a claim

In cryptography Kerckhoff's principle, there is a rule said "The key should be the only thing that must be kept secret, and the system should be designed to make it easy to change keys that are lead", which mean `it shouldn't be 100% secured if the whole system never been revealed to anyone`.

##### 3. If one-time pad gives us perfect secrecy, why do we not use it all the time?

Because it is `too secure`, the perfect secrecy is impractical to implement. There are enough potential operational difficulties that provide the adversary an attack vector that the defender's effort is often better spent on something besides the one-time pad key management problems.

##### 4. What are the differences between stream cipher and block cipher?

Both stream cipher and block cipher are the main categories of symmetric encryption algorithms. Which means they use the same key to encrypt and decrypt data. The main difference between the two are `encrypting process` and `environments` they operate in.

To encrypting information for block cipher, plaintext message would be broken down into smaller blocks of binary and will be `process as blocks`. On the other hand for stream cipher, it `process bit-by-bit` (running realtime). Also it encrypt data in long, pseudorandom streams, unlike block cipher that `require the formation of blocks prior` to encryption (so it faster).

| Block Ciphers                                                                                                                               | Stream Ciphers                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| encrypt and decrypt data in fixed-size blocks.                                                                                              | encrypt and decrypt data bit-by-bit.                                                                       |
| Slower processing.                                                                                                                          | Faster processing.                                                                                         |
| Require more resources.                                                                                                                     | Require fewer resources.                                                                                   |
| Can take on stream cipher properties through certain modes of operation.                                                                    | Cannot take on block cipher properties.                                                                    |
| Rely on stateless and stateful modes of operation, which include ECB, CBC, CFB, OFB, CTR, GCM, and XTS. Can be synchronous or asynchronous. | Used nearly everywhere. Used for some data in-transit encryption, including in some SSL/TLS cipher suites. |

##### 5. What are the weaknesses of a system like Kerberos?

It is `too depend on Kerberos server`. For an application to use Kerberos, its source must be modified to make the appropriate calls into the Kerberos libraries, which may require too much programming effort to make certain closed-source applications work with Kerberos.

##### 6. What is the problem solved by the Diffie-Hellman protocol?

It solves `problem about the share key`, the Diffie-Hellman key exchange is to securely develop shared secrets that can be used to derive keys. These keys can then be used with symmetric-key algorithms to transmit information in a protected manner.

##### 7. What problems do public key cryptography solve and what new problems it faces of its own?

Public key solved `distributing keys problem for non-authentication server`. But afterwards, create `Man-in-the-middle(MIM) problem`.

##### 8. How can we have the hiding property for inputs that are derived from a very small domain (not so many members)?

To hiding input x, you can `concatenate x with r`. Meanwhile, r is some random bit strings from a very large and uniformly distributed domain. Calculate hash H(r | x)

##### 9. In the commitment API, why is the “key” necessary? Can we just do it with H(msg)?

Key is the `proof to access` the hash. `We can't just do it with H(msg)` if you want to prevent other to change your msg after you have committed to it.

##### 10. If your website is not certified by a root CA that Chrome or Firefox knows about, would it be flagged as a fake website?

`No, it wouldn't`. Because even a root CA is not certified, your browser will try to finding the certified CA from upper root. (since PKI has Hierarchical management of public key verification)

##### 11. “I do not see why Merkel tree is useful. If I have 8 data blocks and I do not use Merkle tree, I calculate 8 hashes to get the root hash. However, with Merkel tree, I have to calculate 8 + 4 + 2 + 1 = 15 hashes to obtain the root hash” Is this claim valid? Explain why or why not

Merkel tree is used to check whether hash changed, if someone try to edit your blog.

##### 12. How do digital signatures protect the integrity of the document as well as allowing other people to verify that the authenticity of that document?

![digital-signatures](https://docs.oracle.com/cd/E19424-01/820-4811/images/digsgn.gif)

following the steps:

1. Message digest is computed by applying hash function on the message and then message digest is encrypted using private key of sender to form the digital signature.

   ```txt
   digital signature = encryption (private key of sender, message digest)
   ```

   message digest = message digest algorithm(message)

2. Digital signature is then transmitted with the message.

   ```txt
   message + digital signature is transmitted
   ```

3. Receiver decrypts the digital signature using the public key of sender. This assures authenticity, as only sender has his private key so only sender can encrypt using his private key which can thus be decrypted by sender’s public key.
4. The receiver now has the message digest.
5. The receiver can compute the message digest from the message (actual message is sent with the digital signature).
6. The message digest computed by receiver and the message digest (got by decryption on digital signature) need to be same for ensuring integrity.
