# Introduction-cryptography
<img src="logo.png" />

The presentation will offer valuable insights into why cryptography matters and how we can use and apply different algorithms in real world scenarios.

## Asymmetric Encryption

### RSA Algorithm
The RSA (Rivest-Shamir-Adleman) algorithm plays a pivotal role in public-key cryptography. To generate public and private keys using RSA, you can use the following commands:

```bash
openssl genrsa -out private-key.pem 2048
```

To derive a public key from the private key:
```bash
openssl rsa -in private-key.pem -pubout -out public-key.pem
```

You can inspect the RSA algorithm's private and public parameters using:
```bash
openssl rsa -in private-key.pem -text -noout
```

Encrypting data, such as a file named plaintext.txt, with the public key can be done as follows:
```bash
openssl pkeyutl -encrypt -in plaintext.txt -out ciphertext -inkey public-key.pem -pubin
```

Decrypting the data requires the use of the private key:
```bash
openssl pkeyutl -decrypt -in ciphertext -inkey private-key.pem -out decrypted.txt
```

## Deffie Hellman key exchange
The Diffie-Hellman key exchange method enables secure communication by establishing shared secret keys. To generate Diffie-Hellman parameters, you can utilize the following command:

```bash
openssl dhparam -out dhparams.pem 2045
```
You can also examine the generated parameters:
```bash
openssl dhparam -in dhparams.pem -text -noout
```

## Public Key Infrastructure (PKI)

Public Key Infrastructure is essential for secure online transactions and communication. To create a certificate using RSA encryption, you can employ the following command:

```bash
openssl req -new -nodes -newkey rsa:4096 -keyout key.pem -out cert.csr
```

You can view the certificate data with:
```bash
openssl req -in cert.csr -text -noout
```

### Resources you might find helpful:

| Website                 |                         What                          |   Links                  |
| :---------------------: | :---------------------------------------------------: | :----------------------: |
| Roadmap                 | A comprehensive information website that offers roadmaps for various topics. | [Roadmap][Roadmap]       |                        
| Cryptopals              | A platform for practicing and learning cryptography.  | [Cryptopals][Cryptopals] |
| RSA VISUAL              | Visualize the RSA algorithm and its operations.                     | [RSAVISUAL][RSAVISUAL]   |
| RSA Whitepaper          | A detailed whitepaper on the RSA cryptographic algorithm.             | [RSA][RSA]               |

[Cryptopals]: https://cryptopals.com/
[RSA]: https://sites.math.washington.edu/~morrow/336_09/papers/Yevgeny.pdf
[Roadmap]: https://roadmap.sh
[RSAVISUAL]: https://www.cryptool.org/en/cto/rsa-visual
