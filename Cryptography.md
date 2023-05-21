# Cryptography

Public-private key cryptography is a privacy concept that uses 'keys' to encrypt and decrypt information, normally in an information pathway.

Can be symmetric (single secret key, like in a caesar cipher), or assymetric (different secret keys).

Everyone normally has a public key, and private key for data exchange. 

Interestingly if you published something with your private key instead of your public key it acts as a signature of sorts as only you have it (the priv key), despite anyone being able to decrypt it with your easily accessible public key.

Normally information is double encrypted prior to sending, once with the priv key then a second time with the public key. This is called the 'Diffie-Hellman key exchange'.

See also:
- [[Cybersecurity]]
- [[Number Theory]]
- [[Hashing]]
- [[RSA]]
- [[AES]]
