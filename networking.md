## IPsec VPN
Default port UDP 500, or UDP 4500 when behind the nat
### Internet Key Exchange (IKE) Protocol
- Negotiates security;
- Provides **identitiy authentication**;
- Creates a secure tunnel;
- Decides what trafic will travel through tunnel;

### Encapsulating Security Payload (ESP)
- Encrption
- Integrity
- Origin authentication

#### Encryption Algorythms used in ESP
DES - Data Encryption Standard, is weak, should not be used;
3DES - Does 3 DES opperations in a row to make it more secure, is slow and has a short key, sould be avoided; 
AES - Advanced Encryption Standard, modern, supports varaible key length, strong, recommended;

#### Hashing Algorythms used in ESP
MD5 - old, vulnerable;
SHA1 - Secure hashing algorythm v1, old, known vulnerabilities, should be avoded;
SHA2 - v2 of SHA, modern standard, has several bitlengths (SHA256, SHA512, SHA384), can be considered secure;
