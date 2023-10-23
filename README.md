# Introduction-cryptography
<img src="logo.png" />

The presentation will offer valuable insights into why cryptography matters and how we can use and apply different algorithms in real world scenarios.

## Asymmetric Encryption
### RSA Algorithm
To generate a public and private key using RSA.

```bash
openssl genrsa -out private-key.pem 2048
```
The we can generate a public key from the private key.

```bash
openssl rsa -in private-key.pem -pubout -out public-key.pem
```

We also can see the RSA algorithm private and public parameters.

```bash
openssl rsa -in private-key.pem -text -noout
```

And if we want to encrypt a data for example stored in a file `plaintext.txt` using the public key.

```bash
openssl pkeyutl -encrypt -in plaintext.txt -out ciphertext -inkey public-key.pem -pubin
```

Also if we want to decrypt we would do it using the private key.

```bash
openssl pkeyutl -decrypt -in ciphertext -inkey private-key.pem -out decrypted.txt
```

## Deffie Hellman key exchange

To generate *DH* parameters we would use.

```bash
openssl dhparam -out dhparams.pem 2045
```
And we can print them also.

```bash
openssl dhparam -in dhparams.pem -text -noout
```

## Public Key Infrastructure (PKI)

To generate a certificate using *RSA* we would use the following command.

```bash
openssl req -new -nodes -newkey rsa:4096 -keyout key.pem -out cert.csr
```

And the we would use this to print the certificate data.

```bash
openssl req -in cert.csr -text -noout
```

### Resources you might find helpful:

| Website                 |                         What                          |   Links                  |
| :---------------------: | :---------------------------------------------------: | :----------------------: |
| Roadmap                 | A information website that provides roadmaps for everything.| [Roadmap][Roadmap]       |                        
| Cryptopals              | Website to practice and learn cryptography            | [Cryptopals][Cryptopals] |
| RSA VISUAL              | Cryptool to Visual RSA Algorithm                      | [RSAVISUAL][RSAVISUAL]   |
| RSA Whitepaper          | RSA Cryptographic Algorithm whitepaper                | [RSA][RSA]               |

[Cryptopals]: https://cryptopals.com/
[RSA]: https://sites.math.washington.edu/~morrow/336_09/papers/Yevgeny.pdf
[Roadmap]: https://roadmap.sh
[RSAVISUAL]: https://www.cryptool.org/en/cto/rsa-visual
