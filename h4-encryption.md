# H4 Encryption


## Summaries


### Applied Cryptography


### Disobey 2023


## Encrypt and Decrypt


I referred to [Tero's Guide](https://terokarvinen.com/2023/pgp-encrypt-sign-verify/) to try out PGP (Pretty Good Privacy). PGP is a security program used to encrypt and decrypt email and to authenticate email messages through digital signatures and file encryption. PGP was one of the first public-key cryptography softwares publicly available for free [(source)](https://www.fortinet.com/resources/cyberglossary/pgp-encryption).

After installing the required tools I went ahead and generated a key.



## Cracking Cyphertext

>HDMH'B TH. KWU'YI AWR WSSTOTMJJK M OWQINYIMLIY! MB KWU BII, BTGPJI BUNBHTHUHTWA OTPDIYB OMA NI NYWLIA RTHD SYIEUIAOK MAMJKBTB. BII KWU MH DHHP://HIYWLMYCTAIA.OWG

I cracked this text in Microsoft Word. I started with the most obvious characters - in the first word this was guessing that the B after the apostrophe was likely an S. Whereas in the third word the two letters after the apostrophe were most likely RE. Near the end was a website address so through deciphering the HTTP, I got a few more letters revealed. I continued to work systematically like this and the more letters I revealed, the more words I was able to guess.

![Deciphering the text](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-08%20104432.png)

The final result was

>THAT'S IT. YOU'RE NOW OFFICIALLY A CODEBREAKER! AS YOU SEE, SIMPLE SUBSTITUTION CIPHERS CAN BE BROKEN WITH FREQUENCY ANALYSIS. SEE YOU AT HTTP://TEROKARVINEN.COM
